# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Connection

- ea: `0x7270`
- end: `0x7282`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Connection`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x20b0`

## callees

- `0x6f60`

## pseudocode

```c

```

## disassembly

```asm
0x7270  ldarg.0
0x7271  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x7276  ldarg.1
0x7277  castclass [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection
0x727c  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::set_Connection(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x7281  ret
```
