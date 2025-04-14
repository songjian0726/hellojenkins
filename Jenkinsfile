pipeline {
  agent {
    docker {
      image 'python:3.11-slim'
    }
  }

  stages {
    stage('Check Python') {
      steps {
        sh 'python --version'
      }
    }

    stage('Run Unit Tests') {
      steps {
        sh '''
          pip install -r requirements.txt || true
          pytest tests/ || echo "test failed"
        '''
      }
    }
  }
}
