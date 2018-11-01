# ansible-ha-mosquitto

This ansible role installs and configures a [Mosquitto MQTT broker](https://mosquitto.org/). It exposes a server on port 8883 with TLS encryption which can be exposed to the internet, and another on 1883 without encryption intended for use only within your home's network.

What this role doesn't (currently) do is setup MQTT level user credentials.

## Requirements

Really this should work on any debian based system, but has been tested on a Raspberry Pi running Hassbian.

## Role Variables

- `domain_name`
  - Ex. `my_home.duckdns.org`
  - This is the domain name where your pi can be reached from the internet.

## Dependencies

- [ha-letsencrypt](https://github.com/mpataki/ansible-ha-letsencrypt) for SSL. This can be installed via git or via ansible galaxy.

## Example Playbook

```yml
    - hosts: pi
      vars:
        domain_name: my_home.duckdns.org
      roles:
         - role: mpataki.ha-mosquitto
```

## License

MIT
