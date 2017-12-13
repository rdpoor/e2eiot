# e2esf
End-to-end Internet of Things Framework, from sensor to smartphone

## Goal

Create a basic framework to facilitate communication between remote devices and
web browsers, tablets and smart phones.

## Design Notes

[remote instrument] <-- RabbitMQ --> [AWS App/Web Server] <-- HTTP --> [Browser]

Assume remote instrument (or sensor hub) is "unix-like".  The remote instrument
will contact a well known address with a request for connection (AWS server).
If and when honored, instrument and server will communicate using RabbitMQ over
a secure link.

The server will maintain a cached image of instrument state.  The cache will be
updated via pushes from the instrument or pulls from the server as appropriate.

The server provides a web interface allow users to interact with the instrument
using HTTP and/or AJAX protocols.  Initially, the interface will be a responsive
browser such as bootstrap to speed development, but device specific support (iOS
and Adroid) may be provided thereafter.

## Toolbox

The following packages, languages, documentation, apps and APIs may be useful in
the development of e2esf:

* [RabbitMQ](https://www.rabbitmq.com/download.html)
* [Node.js](https://nodejs.org/en/)
