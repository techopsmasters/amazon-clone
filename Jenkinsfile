pipeline {
    agent any

    environment {
        DOCKER_COMPOSE = '/usr/bin/docker-compose' // Adjust the path if necessary
    }

    stages {
        stage('Checkout') {
            steps {
                git branch:'main', url:'https://github.com/techopsmasters/amazon-clone.git'
            }
        }
        
        stage('Build and Deploy') {
            steps {
                script {
                    sh "${env.DOCKER_COMPOSE} down"
                    sh "${env.DOCKER_COMPOSE} up -d --build"
                }
            }
        }
    }
}
