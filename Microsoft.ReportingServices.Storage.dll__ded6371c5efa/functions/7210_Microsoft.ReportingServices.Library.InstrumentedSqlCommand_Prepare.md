# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Prepare

- ea: `0x7210`
- end: `0x7235`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Prepare`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6dd0`
- `0x6f60`
- `0x7210`

## pseudocode

```c

```

## disassembly

```asm
0x7210  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x7215  stloc.0
0x7216  ldarg.0
0x7217  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::get_Command()
0x721c  callvirt instance void [System.Data]System.Data.Common.DbCommand::Prepare()
0x7221  leave.s  loc_7234
0x7223  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x7228  rethrow
0x722a  ldloc.0
0x722b  brfalse.s loc_7233
0x722d  ldloc.0
0x722e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7233  endfinally
0x7234  ret
```
