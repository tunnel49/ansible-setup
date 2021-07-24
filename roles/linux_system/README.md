# xorg

## Requirements

Expects a baseline configuration on the client with python, pip and sshd installed
Needs to be run with become privileges

## Role Variables

### Accepts
- x11_restart_on reconfiguration: <bool|false>
- github_user: <github user with access to the monolisa repo>
- github_token: <token to said account>
- font_preference:
	- for: <font family>
		use: <font>
- xorg_conf_d_files: <path of files to copy to xorg.conf.d>
		
## Dependencies

collections:
- name: tunnel49.util
  source: https://github.com/tunnel49/tunnel49.util.git
  type: git
  version: >0.1.0

## Example Playbook

- name: "import xorg"
	import_role:
		name: xorg
	vars:
		xorg_conf_d_files: >-
			"{{ host_files }}/etc/X11/xorg.conf.d/"

## License

Creative Commons Zero v1.0 Universal
(see LICENSE)
	
## Author Information

author: Pontus Lundgren
webpage: https://www.github.com/tunnel49
