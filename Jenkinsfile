pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('init') {
       steps {
        script{
          def dockerPath = tool 'docker' //全局配置里的docker
          echo dockerPath
          env.PATH = "${dockerPath}/bin:${env.PATH}" //添加了系统环境变量上
        }
       }
    }
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

  }
}
