# Microsoft.ReportingServices.Library.Storage::get_Connection

- ea: `0x6a80`
- end: `0x6a8c`
- name: `Microsoft.ReportingServices.Library.Storage::get_Connection`
- size: `12`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6140`
- `0x6bb0`
- `0x6c00`
- `0x6c60`

## callees

- `0x3170`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6a86  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x6a8b  ret
```
