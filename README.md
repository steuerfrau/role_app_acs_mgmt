role_app_acs-mgmt
============
Installs a Cloudstack Management Node, according to:

http://docs.cloudstack.apache.org/en/4.14.0.0/installguide/management-server/index.html

Requirements
------------

Expects a baseinstall, according to my playbook "playbook_baseinstall".

Role Variables
--------------

Nothing important to say here.

Dependencies
------------

Uses:
```
- name: Create Repositories
  import_role:
    name: role_mod_repositories
  vars:
    - role_mod_repositories_yum_repos:
        - name: CloudStack-ShapeBlue
          description: "ShapeBlue CloudStack Repository."
          file: "CloudStack-ShapeBlue"
          baseurl: "http://packages.shapeblue.com/cloudstack/upstream/centos7/4.14"
          gpgcheck: "yes"
          gpgkey: "http://packages.shapeblue.com/release.asc"
          enabled: "yes"
```

Example Playbook
----------------

Is utilized in my playbook "playbook_acs_single_node".
   
License
-------

GNU Public License v3.0

Author Information
------------------

Melanie Desaive, m.desaive@mailbox.org
