

pipeline {
    agent any

    options {
        timestamps()
    }

    stages {

        stage('Checkout - Cloner le dépôt') {
            steps {
                git url: 'https://github.com/zouhour-hub/TPJenkins.git',
                    branch: 'main'
            }
        }

        stage('Build - Vérification du dépôt') {
            steps {
                bat 'echo === Vérification du dépôt ==='
                bat 'git status'
            }
        }

        stage('Test - Afficher le contenu du projet') {
            steps {
                bat 'echo === Afficher le contenu du projet ==='
                bat 'dir'
                bat 'if not exist index.html exit /b 1'
                bat 'echo TEST SUCCESS'
            }
        }

        stage('Deploy - Simuler un déploiement local') {
            steps {
                bat 'echo === Simulation du déploiement local ==='
                bat 'echo Le fichier index.html est prêt à être affiché'
            }
        }
    }

    post {
        success {
            echo 'BUILD OK'
        }
        failure {
            echo 'BUILD KO'
        }
    }
}
