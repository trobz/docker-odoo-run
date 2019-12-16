# Odoo 13 docker images

## Usage

### Configuration

Clone this repo:

  $ git clone https://github.com/trobz/docker-odoo-run

Make sure you have docker and docker-compose installed:

  $ sudo pip install docker-compose

### Start odoo

  $  docker-compose up

### Create a database

- Open `http://localhost:8069` in your browser
- Create database:
  - Choose name `odoo13` as a start for example
  - Check the option for `Demo data`

### Stop/Restart odoo

- Press `Ctrl-c`
- `$ docker-compose up` again

## A few things to know

### Adding/modifying custom addons

- Add your modules in folder `./addons`
- Restart Odoo
- Open Odoo in debug mode (append to the url `?debug=1`: `http://localhost:8069/web?debug=1`)
- Use `Apps > Update Apps List` to take new modules into account
- Use `Apps` Upgrade action on the modules that you modified

### Get into the odoo container

  $ docker exec -it odoo bash

###  Use pgadmin

- Open `http://localhost:8082` in your browser, log in by the following information
  - Email Address: pgadmin
  - Password: pgadmin
- Connect to pg server, by clicking on `Servers > Create > Server` and filling in these parameters:
  - Host: db
  - Port: 5432
  - Username: odoo
  - Password: odoo