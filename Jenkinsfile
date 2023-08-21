pipeline {
    agent { 
       node { label 'agent1' }
    }
    
   stages {
        stage('Git clone') { 
            steps {
                git 'https://github.com/vijayj1995/demo-java.git'
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy to tomcat') { 
            steps {
                sh 'echo "i am Deploying"'
                sh 'sudo cp /home/jenkins/jenkins_slave/workspace/pipeline_job/target/demo.war /opt/tomcat/apache-tomcat-9.0.79/webapps/' 
                sh 'sudo systemctl stop tomcat'
                sh 'sudo systemctl start tomcat'
            }
        }
    }
}
