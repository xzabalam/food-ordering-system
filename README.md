# Para crear el grafico que permite ver las dependencias

Se debe ejecutar el siguiente comando:

```bash
mvn com.github.ferstl:depgraph-maven-plugin:aggregate -DcreateImage=true -DreduceEdges=false -Dscope=compile "-Dincludes=com.food.ordering.system*:*"
```

Como resultado se verá la siguiente imagen
![dependency-graph.png](docs%2Fimages%2Fdependency-graph.png)


# Domain Ports
1. Input ports are the interfaces that's implemented in the domain layer and used by the clients of the domain layer.
1.1. OrderApplication Service. That will be used by the client of this application, like the postmant calls that I 
   will make to initiate an order. 
1.2. PaymentResponseMessageListener and RestaurantApprovalResponseMessageListener are messages listeners for payment 
   and restaurant approvals.  This domain event listeners are special types of application services and they 
   triggered by domain events, not by the clients.
2. Output ports are the interfaces that's implemented in the infrastructure layers like data access or messaging 
   modules and used by the domain layer to reach to those infrastructure layers.

