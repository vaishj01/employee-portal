pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/vaishj01/employee-portal.git'
            }
        }

        stage('Verify Files') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                echo 'HTML/CSS Project Build Successful'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp -r * /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Webhook Triggered Build Successfully!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}
