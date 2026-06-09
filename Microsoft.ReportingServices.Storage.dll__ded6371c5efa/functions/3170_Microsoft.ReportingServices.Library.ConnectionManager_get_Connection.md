# Microsoft.ReportingServices.Library.ConnectionManager::get_Connection

- ea: `0x3170`
- end: `0x317e`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::get_Connection`
- size: `14`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x11f0`
- `0x17c0`
- `0x21b0`
- `0x31b0`
- `0x35a0`
- `0x3670`
- `0x6a80`

## callees

- `0x3360`

## pseudocode

```c

```

## disassembly

```asm
0x3170  ldarg.0
0x3171  ldc.i4.1
0x3172  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection([opt] bool initializeEncryption)
0x3177  ldarg.0
0x3178  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x317d  ret
```
