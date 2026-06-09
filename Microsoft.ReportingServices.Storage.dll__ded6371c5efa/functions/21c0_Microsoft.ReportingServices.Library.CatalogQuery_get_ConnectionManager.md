# Microsoft.ReportingServices.Library.CatalogQuery::get_ConnectionManager

- ea: `0x21c0`
- end: `0x21ed`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::get_ConnectionManager`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x21b0`

## callees

- `0x21c0`
- `0x3060`
- `0x32e0`

## pseudocode

```c

```

## disassembly

```asm
0x21c0  ldarg.0
0x21c1  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x21c6  brtrue.s loc_21E6
0x21c8  ldarg.0
0x21c9  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x21ce  stfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x21d3  ldarg.0
0x21d4  ldfld    bool Microsoft.ReportingServices.Library.CatalogQuery::m_willClose
0x21d9  brfalse.s loc_21E6
0x21db  ldarg.0
0x21dc  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x21e1  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x21e6  ldarg.0
0x21e7  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x21ec  ret
```
