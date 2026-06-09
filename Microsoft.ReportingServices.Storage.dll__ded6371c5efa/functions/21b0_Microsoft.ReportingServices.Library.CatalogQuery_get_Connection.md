# Microsoft.ReportingServices.Library.CatalogQuery::get_Connection

- ea: `0x21b0`
- end: `0x21bc`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::get_Connection`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x20b0`

## callees

- `0x21c0`
- `0x3170`

## pseudocode

```c

```

## disassembly

```asm
0x21b0  ldarg.0
0x21b1  call     instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::get_ConnectionManager()
0x21b6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x21bb  ret
```
