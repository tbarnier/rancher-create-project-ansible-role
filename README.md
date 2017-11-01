# rancher-create-project-ansible-role

Ansible role to create rancher project.
This role is also in charge to configure custom registry if you have one.

At the end this role will produce an apikey file in {{ inventory_dir }}/group_vars/{{ rancher_project_name }}/apikey.yml containing the following variables :
* rancher_api_key
* rancher_api_secret
* rancher_project_id


Mandatory Variables
-------------------
```
rancher_api_key: "mykey"
rancher_api_secret: "mysecret"
rancher_project_name: "default"
```

Role Variables
--------------

```
rancher_master_url: "http://localhost:8080"
rancher_project_template_name: "Cattle"

docker_registries: []
```

Registries  Examples
----------
```
docker_registries:
  # docker hub
  - url: index.docker.io
    username: XXX
    password: ZZZ
  # if you have the ca certificate
  - url: my.custom.registry
    username: XXX
    password: ZZZ
```
License
-------

Apache License 2
