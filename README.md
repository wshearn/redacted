# Redacted


Redacted is a DevOps tool to allow opertations the ability to delegate yaml
config access to developers without having to worry about censoring data
everytime they pull the file.

### Installation

Redacted requires python with PyYAML installed.

Copy redacted.yaml to /etc and setup config files

Example redacted.yaml
```yaml
---
config:
- name: master-config
  path: /etc/origin/master/master-config.yml
  attributes:
  - oauthConfig.identityProviders.provider.url
  - oauthConfig.identityProviders.provider.bindPassword
  - oauthConfig.identityProviders.provider.bindDN
```

Copy redacted.py to /usr/sbin/redacted

Setup sudo access to redacted
In /etc/sudoers
```sh
%developers  ALL=/usr/sbin/redacted
```

