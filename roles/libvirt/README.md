# Ansible Role - radiorabe.foreman-libvirt.libvirt

Install libvirtd, enable and start libvirtd and create default storage pool using [`ansible.builtin.package`](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/package_module.html), [`ansible.builtin.systemd_service`](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/systemd_service_module.html) and [`ansible.builtin.template`](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html).

## Requirements

Destination host needs to be able to download and install libvirt package from repository.

## Role Variables

| Variable | Default | Description |
| -------- | ------- | ----------- |
| `libvirt_storage_pool_path` | `/var/lib/libvirt/images/` | libvirt directory storage pool path. |
| `libvirt_storage_pool_name` | `default` | libvirt directory storage pool name. |
| `libvirt_libvirt_package_name` | `libvirt` | libvirt package name from repository. |
| `libvirt_libvirt_service_name` | `libvirtd` | libvirt service name. |

## Dependencies

None

## Example Playbook

```yaml
- hosts: all
  roles:
    - libvirt
      vars:
        libvirt_storage_pool_path: /var/lib/libvirt/images/
        libvirt_storage_pool_name: default
        libvirt_libvirt_package_name: libvirt
        libvirt_libvirt_service_name: libvirtd
```

## License

This role is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, version 3 of the License.
