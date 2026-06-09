# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar

- ea: `0x7190`
- end: `0x71b7`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0x2f40`
- `0x7010`

## callees

- `0x6dd0`
- `0x6f60`
- `0x7190`

## pseudocode

```c

```

## disassembly

```asm
0x7190  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x7195  stloc.0
0x7196  ldarg.0
0x7197  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x719c  callvirt instance object [System.Data]System.Data.Common.DbCommand::ExecuteScalar()
0x71a1  stloc.1
0x71a2  leave.s  loc_71B5
0x71a4  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x71a9  rethrow
0x71ab  ldloc.0
0x71ac  brfalse.s loc_71B4
0x71ae  ldloc.0
0x71af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71b4  endfinally
0x71b5  ldloc.1
0x71b6  ret
```
