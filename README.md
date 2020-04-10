# Ansible Role: Unix Home Setup

Setup unix home directory (fzf, shell+vim+tmux configs and more), to make users feel at home.

## Requirements

- git

## Role Variables

Defaults:

- URL to the fzf repository (`fzf_repo: https://github.com/junegunn/fzf.git`)
- URL to the vundle repository (`vundle_repo: https://github.com/VundleVim/Vundle.vim.git`)
- default URL of the local_configs_repo (`local_configs_repo: "https://github.com/tnaglo/.local-configs.git"`)
- default URL of the tmux_base_config_repo (`tmux_base_config_repo: "https://github.com/tnaglo/.tmux.git"`)

Variables that should be set via parameters to the role:

```yaml
unix_home_setup_configs:
  - user: [username]
    tmux_base_config_repo: (optional) # default: https://github.com/tnaglo/.tmux.git
    local_configs_repo: (optional) # default: https://github.com/tnaglo/.local-configs.git
```

## Dependencies

- viasite-ansible.zsh

## Example Playbook

```yaml
---
- hosts: all
  roles:
    - role: tnaglo.unix_home_setup
      vars:
        unix_home_setup_configs:
          - user: tnaglo
            tmux_base_config_repo: 'https://github.com/tnaglo/.tmux.git'
            local_configs_repo: 'https://github.com/tnaglo/.local-configs.git'
```

The variables above equal to the current default and can be therefore skipped.

```yaml
---
- hosts: all
  roles:
    - role: tnaglo.unix_home_setup
      vars:
        unix_home_setup_configs:
          - user: tnaglo
```

## License

MIT

## Author Information

Tomasz Naglo (tomasz.naglo.systems)
