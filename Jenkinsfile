pipeline {

  agent { label 'kubepods' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/tuladhar/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "config")
        }
      }
    }

  }

}
