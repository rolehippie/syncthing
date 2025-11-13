# syncthing

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/syncthing)
[![General Workflow](https://github.com/rolehippie/syncthing/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/syncthing/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/syncthing/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/syncthing/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/syncthing/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/syncthing/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/syncthing)](https://github.com/rolehippie/syncthing/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.syncthing-blue)](https://galaxy.ansible.com/rolehippie/syncthing)

Ansible role to install and configure syncthing.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of contents

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [syncthing_arch](#syncthing_arch)
  - [syncthing_extra_users](#syncthing_extra_users)
  - [syncthing_general_users](#syncthing_general_users)
  - [syncthing_keyring](#syncthing_keyring)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### syncthing_arch

Architecture for syncthing repo

#### Default value

```YAML
syncthing_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' or ansible_architecture
  == 'arm64' else 'amd64' }}"
```

### syncthing_extra_users

List of extra users to configure

#### Default value

```YAML
syncthing_extra_users: []
```

#### Example usage

```YAML
syncthing_extra_users:
  - username: hans
    config:
      device:
        '@introducer': true
        autoAcceptFolders: true
      gui:
        address: 0.0.0.0:8384
  - username: foobar
    home: /var/lib/foobar
```

### syncthing_general_users

List of general users to configure

#### Default value

```YAML
syncthing_general_users: []
```

#### Example usage

```YAML
syncthing_general_users:
  - username: hans
    config:
      device:
        '@introducer': true
        autoAcceptFolders: true
      gui:
        address: 0.0.0.0:8384
  - username: foobar
    home: /var/lib/foobar
```

### syncthing_keyring

Path for the repository keyring

#### Default value

```YAML
syncthing_keyring: /usr/share/keyrings/syncthing-archive-keyring.gpg
```

## Discovered Tags

**_syncthing_**

## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
