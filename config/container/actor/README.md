# LVM container for actors - to rule them all¹

- Needs some enviroment variables in the kube files or as container -e parameters
- Supports two modes.
  - running only with pypi installed packages (code & config) from container build.
  - in debug mode with mounted host file system develop directories.

### LVM_ACTOR - name your actor
Its mandatory to provide the actor python module name, it will start with default config of the same name from YOUR_ACTOR/etc/YOUR_ACTOR.yml or in debug mode from python/YOUR_ACTOR/etc/YOUR_ACTOR.yml.

### LVM_RMQ_HOST: hostname for rabbitmq
Replaces the usual rmq localhost host address with $LVM_RMQ_HOST

    actor:
       ...
       host: localhost
       ...

### LVM_ACTOR_CONFIG
Name the config file (without '.yml'), if it is not named as the actor python module name.

### LVM_ACTOR_ARGS
Add some options to actor startup, eg --verbose or --simulate

### LVM_DEBUG=yes
In debug mode the local file system with the python modules and config has to be mapped into the container on runtime.
Either only the actor module or a directory lvm with several python modules.

# TODO

# NOTES

¹ Except lvmtan & lvmpwi
