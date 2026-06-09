# Microsoft.ReportingServices.Library.ReportExecutionCacheDb::FlushCache

- ea: `0x658f0`
- end: `0x6592e`
- name: `Microsoft.ReportingServices.Library.ReportExecutionCacheDb::FlushCache`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x314f0`
- `0x399d0`

## callees

- `0x658f0`

## string_xrefs

- `0x65903`: `@Path`
- `0x658f1`: `FlushReportFromCache`

## pseudocode

```c

```

## disassembly

```asm
0x658f0  ldarg.0
0x658f1  ldstr    aFlushreportfro// "FlushReportFromCache"
0x658f6  ldnull
0x658f7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x658fc  stloc.0
0x658fd  ldloc.0
0x658fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65903  ldstr    aPath// "@Path"
0x65908  ldarg.1
0x65909  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6590e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65913  ldc.i4.s 0xC
0x65915  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x6591a  ldloc.0
0x6591b  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x65920  pop
0x65921  leave.s  loc_6592D
0x65923  ldloc.0
0x65924  brfalse.s loc_6592C
0x65926  ldloc.0
0x65927  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6592c  endfinally
0x6592d  ret
```
