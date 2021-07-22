pipeline {
    agent any
    
    stages {
        stage ('Checkout Git') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-suvarna', url: 'https://github.com/suvarna-gaikwad/javaparser-maven-sample']]])
            }
        }
        
        stage ('Build') {
            steps {
                bat '''set java_home=C:\\Program Files (x86)\\Java\\jdk1.8.0_151
                    set m2_home=D:\\apache-maven-3.8.1
                    set path=%java_home%\\bin;%m2_home%\\bin;%path%
                    mvn clean install
                    java -jar target\\javaparser-maven-sample-2.0-shaded.jar'''
            }
        }
    }
}
