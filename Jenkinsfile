pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                git 'https://github.com/thedovekana/GLPI-PROJECT.git'
            }
        }

        stage('Copy yaml files to Ansible server') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansiblemaster', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQM7/oZqkpef6k7MxTl/3oj6Oibg2gV67waRVXYIcfGnQ=}', key: '', keyPath: '', username: 'vagrant'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sudo rm -Rf *.yml', execTimeout: 300000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home//vagrant', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansiblemaster', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQcFydTQTWGvC/NyTg5OBFmce5ABAUS0xA8fdl9EHQEkY=}', key: '', keyPath: '', username: 'vagrant'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 300000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home//vagrant', remoteDirectorySDF: false, removePrefix: '', sourceFiles: ' *.yml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                
                
            }
        }
        stage('Deploy to docker server') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansiblemaster', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQ8YGhTNfGu+KPcPI5vJQTjWKUoxNgPvHJu2wyDC3pQO8=}', key: '', keyPath: '', username: 'vagrant'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook glpi-deploy.yml', execTimeout: 300000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home//vagrant', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                
                
            }
        }
    }
}
