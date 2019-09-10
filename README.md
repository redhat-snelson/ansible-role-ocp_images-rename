Role Name
=========

Renames OpenShift Images on the local machine in preparation of pushing images
to an on-premise Container Registry.  

Requirements
------------

Requires Podman to re-tag images.

Role Variables
--------------

The following variables may need to be set, defaults found in `defaults/main/*.yml`:

The Source Registry URL variable is as follow:
    src_registry_url: "registry.redhat.io/"

The Destination Registry URL variable is as follow:
    dest_registry_url: "registry.example.com/"

You should also have three image lists that define the images to download for OpenShift (as YAML)
    docker_image_list_required
    docker_image_list_optional
    docker_image_list_s2i

Dependencies
------------

None

Example Playbook
----------------

- hosts: servers
  roles:
    - role: snelson_redhat.ocp_images.rename
      src_registry_url: "registry.redhat.io/"
      dest_registry_url: "registry.example.com/"

License
-------

MIT / BSD

Author Information
------------------

This role was written in 2019 by Sean Nelson
