# rails-project

This is a role to provision some basic folder for a rails project based on
Capistrano deployment folder.

## Dependencies in the machine

 - ruby(with rvm)
 - node
 - logrotate


## Default Variables

```yml
---
rails_project_deploy_to: /srv/rails_project
rails_project_current_dir: "{{ rails_project_deploy_to }}/current"
rails_project_public_dir: "{{ rails_project_current_dir }}/public"
rails_project_shared_dir: "{{ rails_project_deploy_to }}/shared"
rails_project_log_dir: "{{ rails_project_shared_dir }}/log"
rails_project_database_name: "rails_project_{{ env }}"
rails_project_gemset: rails_project
```

## Usage

```yml
---
- name: Playbook example
  hosts: example_host
  roles:
    - role: rails-project
      rails_project_deploy_to: /srv/example_project
      rails_project_gemset: example_project
```
