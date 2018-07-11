# How to setup

### Build docker image
docker build --tag senz/mongodb .

### Run docker image
```
docker build --tag senz/mongodb .
docker run -d -v /opt/mongodb:/data/db -p 27017:27017 senz/mongodb
```

# Authentication

### mongo without auth

up mongodb without `--auth`
connect mongodb with `mongo`

### create root user

```
use admin
db.createUser({user: "root", pwd: "root", roles:["root"]});
```

### create senz user

```
use senz
db.createUser({user: "senz", pwd: "senz", roles:[{role: "readWrite", db: "senz"}]});
```

### mongo with auth

up mongodb with `--auth`

```
mongo -u root -p root --authenticationDatabase admin
mongo -u senz -p senz --authenticationDatabase senz
```
