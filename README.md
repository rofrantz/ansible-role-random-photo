Random Photo w/Ansible 
=========
[![Ansible Role](https://img.shields.io/ansible/role/20265.svg)](https://galaxy.ansible.com/rofrantz/random-photo/)
[![Build Status](https://travis-ci.org/rofrantz/ansible-role-random-photo.svg?branch=master)](https://travis-ci.org/rofrantz/ansible-role-random-photo)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://galaxy.ansible.com/rofrantz/random-photo/)

An Ansible role that installs [Random Photo](https://github.com/rofrantz/random-photo) on Ubuntu machines via [Ansible Galaxy](https://galaxy.ansible.com/).

Requirements
------------
Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## ansible.cfg
This role is designed to work with merge "hash_behaviour". Make sure your
ansible.cfg contains these settings

```INI
[defaults]
hash_behaviour = merge
```

Role Variables
--------------
Available variables are listed below, along with default values (see `defaults/main.yml`):

    # defaults file for Random Photo
    app_engine: Filesystem
    
    project_name: "random-photo"
    project_destination_folder: "/var/www/{{ project_name }}"
    
    nginx_user: "www-data"
    nginx_group: "www-data"
    nginx_root: "{{ project_destination_folder -}}/web"
    nginx_server_name: "{{ project_name }}"
    nginx_port: 9000
    
Dependencies
------------
N/A

Example Playbook
----------------
Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: rofrantz.random-photo, app_photo_path: "/path/of/your/photos" }

License
-------
MIT

Author Information
------------------
Francisc Ungureanu
