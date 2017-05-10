# soulshake.net

This stack contains the bits and pieces needed to deploy several of my personal projects:

- cv.soulshake.net
- blog.soulshake.net
- www.soulshake.net

## Clone the meta-repo

    $ git clone git@github.com:soulshake/soulshake.net.git && cd soulshake.net
    $ git submodule update --init --recursive

## Deploy a local Docker registry

    $ docker stack deploy registry --compose-file stacks/registry.yml

## Deploy the services

    $ docker-compose -f stacks/soulshake.net.yml build
    $ docker-compose -f stacks/soulshake.net.yml push
    $ docker stack deploy soulshake --compose-file stacks/soulshake.net.yml 
