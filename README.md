# stream-stock-exchange
A Streaming Application to build data streaming pipelines from HTTP sources and save the contents to a database tables. We will first run these as standalone **Java 8** applications, then run as **Spring Cloud Stream** applications, and finally show how to orchestrate the same pipeline with **Spring Cloud Data Flow**.

## Usage
**Step 1** Download now avalable stocks and warrants names.
1.1) Run *CommonLookupDownloader* class to load list of current stocks symbols :
```shell
java -cp stream-stock-exchange.jar CommonLookupDownloader
```
1.2) Run *WarrantLookupDownloader* class to load list of current stocks symbols :
```shell
java -cp stream-stock-exchange.jar WarrantLookupDownloader
```
**Step 2** Download HTML files of stocks and warrants symbols
2.1) Run *CommonStockDownloader* class to save HTML contents according to list of stocks from 1.1) :
```shell
java -cp stream-stock-exchange.jar CommonStockDownloader
```
2.2) Run *WarrantStockDownloader* class to save HTML contents according to list of warrants from 1.2) :
```shell
java -cp stream-stock-exchange.jar WarrantStockDownloader
```
**Step 3** Transform HTML contents and persist to relational database as JDBC driver configuration. Run *JDBCPersistor* class :
```shell
java -cp stream-stock-exchange.jar JDBCPersistor
```