# Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction

- ea: `0x3230`
- end: `0x3237`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x11f0`
- `0x2210`
- `0x6750`
- `0x6aa0`

## pseudocode

```c

```

## disassembly

```asm
0x3230  ldarg.0
0x3231  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3236  ret
```
