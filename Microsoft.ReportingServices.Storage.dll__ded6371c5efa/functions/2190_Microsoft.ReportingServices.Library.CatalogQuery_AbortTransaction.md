# Microsoft.ReportingServices.Library.CatalogQuery::AbortTransaction

- ea: `0x2190`
- end: `0x21ac`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::AbortTransaction`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x20b0`
- `0x2290`
- `0x2420`

## callees

- `0x2190`
- `0x21f0`
- `0x37f0`

## pseudocode

```c

```

## disassembly

```asm
0x2190  ldarg.0
0x2191  call     instance bool Microsoft.ReportingServices.Library.CatalogQuery::get_AllowCommit()
0x2196  brfalse.s loc_21AB
0x2198  ldarg.0
0x2199  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x219e  brfalse.s loc_21AB
0x21a0  ldarg.0
0x21a1  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x21a6  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x21ab  ret
```
