# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery

- ea: `0x70e0`
- end: `0x7107`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery`
- size: `39`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1230`
- `0x17c0`
- `0x1d70`
- `0x20b0`
- `0x2710`
- `0x27a0`
- `0x27f0`
- `0x2860`
- `0x28c0`
- `0x2ba0`
- `0x2be0`
- `0x2c10`
- `0x2c60`
- `0x2d40`
- `0x35a0`
- `0x6240`
- `0x62e0`
- `0x63e0`
- `0x68b0`
- `0x6fa0`

## callees

- `0x6dd0`
- `0x6f60`
- `0x70e0`

## pseudocode

```c

```

## disassembly

```asm
0x70e0  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x70e5  stloc.0
0x70e6  ldarg.0
0x70e7  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x70ec  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x70f1  stloc.1
0x70f2  leave.s  loc_7105
0x70f4  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x70f9  rethrow
0x70fb  ldloc.0
0x70fc  brfalse.s loc_7104
0x70fe  ldloc.0
0x70ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7104  endfinally
0x7105  ldloc.1
0x7106  ret
```
