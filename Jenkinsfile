pipeline {
    agent {
        docker {
            image 'node:6'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('installdeps') {
            steps {
                sh 'npm install'
                // sh 'npm run bower'
            }
        }
        stage('build') {
            steps {
                sh 'printenv'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        // stage('Deliver') { 
        //     steps {
        //         sh './jenkins/scripts/deliver.sh' 
        //         input message: 'Finished using the web site? (Click "Proceed" to continue)' 
        //         sh './jenkins/scripts/kill.sh' 
        //     }
        // }
    }
}
