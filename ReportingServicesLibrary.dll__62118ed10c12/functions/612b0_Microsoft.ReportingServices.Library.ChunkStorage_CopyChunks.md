# Microsoft.ReportingServices.Library.ChunkStorage::CopyChunks

- ea: `0x612b0`
- end: `0x613dc`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::CopyChunks`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5fb80`
- `0x5fc20`
- `0x61260`

## callees

- `0x612b0`

## string_xrefs

- `0x612c2`: `### CopyChunks ({0}, {1})`
- `0x612e5`: `CopyChunksOfType`

## pseudocode

```c

```

## disassembly

```asm
0x612b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x612b5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x612ba  brfalse.s loc_612E4
0x612bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x612c1  ldc.i4.4
0x612c2  ldstr    aCopychunks01// "### CopyChunks ({0}, {1})"
0x612c7  ldc.i4.2
0x612c8  newarr   [mscorlib]System.Object
0x612cd  dup
0x612ce  ldc.i4.0
0x612cf  ldarg.1
0x612d0  box      [mscorlib]System.Guid
0x612d5  stelem.ref
0x612d6  dup
0x612d7  ldc.i4.1
0x612d8  ldarg.3
0x612d9  box      [mscorlib]System.Guid
0x612de  stelem.ref
0x612df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x612e4  ldarg.0
0x612e5  ldstr    aCopychunksofty// "CopyChunksOfType"
0x612ea  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x612ef  stloc.0
0x612f0  ldloc.0
0x612f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x612f6  ldstr    aFromsnapshotid// "@FromSnapshotID"
0x612fb  ldc.i4.s 0xE
0x612fd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61302  ldarg.1
0x61303  box      [mscorlib]System.Guid
0x61308  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6130d  ldloc.0
0x6130e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61313  ldstr    aFromispermanen// "@FromIsPermanent"
0x61318  ldc.i4.2
0x61319  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6131e  ldarg.2
0x6131f  box      [mscorlib]System.Boolean
0x61324  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61329  ldloc.0
0x6132a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6132f  ldstr    aTosnapshotid// "@ToSnapshotID"
0x61334  ldc.i4.s 0xE
0x61336  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6133b  ldarg.3
0x6133c  box      [mscorlib]System.Guid
0x61341  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61346  ldloc.0
0x61347  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6134c  ldstr    aToispermanent// "@ToIsPermanent"
0x61351  ldc.i4.2
0x61352  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61357  ldarg.s  4
0x61359  box      [mscorlib]System.Boolean
0x6135e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x61363  ldarga.s 5
0x61365  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x6136a  brfalse.s loc_6138E
0x6136c  ldloc.0
0x6136d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61372  ldstr    aChunktype// "@ChunkType"
0x61377  ldc.i4.8
0x61378  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6137d  ldarga.s 5
0x6137f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x61384  box      [mscorlib]System.Int32
0x61389  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6138e  ldarg.s  6
0x61390  brfalse.s loc_613AB
0x61392  ldloc.0
0x61393  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x61398  ldstr    aChunkname// "@ChunkName"
0x6139d  ldc.i4.s 0xC
0x6139f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x613a4  ldarg.s  6
0x613a6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x613ab  ldarg.s  7
0x613ad  brfalse.s loc_613C8
0x613af  ldloc.0
0x613b0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x613b5  ldstr    aTargetchunknam// "@TargetChunkName"
0x613ba  ldc.i4.s 0xC
0x613bc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x613c1  ldarg.s  7
0x613c3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x613c8  ldloc.0
0x613c9  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x613ce  pop
0x613cf  leave.s  loc_613DB
0x613d1  ldloc.0
0x613d2  brfalse.s loc_613DA
0x613d4  ldloc.0
0x613d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x613da  endfinally
0x613db  ret
```
