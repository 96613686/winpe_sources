# Microsoft.ReportingServices.Library.CatalogQuery::Commit

- ea: `0x2240`
- end: `0x225c`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::Commit`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2290`
- `0x2420`

## callees

- `0x21f0`
- `0x2240`
- `0x3710`

## pseudocode

```c

```

## disassembly

```asm
0x2240  ldarg.0
0x2241  call     instance bool Microsoft.ReportingServices.Library.CatalogQuery::get_AllowCommit()
0x2246  brfalse.s loc_225B
0x2248  ldarg.0
0x2249  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x224e  brfalse.s loc_225B
0x2250  ldarg.0
0x2251  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x2256  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x225b  ret
```
