
memwatch

websocket 模块
内存泄露问题：
server端 code：
var WebSocketServer = require(‘ws’).Server;
var m = require(“memwatch”)
var wss = new WebSocketServer({
port: 8101
});
setInterval(function (argument) {
var mem = process.memoryUsage();
console.log(‘clients’+wss.clients.length+‘rss:’, Math.round((mem.rss / 1024/1024)) + “MB”);
},5000)

wss.on(‘connection’, function(ws) {
	 ws.on(“close”,function(err){

 })


