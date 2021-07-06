pipeline {
    agent any
    stages {
        stage('Setup parameters') {
            steps {
                script {
                    properties([
                        parameters([
                           
                            string(
                                defaultValue: 'Madhu',
                                name: 'FIRST_NAME',
                                trim: true
                            ),
                            string(
                                defaultValue: 'Chejerla',
                                name: 'LAST_NAME',
                                trim: true
                            ),
                            string(
                                defaultValue: 'Bangalore',
                                name: 'CITIES',
                                trim: true
                            ),
                            string(
                                defaultValue: 'I love python' ,
                                name: 'ABOUT_ME',
                                trim: true
                            ),
                             choice(
                                choices: ['No', 'Yes'],
                                name: 'VACCINATED'
                            )
                        ])
                    ])
                }
            }
        }
        stage('Use Parameters') {
            steps   {
                sh 'python sample.py ${params.FIRST_NAME} ${params.LAST_NAME} ${params.CITIES} ${params.ABOUT_ME} ${params.VACCINATED}'
                print "FIRST_NAME value is ${params.FIRST_NAME}"
                print "LAST_NAME value is ${params.LAST_NAME}"
                print "CITIES value is ${params.CITIES}"
                print "ABOUT_ME value is ${params.ABOUT_ME}"
                print "VACCINATED value is ${params.VACCINATED}"
            }
        }
    }
}
