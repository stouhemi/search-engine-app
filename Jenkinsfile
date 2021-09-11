pipeline {
    agent any
    
    stages {
        stage ('test') {
            steps {
                sh( returnStdout: false, script: """#!/bin/sh
                    g++ generate.cpp -o generate
                    chmod u=x generate
                    ./generate
                    """.stripIndent()
                    g++ search.cpp -o search
                    chmod u=x search
                    ./search
                    returnStdout: false, script: """#!/bin/sh
                    if cmp -s RES.txt OUT.txt ; then echo SUCCESS ; else exit 1 ; fi
                    """.stripIndent()
                )
            }
        }
    }
