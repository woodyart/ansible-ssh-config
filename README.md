Role Name
=========

The role creates ssh connections file based on your ansible inventory file and includes it into your `~/.ssh/config`.


Role Variables
--------------

The role takes these hosts variables from inventory file:

* `inventory_hostname` or `ansible_host` for `Host`
* `ansible_port` for `Port` if present
* `ansible_user` for `User` if present
* `ansible_ssh_private_key_file` for `IdentityFile` if present

Also you need to specify variables for ssh config

* `confd_path` - path to a directory where your ssh connections stored, like `~/.ssh/conf.d`
* `ssh_config_name` - name of your ssh connections file, that will be placed into `confd_path`

For exmple: your `confd_path` is `~/.ssh/includes` and `ssh_config_name` is `my_aws_hosts`. Then all config will be stored in `~/.ssh/includes/my_aws_hosts` and included in `~/.ssh/config` file

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- name: Create SSH config from inventory
  hosts: localhost
  connection: local
  gather_facts: no
  roles:
    - ssh-config
```

License
-------

BSD
