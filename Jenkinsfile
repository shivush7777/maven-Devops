node('master') 
{
    stage('CD') 
    {
     git 'https://github.com/sandytanti/maven-Devops.git'
    }
    stage('CB') 
    {
     sh 'mvn package'
    }
    stage('CDep') 
    {
     sh 'scp /root/.jenkins/workspace/SP/webapp/target/webapp.war ubuntu@172.31.44.159:/var/lib/tomcat9/webapps/testenv.war'
    }
    stage('CT')
    {
     git 'https://github.com/sandytanti/Testing-Devops.git'
     sh 'java -jar /root/.jenkins/workspace/SP/testing.jar'
    }
    stage('CDev') 
    {
      sh 'scp /root/.jenkins/workspace/SP/webapp/target/webapp.war ubuntu@172.31.46.252:/var/lib/tomcat9/webapps/prod.war'
    }
}

