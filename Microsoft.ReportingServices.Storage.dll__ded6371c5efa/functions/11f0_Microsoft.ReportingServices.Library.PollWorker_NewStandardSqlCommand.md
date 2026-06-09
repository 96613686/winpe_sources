# Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand

- ea: `0x11f0`
- end: `0x121a`
- name: `Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1230`
- `0x1d70`

## callees

- `0x2ff0`
- `0x3170`
- `0x3230`
- `0x70c0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x11f0  ldarg.0
0x11f1  ldarg.1
0x11f2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x11f7  ldarg.1
0x11f8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x11fd  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x1202  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command)
0x1207  dup
0x1208  ldc.i4.4
0x1209  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x120e  dup
0x120f  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x1214  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x1219  ret
```
