# Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewTransaction

- ea: `0x6880`
- end: `0x688c`
- name: `Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x67f0`
- `0x6890`

## pseudocode

```c

```

## disassembly

```asm
0x6880  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x6885  ldarg.0
0x6886  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewTransaction(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection connection, string name)
0x688b  ret
```
