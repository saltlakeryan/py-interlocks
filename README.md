Python Interlocks Controller
===

This project acts as a middle man between a server like OpenCoral and the Utah Nanofab
interlock boxes.

Prerequisite:
---
Requires flask and rocket (pip install flask, pip install rocket)

Usage:
---
You can start a fake interlock box for testing by running:

    python fakeInterlockBox.py  #will listen on port 2101

Then run the service as:

    python app.py 127.0.0.1 55009 mySecretPassword

where 127.0.0.1 is the IP address of the lock box and 55009 is the port for the service
to listen on for commands.


API:
---
The service responds to POST commands to control the box.  Example:

    curl -H 'Accept: application/json' -X POST -u admin:mySecretPassword http://localhost:55009/sense
    curl -H 'Accept: application/json' -X POST -u admin:mySecretPassword http://localhost:55009/enable
    curl -H 'Accept: application/json' -X POST -u admin:mySecretPassword http://localhost:55009/disable


API Documentation:
---
The swagger.yaml file uses the swagger standard for documenting REST APIs.  
Served up on http://localhost:55009/swagger.yaml (or configured port).


Browser Access:
---
Open browser to http://localhost:55009/admin

