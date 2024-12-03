pipeline{
    agent any
    tools{
        
        maven 'mavenhome'  
    }
    
    stages{
        stage('checkout gitcode'){
            
            steps{
                
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kliakos/sparkjava-war-example.git']])
            }
        }
        stage('create package using maven'){
            steps{
                
                sh 'mvn package'
            }
        }
        stage('deploy'){
    steps{
	  sh 'cp -r /var/lib/jenkins/workspace/build/target/sparkjava-hello-world-1.0.war  /opt/apache-tomcat-9.0.97/webapps'
	
	}
}
