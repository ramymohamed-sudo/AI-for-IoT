

pipeline {

    agent { docker { image 'python:3.5.1' } }
    

    node{
    // def commit_id 
    // commit_id = 'python-test'

    stages {
        
        stage('build') {
            steps {
                sh 'python --version'
            }
        }


        stage('docker build/push'){
        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub'){
            def app = docker.build("ramyrr/docker-python:${commit_id}", '.').push()
        }
    } 

        
    }

}

}

// node{

//     def commit_id 

//     stage('Preparation'){
//         checkout scm
//         sh 'git rev-parse --short HEAD > .git/commit-id'  
//         commit_id = readFile('.git/commit-id').trim()
//     }


//     stage('test'){
//         withPythonEnv('python3') {
//         sh 'python --version'
//         // sh 'python3 train-rul.py'
//         }
//         // nodejs(nodeJSInstallationName: 'nodejs'){
//         //     sh 'npm install --only-dev'
//         //     // sh 'npm test'
//         // }
//     }


//     stage('docker build/push'){
//         docker.withRegistry('https://index.docker.io/v1/', 'dockerhub'){
//             def app = docker.build("ramyrr/docker-node-js-demo:${commit_id}", '.').push()
//         }
//     }    

// }