[//]: # (Describe the project's purpose.)

## `vulturm.custom-vim` - ansible role

The `vulturm.custom-vim` project goal is to provide a standard way to customize our vim installation to be used during ansible development..


[//]: # (TOC.)

- [About this project](#)
- [What is anible](#what-is-ansible)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [License](#license-and-authors)

[//]: # (Describe the technology used.)

## What is ansible
[Ansible][1] is an open source software that automates software provisioning, configuration management, and application deployment.
Simple yaml based configuration that gives you a single view of your entire infrastructure.

[//]: # (List Project dependencies.)

## Dependencies
|Dependency |Comments |
|:---------|:----------|
| `ansible` | This project was developed and tested using `Ansible v2.7.4` |


## Role Variables
--------------
|   Name               | Default Value | Description                                                      |
|----------------------|---------------|------------------------------------------------------------------|
| `vim_config_entrypoint` | `~/.vimrc` | Entrypoint to inject `vim` configuration. |
| `vim_config_plugins_file` | `~/.vim/vimrc.plugins` | Name of the file where we will keep plugins configuration. |
| `vim_config_defaults_file` | `~/.vim/vimrc.defaults` | Name of the file that holds our default deployed configuration. See: `vim_config_deploy_defaults_file`. |
| `vim_config_user_file` | `~/.vim/vimrc.local` | Name of the file where use could keep his configuration and ansible won't touch. |
| `vim_config_deploy_defaults_file` | `true` | If we want to deploy default playbook configuration or not. |
| `vim_config_install_plugins` | `[]` | List of `VIM plugins` that user wants to install. |
| `vim_config_custom_syntax` | `""` | String. Custom configuration that we want to be inserted in our vim configs. Can be used to customize installed plugins. |



Dependencies
------------
None.

Usage
----------------

* Save the following in a file named `install_custom_vim.yml`.
```yaml
---
- name: "Configures vim"
  hosts: localhost

  roles:
  - { role: vulturm.vim-config }
```

## Playbook invocation
```yaml
ansible-playbook install_custom_vim.yml
```

## Authors / Maintainers
* Owner - Mihai Vultur
* Team - SRE

[1]: https://www.ansible.com/ "Ansible"
