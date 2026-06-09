# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Cancel

- ea: `0x71c0`
- end: `0x71e5`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Cancel`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x7040`

## callees

- `0x6dd0`
- `0x6f60`
- `0x71c0`

## pseudocode

```c

```

## disassembly

```asm
0x71c0  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x71c5  stloc.0
0x71c6  ldarg.0
0x71c7  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x71cc  callvirt instance void [System.Data]System.Data.Common.DbCommand::Cancel()
0x71d1  leave.s  loc_71E4
0x71d3  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x71d8  rethrow
0x71da  ldloc.0
0x71db  brfalse.s loc_71E3
0x71dd  ldloc.0
0x71de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71e3  endfinally
0x71e4  ret
```
