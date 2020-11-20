# [openvpn](#openvpn)

Install and configure openvpn server or client on your system.

|Travis|GitHub|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|XXXX|[![github](https://github.com/redbeard28/ansible-role-openvpn/workflows/Ansible%20Molecule/badge.svg)](https://github.com/redbeard28/ansible-role-openvpn/actions)|[![quality](https://img.shields.io/ansible/quality/37845)](https://galaxy.ansible.com/redbeard28/openvpn)|[![downloads](https://img.shields.io/ansible/role/d/37845)](https://galaxy.ansible.com/redbeard28/openvpn)|[![Version](https://img.shields.io/github/release/redbeard28/ansible-role-openvpn.svg)](https://github.com/redbeard28/ansible-role-openvpn/releases/)|

## [First of ALL](#First of ALL)
This role was forked from [robertdebock](https://github.com/robertdebock). Please go to its repositories to see his great work.

 

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  vars:
    openvpn_server: yes

  roles:
    - role: robertdebock.openvpn
```

The machine needs to be prepared in CI this is done using `molecule/resources/prepare.yml`:
```yaml
---
- name: Prepare server
  hosts: all
  gather_facts: no
  become: yes
  serial: 30%

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.buildtools
    - role: robertdebock.epel
    - role: robertdebock.python_pip
    - role: robertdebock.openssl
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for openvpn

# Generated keys are saved locally, in what directory do you want to save these files?
openvpn_local_key_directory: /tmp
```

## [Requirements](#requirements)

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the current, previous and next release of Ansible.)

## [Status of requirements](#status-of-requirements)

| Requirement | Travis | GitHub |
|-------------|--------|--------|
| [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-bootstrap.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-bootstrap) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions) |
| [robertdebock.buildtools](https://galaxy.ansible.com/robertdebock/buildtools) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-buildtools.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-buildtools) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-buildtools/actions) |
| [robertdebock.ca](https://galaxy.ansible.com/robertdebock/ca) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-ca.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-ca) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-ca/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-ca/actions) |
| [robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-epel.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-epel) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions) |
| [robertdebock.openssl](https://galaxy.ansible.com/robertdebock/openssl) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-openssl.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-openssl) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-openssl/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-openssl/actions) |
| [robertdebock.python_pip](https://galaxy.ansible.com/robertdebock/python_pip) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-python_pip.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-python_pip) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-python_pip/actions) |
| [robertdebock.reboot](https://galaxy.ansible.com/robertdebock/reboot) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-reboot.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-reboot) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-reboot/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-reboot/actions) |
| [robertdebock.update](https://galaxy.ansible.com/robertdebock/update) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-update.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-update) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-update/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-update/actions) |

## [Dependencies](#dependencies)

Most roles require some kind of preparation, this is done in `molecule/default/prepare.yml`. This role has a "hard" dependency on the following roles:

- robertdebock.ca
## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/openvpn.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|debian|buster, bullseye|
|ubuntu|focal, bionic|

The minimum version of Ansible required is 2.9, tests have been done to:

- The previous version.
- The current version.
- The development version.



## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-openvpn) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-openvpn/issues)

Testing is done using [Tox](https://tox.readthedocs.io/en/latest/) and [Molecule](https://github.com/ansible/molecule):

[Tox](https://tox.readthedocs.io/en/latest/) tests multiple ansible versions.
[Molecule](https://github.com/ansible/molecule) tests multiple distributions.

To test using the defaults (any installed ansible version, namespace: `robertdebock`, image: `fedora`, tag: `latest`):

```
molecule test

# Or select a specific image:
image=ubuntu molecule test
# Or select a specific image and a specific tag:
image="debian" tag="stable" tox
```

Or you can test multiple versions of Ansible, and select images:
Tox allows multiple versions of Ansible to be tested. To run the default (namespace: `robertdebock`, image: `fedora`, tag: `latest`) tests:

```
tox

# To run CentOS (namespace: `robertdebock`, tag: `latest`)
image="centos" tox
# Or customize more:
image="debian" tag="stable" tox
```

## [License](#license)

Apache-2.0


## [Author Information](#author-information)

 * Original source [Robert de Bock](https://robertdebock.nl/)
 * Adapted for my use [Jeremie CUADRADO](https://github.com/redbeard28)
    * Add some templating for server.conf and client.conf
