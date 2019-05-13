# grpc_tutorial
[Tutorial] How to develop Go gRPC microservice with HTTP/REST endpoint, middleware, Kubernetes deployment, etc.

Start terminal to build and run gRPC server (replace parameters according to your SQL database server):

```
cd cmd/server
go build .
server.exe -grpc-port=9090 -db-host=<HOST>:3306 -db-user=<USER> -db-password=<PASSWORD> -db-schema=<SCHEMA>
```
If we see:
```
2018/09/09 08:02:16 starting gRPC server...
```
It means server is started.

Open another terminal to build and run gRPC client:
```
cd cmd/client-grpc
go build .
client-grpc.exe -server=localhost:9090
```
If we see something like this:
```
2018/09/09 09:16:01 Create result: <api:"v1" id:13 >
2018/09/09 09:16:01 Read result: <api:"v1" toDo:<id:13 title:"title (2018-09-09T06:16:01.5755011Z)" description:"description (2018-09-09T06:16:01.5755011Z)" reminder:<seconds:1536473762 > > >
2018/09/09 09:16:01 Update result: <api:"v1" updated:1 >
2018/09/09 09:16:01 ReadAll result: <api:"v1" toDos:<id:9 title:"title (2018-09-09T04:45:16.3693282Z)" description:"description (2018-09-09T04:45:16.3693282Z)" reminder:<seconds:1536468316 > > toDos:<id:10 title:"title (2018-09-09T04:46:00.7490565Z)" description:"description (2018-09-09T04:46:00.7490565Z)" reminder:<seconds:1536468362 > > toDos:<id:13 title:"title (2018-09-09T06:16:01.5755011Z)" description:"description (2018-09-09T06:16:01.5755011Z) + updated" reminder:<seconds:1536473762 > > >
2018/09/09 09:16:01 Delete result: <api:"v1" deleted:1 >
```
Everything works fine.
