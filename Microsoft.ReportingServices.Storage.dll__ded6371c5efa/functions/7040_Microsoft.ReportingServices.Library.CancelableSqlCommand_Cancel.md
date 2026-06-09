# Microsoft.ReportingServices.Library.CancelableSqlCommand::Cancel

- ea: `0x7040`
- end: `0x7084`
- name: `Microsoft.ReportingServices.Library.CancelableSqlCommand::Cancel`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6f60`
- `0x7040`
- `0x71c0`

## string_xrefs

- `0x7079`: `CancelableSqlCommand.Cancel not called, connection is not valid`

## pseudocode

```c

```

## disassembly

```asm
0x7040  ldarg.0
0x7041  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x7046  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Connection()
0x704b  brfalse.s loc_7067
0x704d  ldarg.0
0x704e  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x7053  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Connection()
0x7058  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x705d  ldc.i4.1
0x705e  beq.s    loc_7067
0x7060  ldarg.0
0x7061  call     instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Cancel()
0x7066  ret
0x7067  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x706c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x7071  brfalse.s loc_7083
0x7073  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7078  ldc.i4.3
0x7079  ldstr    aCancelablesqlc// "CancelableSqlCommand.Cancel not called,"...
0x707e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7083  ret
```
