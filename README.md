# GRPC example


Create file datafiles/transaction.proto and define the message and method

Generate go files with following command

```
rotoc --go_out=. --go_opt=paths=source_relative \
    --go-grpc_out=. --go-grpc_opt=paths=source_relative \
    datafiles/transaction.proto 
```

Implement the server, the server should embed the UnimplementedMoneyTransactionServer like that 

```
type server struct {
	pb.UnimplementedMoneyTransactionServer
}
```

Implement the client