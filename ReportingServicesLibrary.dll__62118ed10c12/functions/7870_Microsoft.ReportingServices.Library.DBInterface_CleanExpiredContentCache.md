# Microsoft.ReportingServices.Library.DBInterface::CleanExpiredContentCache

- ea: `0x7870`
- end: `0x78b8`
- name: `Microsoft.ReportingServices.Library.DBInterface::CleanExpiredContentCache`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb60`

## callees

- `0x7870`

## string_xrefs

- `0x7873`: `CleanExpiredContentCache`
- `0x78a0`: `Error in CleanExpiredContentCache: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7870  ldc.i4.0
0x7871  stloc.0
0x7872  ldarg.0
0x7873  ldstr    aCleanexpiredco// "CleanExpiredContentCache"
0x7878  ldnull
0x7879  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x787e  stloc.1
0x787f  ldloc.1
0x7880  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x7885  unbox.any [mscorlib]System.Int32
0x788a  stloc.0
0x788b  leave.s  loc_7897
0x788d  ldloc.1
0x788e  brfalse.s loc_7896
0x7890  ldloc.1
0x7891  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7896  endfinally
0x7897  leave.s  loc_78B6
0x7899  stloc.2
0x789a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x789f  ldc.i4.1
0x78a0  ldstr    aErrorInCleanex// "Error in CleanExpiredContentCache: {0}"
0x78a5  ldc.i4.1
0x78a6  newarr   [mscorlib]System.Object
0x78ab  dup
0x78ac  ldc.i4.0
0x78ad  ldloc.2
0x78ae  stelem.ref
0x78af  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x78b4  rethrow
0x78b6  ldloc.0
0x78b7  ret
```
