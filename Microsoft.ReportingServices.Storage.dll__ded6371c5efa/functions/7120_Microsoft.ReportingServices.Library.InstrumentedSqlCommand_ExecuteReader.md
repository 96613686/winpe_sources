# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader

- ea: `0x7120`
- end: `0x714e`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader`
- size: `46`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x20b0`
- `0x2990`
- `0x2ca0`
- `0x2d40`
- `0x61e0`
- `0x6750`
- `0x6970`
- `0x6fe0`
- `0x7110`

## callees

- `0x6dd0`
- `0x6f60`
- `0x7120`
- `0x7490`

## pseudocode

```c

```

## disassembly

```asm
0x7120  ldnull
0x7121  stloc.0
0x7122  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x7127  stloc.1
0x7128  ldarg.0
0x7129  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x712e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::ExecuteReader()
0x7133  stloc.0
0x7134  leave.s  loc_7147
0x7136  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x713b  rethrow
0x713d  ldloc.1
0x713e  brfalse.s loc_7146
0x7140  ldloc.1
0x7141  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7146  endfinally
0x7147  ldloc.0
0x7148  newobj   instance void Microsoft.ReportingServices.Library.HandledSqlDataReader::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader reader)
0x714d  ret
```
