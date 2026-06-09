# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader_0

- ea: `0x7160`
- end: `0x718f`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader_0`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6fd0`
- `0x7150`

## callees

- `0x6dd0`
- `0x6f60`
- `0x7160`
- `0x7490`

## pseudocode

```c

```

## disassembly

```asm
0x7160  ldnull
0x7161  stloc.0
0x7162  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x7167  stloc.1
0x7168  ldarg.0
0x7169  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x716e  ldarg.1
0x716f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::ExecuteReader(valuetype [System.Data]System.Data.CommandBehavior)
0x7174  stloc.0
0x7175  leave.s  loc_7188
0x7177  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x717c  rethrow
0x717e  ldloc.1
0x717f  brfalse.s loc_7187
0x7181  ldloc.1
0x7182  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7187  endfinally
0x7188  ldloc.0
0x7189  newobj   instance void Microsoft.ReportingServices.Library.HandledSqlDataReader::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader reader)
0x718e  ret
```
