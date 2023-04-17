pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/ryanaelliss/flask.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t ryanaelliss/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u ryanaelliss -p dckr_pat_QjEJQbvnJovVq_Hx-8AISy-JfGs'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push ryanaelliss/flask_app'
      }
    }

  }
}