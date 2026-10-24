pipeline {

    agent any

    stages {

        stage('Get The Code from Git') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ramireddybolla23/pet_shop.git'
            }
        }

        stage('Build the Code') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy in Tomcat') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'r', path: '', url: 'http://52.63.43.148:8090/')], contextPath: 'app', war: '**/*.war'
            }
        }

    }
}
