## Example role


This test role shows how to use global project variables and how to use variables inside a loop of tasks.

The global variable `project_test_ports` describes set of values (let's call them ports), each one of them is supposed to be used inside a loop of tasks (`tasks_per_port.yml`). Value of the variable `test_name` produced by using loop variable `test_port`.

To access global variables inside roles, use prefix `pv.project_test_ports`. The prefix `pv` defined inside `test-role.yml`.

More info about `include_vars`: https://docs.ansible.com/ansible/latest/modules/include_vars_module.html .


You can run the role using `ansible-playbook`:
```
ansible-playbook test-role.yml
```

Output should be something like this:
```
...

TASK [test-role : test] ********************************************************
ok: [localhost] => {
    "msg": "port: 6400, name: name_6400"
}

TASK [test-role : test] ********************************************************
ok: [localhost] => {
    "msg": "port: 6401, name: name_6401"
}

TASK [test-role : test] ********************************************************
ok: [localhost] => {
    "msg": "port: 6402, name: name_6402"
}
...

```

----

#### Requirements
- Ansible 2.5+
