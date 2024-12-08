pipeline {
    agent any
    
    tools {
        //To specify the maven to use
        maven "mvn-3.9.8"
    }
    
    stages {
        stage('Checkout'){
            steps{
                //Checkout the source repo from scm
                git 'https://github.com/vanand46/simple-java-maven-app.git'
            }
        }
        stage('Build'){
            steps{
                //Use maven to build the project
                sh 'mvn clean package'
            }
        }
        stage('Test'){
            steps{
                //Run tests if applicable
                sh 'mvn test'
            }
        }
    }
    post{
        success{
            //This will be executed if the pipeline execution is successful
            echo 'Pipeline executed successfully!'
        }
        failure{
            //This will be executed if the pipeline execution fails
            echo 'Pipeline failed!'
        }
    }
}
