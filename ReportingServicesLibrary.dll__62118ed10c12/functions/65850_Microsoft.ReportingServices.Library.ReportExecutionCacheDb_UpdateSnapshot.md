# Microsoft.ReportingServices.Library.ReportExecutionCacheDb::UpdateSnapshot

- ea: `0x65850`
- end: `0x658eb`
- name: `Microsoft.ReportingServices.Library.ReportExecutionCacheDb::UpdateSnapshot`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x17640`

## callees

- `0x637b0`
- `0x65850`

## string_xrefs

- `0x6586f`: `@Path`
- `0x6585d`: `UpdateSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x65850  ldarg.1
0x65851  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x65856  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6585b  stloc.0
0x6585c  ldarg.0
0x6585d  ldstr    aUpdatesnapshot_1// "UpdateSnapshot"
0x65862  ldnull
0x65863  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x65868  stloc.1
0x65869  ldloc.1
0x6586a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6586f  ldstr    aPath// "@Path"
0x65874  ldc.i4.s 0xC
0x65876  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6587b  ldloc.0
0x6587c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x65881  ldloc.1
0x65882  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65887  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x6588c  ldc.i4.s 0xE
0x6588e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x65893  ldarg.s  4
0x65895  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x6589a  box      [mscorlib]System.Guid
0x6589f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x658a4  ldloc.1
0x658a5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x658aa  ldstr    aExecutiondate_0// "@executionDate"
0x658af  ldc.i4.4
0x658b0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x658b5  ldarg.3
0x658b6  box      [mscorlib]System.DateTime
0x658bb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x658c0  ldloc.1
0x658c1  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x658c6  pop
0x658c7  leave.s  loc_658D3
0x658c9  ldloc.1
0x658ca  brfalse.s loc_658D2
0x658cc  ldloc.1
0x658cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x658d2  endfinally
0x658d3  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager::.ctor()
0x658d8  dup
0x658d9  ldarg.0
0x658da  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x658df  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x658e4  ldarg.2
0x658e5  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager::FireSnapShotCreatedEvent(valuetype [mscorlib]System.Guid)
0x658ea  ret
```
