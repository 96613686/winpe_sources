# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType

- ea: `0x7310`
- end: `0x731d`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType`
- size: `13`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`
- `0x17c0`
- `0x20b0`
- `0x2580`
- `0x35a0`
- `0x6970`
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
0x7310  ldarg.0
0x7311  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x7316  ldarg.1
0x7317  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x731c  ret
```
