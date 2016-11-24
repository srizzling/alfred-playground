# alfred_build

## Usage
First install the necessary prerequisites for this playbook and then
populate the inventory directory with the machines you'd like to
provision.

### Prerequisites
```sh
$ git submodule update --init --recursive
```

### Defining inventory

Here's what I'd do if I wanted to add `webserver.local` to a group of servers
called `webservers`.

```sh
$ ssh-copy-id user@webserver.local # Copy SSH keys over to webserver so
                                   # ansible doesn't prompt you for a
                                   # password when you provision the server.
$ echo "[webservers]\nwebserver.local" > ./inventory/webservers
```

### Provisioning
```sh
$ ansible-playbook --inventory-file=inventory site.yml [--ask-become-pass]
```
A helper script, `deploy.sh` has been provided to run this command for you.

Author: Sriram Venkatesh

Generated using
[generator-ansible](http://github.com/willprice/generator-ansible) with
[Yo](yeoman.io).
