pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rmhman/tftest']]])
            }
        }
        
        stage("Terraform Init") {
            steps {
                sh ("terraform init");
            }
        }
        
        stage ("Terraform Action") {
            steps {
                echo "Terraform Action is ${action}"
                sh ("terraform ${action} --auto-approve");
            }
        }
    }
}
