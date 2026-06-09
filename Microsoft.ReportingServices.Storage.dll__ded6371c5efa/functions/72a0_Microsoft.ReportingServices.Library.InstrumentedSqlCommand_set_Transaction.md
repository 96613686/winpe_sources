# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Transaction

- ea: `0x72a0`
- end: `0x72b2`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Transaction`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x20b0`
- `0x6750`

## callees

- `0x6f60`

## pseudocode

```c

```

## disassembly

```asm
0x72a0  ldarg.0
0x72a1  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x72a6  ldarg.1
0x72a7  castclass [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction
0x72ac  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::set_Transaction(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x72b1  ret
```
