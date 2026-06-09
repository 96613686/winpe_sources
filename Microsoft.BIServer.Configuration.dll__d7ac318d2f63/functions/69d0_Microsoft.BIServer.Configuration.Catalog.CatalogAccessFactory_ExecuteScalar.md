# Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::ExecuteScalar

- ea: `0x69d0`
- end: `0x69ed`
- name: `Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::ExecuteScalar`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x67f0`
- `0x69d0`

## pseudocode

```c

```

## disassembly

```asm
0x69d0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x69d5  stloc.0
0x69d6  ldloc.0
0x69d7  ldarg.0
0x69d8  ldarg.1
0x69d9  callvirt T0x2B00003C
0x69de  stloc.1
0x69df  leave.s  loc_69EB
0x69e1  ldloc.0
0x69e2  brfalse.s loc_69EA
0x69e4  ldloc.0
0x69e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69ea  endfinally
0x69eb  ldloc.1
0x69ec  ret
```
