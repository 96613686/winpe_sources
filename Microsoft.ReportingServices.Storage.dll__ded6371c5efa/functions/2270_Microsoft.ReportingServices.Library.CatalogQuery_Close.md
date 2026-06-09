# Microsoft.ReportingServices.Library.CatalogQuery::Close

- ea: `0x2270`
- end: `0x2284`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::Close`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2290`
- `0x2420`

## callees

- `0x2270`
- `0x32f0`

## pseudocode

```c

```

## disassembly

```asm
0x2270  ldarg.0
0x2271  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x2276  brfalse.s loc_2283
0x2278  ldarg.0
0x2279  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.CatalogQuery::m_connManager
0x227e  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x2283  ret
```
