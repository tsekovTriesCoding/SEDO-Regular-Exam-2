pipeline {
    agent {
        label 'windows' // Ensure you have a Windows agent labeled as such
    }

    environment {
        DOTNET_VERSION = '8.0.x'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                powershell 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                powershell 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                powershell 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
