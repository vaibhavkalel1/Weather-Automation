pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git 'https://github.com/vaibhavkalel1/Weather-Automation.git'
            }
        }
        /*stage('Build Docker Image') {
            steps {
                script {
                    bat "docker build -t vaibhavkalel/weather-automation ."
                }
            }
        }
        stage('Cretae Docker Container') {
            steps {
                script {
                    bat "docker run -d --name weatherautomationcontainer -p 8000:8000  vaibhavkalel/weather-automation"
                }
            }
        }
        stage('Push Docker Images to Docker Hub') {

            steps {

                script {

                    // Log in to Docker Hub using Jenkins credentials

                    withCredentials([usernamePassword(credentialsId: 'docker-cred', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {

                        bat "docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD"

 

                        // Push the Docker images to your Docker Hub repository
                     
                        bat 'docker push vaibhavkalel/weather-automation'

                    }

                }

            }
        }
        stage('Download Minikube for Windows') {
            steps {
                bat 'curl -Lo minikube.exe https://storage.googleapis.com/minikube/releases/latest/minikube-windows-amd64.exe'
            }
        }
        stage('Install Minikube') {
            steps {
                bat 'move minikube.exe C:\\Users\\12826\\.jenkins\\workspace\\Weather-Automation'
                bat 'setx PATH "%PATH%;C:\\minikube"'
            }
        }
        stage('Start Minikube') {
            steps {
                script {
                    // Define Minikube installation path (update as needed)
                    def minikubePath = 'C:\\Users\\12826\\minikube.exe'

 

                    // Start Minikube
                    bat "cd C:\\Users\\12826\\.jenkins\\workspace\\Poll-Automation && ${minikubePath} start --driver=docker"
                }
            }
        }
        stage('Minikube status') {
            steps {
                script {
                    bat "minikube status"
                }
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                script {
                    bat "kubectl apply -f deployment.yml"
                    bat "kubectl get deployment"
                }
            }
        }
        stage('Create NodePort Service') {
            steps {
                script {
                    bat "kubectl apply -f service.yml"
                    bat "kubectl get svc"
                }
            }
        }*/
        stage('Expose NodePort 8000') {
            steps {
                script {
                    bat "kubectl expose deployment weather-automation-deployment --type=NodePort --port=8000"
                }
            }
        }
        /*stage('Get URL and play with Application') {
            steps {
                script {
                    bat "minikube service weather-automation-service"
                }
            }
        }*/
    }
}
