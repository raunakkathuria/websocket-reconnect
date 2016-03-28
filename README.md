# websocket-reconnect
Small javascript library that reconnects websocket if connection is closed or dropped. It doesn't override or modify original websocket connection. It just provides mechanism to reconnect when connection is closed.

You need to update following settings as per your need

##### socketUrl 

`socketUrl = "wss://www.sample.com/websockets/"`

##### isJSON (default = 0)

`isJSON = 1`

*set this flag to 1 if you send json data over websocket*


### Usage

You need to write your own on message handler the same way you will do it in your normal websocket script

```
// implement your server response handling here
socket.onmessage = function (msg){
   console.log(msg);
};
```

Now include this file in your scripts, then `ReconnectSocket` object will be available for you

##### Methods

`ReconnectSocket.init() // initiate connection`

or if you don't want to initiate you can just use

`ReconnectSocket.send()` 

this automatically initiates connection if its closed and sends the message, so you don't have to worry about whether connection is closed or not.

`ReconnectSocket.close()`

closes the websocket connection

`ReconnectSocket.clear()`

clear buffer message waiting to be send to server
