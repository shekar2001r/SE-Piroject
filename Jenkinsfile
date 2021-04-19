pipeline {
    agent any 

    tools {nodejs "node"}

    stages{
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh 'deploy.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'kill.sh'
            }
        }
    }
}
