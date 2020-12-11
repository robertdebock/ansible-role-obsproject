# [obsproject](#obsproject)

Install obsproject on your system.

|Travis|GitHub|GitLab|Quality|Downloads|Version|
|------|------|------|-------|---------|-------|
|[![travis](https://travis-ci.com/robertdebock/ansible-role-obsproject.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-obsproject)|[![github](https://github.com/robertdebock/ansible-role-obsproject/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-obsproject/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-obsproject/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-obsproject)|[![quality](https://img.shields.io/ansible/quality/42908)](https://galaxy.ansible.com/robertdebock/obsproject)|[![downloads](https://img.shields.io/ansible/role/d/42908)](https://galaxy.ansible.com/robertdebock/obsproject)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-obsproject.svg)](https://github.com/robertdebock/ansible-role-obsproject/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.obsproject
```

The machine needs to be prepared in CI this is done using `molecule/resources/prepare.yml`:
```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.rpmfusion
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.


## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/robertdebock/ansible-role-obsproject/blob/master/requirements.txt).

## [Status of requirements](#status-of-requirements)

The following roles are used to prepare a system. You may choose to prepare your system in another way, I have tested these roles as well.

| Requirement | Travis | GitHub |
|-------------|--------|--------|
| [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-bootstrap.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-bootstrap) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions) |
| [robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-epel.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-epel) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions) |
| [robertdebock.rpmfusion](https://galaxy.ansible.com/robertdebock/rpmfusion) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-rpmfusion.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-rpmfusion) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-rpmfusion/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-rpmfusion/actions) |

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/obsproject.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|el|7|
|debian|buster, bullseye|
|fedora|33|
|ubuntu|focal, bionic|

The minimum version of Ansible required is 2.9, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some variarations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| opensuse | Requires [much more efforts](https://obsproject.com/wiki/install-instructions#opensuse-installation-unofficial) than usual. |
| alpine | obs-studio (missing) |
| centos:latest | nothing provides libSDL2-2.0.so.0()(64bit) needed by ffmpeg-4.2.1-3.el8.x86_64 |
| amazonlinux | Missing dependecies |
| fedora:rawhide | Failure downloading https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-33.noarch.rpm |


## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-obsproject) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-obsproject/issues)

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

[Robert de Bock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
