# Microsoft.ReportingServices.Library.CatalogQuery::get_Transaction

- ea: `0x2210`
- end: `0x2234`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::get_Transaction`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x20b0`

## callees

- `0x2210`
- `0x3230`
- `0x3700`

## pseudocode

```c

```

## disassembly

```asm
0x2210  ldarg.0
0x2211  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x2216  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x221b  brtrue.s loc_2228
0x221d  ldarg.0
0x221e  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x2223  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0x2228  ldarg.0
0x2229  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x222e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x2233  ret
```
