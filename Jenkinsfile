pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        script {
          docker.withRegistry(
            'https://160358738096.dkr.ecr.us-west-2.amazonaws.com',
            'ecr:us-west-2:docker_registry_push')
          {
            def myImage = docker.build('test_repo')
            myImage.push()
          }
        }
      }
    }
  }
}
       
