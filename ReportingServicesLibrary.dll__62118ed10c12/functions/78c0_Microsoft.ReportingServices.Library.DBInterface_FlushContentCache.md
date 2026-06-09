# Microsoft.ReportingServices.Library.DBInterface::FlushContentCache

- ea: `0x78c0`
- end: `0x7925`
- name: `Microsoft.ReportingServices.Library.DBInterface::FlushContentCache`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x78c0`

## string_xrefs

- `0x78d5`: `@Path`
- `0x78c3`: `FlushContentCache`
- `0x790d`: `Error in FlushContentCache: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x78c0  ldc.i4.0
0x78c1  stloc.0
0x78c2  ldarg.0
0x78c3  ldstr    aFlushcontentca// "FlushContentCache"
0x78c8  ldnull
0x78c9  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x78ce  stloc.1
0x78cf  ldloc.1
0x78d0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x78d5  ldstr    aPath// "@Path"
0x78da  ldc.i4.s 0x16
0x78dc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x78e1  ldarg.1
0x78e2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x78e7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x78ec  ldloc.1
0x78ed  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x78f2  unbox.any [mscorlib]System.Int32
0x78f7  stloc.0
0x78f8  leave.s  loc_7904
0x78fa  ldloc.1
0x78fb  brfalse.s loc_7903
0x78fd  ldloc.1
0x78fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7903  endfinally
0x7904  leave.s  loc_7923
0x7906  stloc.2
0x7907  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x790c  ldc.i4.1
0x790d  ldstr    aErrorInFlushco// "Error in FlushContentCache: {0}"
0x7912  ldc.i4.1
0x7913  newarr   [mscorlib]System.Object
0x7918  dup
0x7919  ldc.i4.0
0x791a  ldloc.2
0x791b  stelem.ref
0x791c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7921  rethrow
0x7923  ldloc.0
0x7924  ret
```
