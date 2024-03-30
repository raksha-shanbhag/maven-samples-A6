pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
  stages {
    stage('check out / Git') {
      steps {
        git(branch: 'master', url: 'https://github.com/raksha-shanbhag/maven-samples-A6.git')
      }
    }

    stage('Bisect') {
      steps {
        sh '''git bisect start
git bisect bad
git bisect good 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
git bisect run mvn clean test'''
      }
    }

    stage('run') {
      steps {
        sh 'mvn clean test'
      }
    }

  }
  tools {
    maven 'DHT_MVN'
    jdk 'DHT_SENSE'
  }
}
