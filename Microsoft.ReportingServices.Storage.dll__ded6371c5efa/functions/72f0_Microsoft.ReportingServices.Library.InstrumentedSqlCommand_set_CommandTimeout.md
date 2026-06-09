# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout

- ea: `0x72f0`
- end: `0x72fd`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout`
- size: `13`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`
- `0x17c0`
- `0x20b0`
- `0x35a0`
- `0x6c00`
- `0x6c60`
- `0x6cb0`

## callees

- `0x6f60`

## pseudocode

```c

```

## disassembly

```asm
0x72f0  ldarg.0
0x72f1  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x72f6  ldarg.1
0x72f7  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x72fc  ret
```
