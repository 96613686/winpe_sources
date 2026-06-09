# Microsoft.ReportingServices.Library.ChunkStorage::DeleteOneChunk

- ea: `0x61440`
- end: `0x61511`
- name: `Microsoft.ReportingServices.Library.ChunkStorage::DeleteOneChunk`
- size: `209`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5fef0`
- `0x60090`
- `0x62570`
- `0x629c0`

## callees

- `0x61440`

## string_xrefs

- `0x61452`: `### DeleteOneChunk({0},'{1}',{2})`
- `0x6147a`: `DeleteOneChunk`

## pseudocode

```c

```

## disassembly

```asm
0x61440  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61445  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6144a  brfalse.s loc_61479
0x6144c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x61451  ldc.i4.4
0x61452  ldstr    aDeleteonechunk// "### DeleteOneChunk({0},'{1}',{2})"
0x61457  ldc.i4.3
0x61458  newarr   [mscorlib]System.Object
0x6145d  dup
0x6145e  ldc.i4.0
0x6145f  ldarg.1
0x61460  box      [mscorlib]System.Guid
0x61465  stelem.ref
0x61466  dup
0x61467  ldc.i4.1
0x61468  ldarg.3
0x61469  stelem.ref
0x6146a  dup
0x6146b  ldc.i4.2
0x6146c  ldarg.s  4
0x6146e  box      [mscorlib]System.Int32
0x61473  stelem.ref
0x61474  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x61479  ldarg.0
0x6147a  ldstr    aDeleteonechunk_0// "DeleteOneChunk"
0x6147f  ldnull
0x61480  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x61485  stloc.0
0x61486  ldloc.0
0x61487  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6148c  ldstr    aSnapshotid_1// "@SnapshotID"
0x61491  ldc.i4.s 0xE
0x61493  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x61498  ldarg.1
0x61499  box      [mscorlib]System.Guid
0x6149e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x614a3  ldloc.0
0x614a4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x614a9  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x614ae  ldc.i4.2
0x614af  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x614b4  ldarg.2
0x614b5  box      [mscorlib]System.Boolean
0x614ba  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x614bf  ldloc.0
0x614c0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x614c5  ldstr    aChunkname// "@ChunkName"
0x614ca  ldc.i4.s 0xC
0x614cc  ldc.i4   0x104
0x614d1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x614d6  ldarg.3
0x614d7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x614dc  ldloc.0
0x614dd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x614e2  ldstr    aChunktype// "@ChunkType"
0x614e7  ldc.i4.8
0x614e8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x614ed  ldarg.s  4
0x614ef  box      [mscorlib]System.Int32
0x614f4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x614f9  ldloc.0
0x614fa  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x614ff  ldc.i4.0
0x61500  cgt
0x61502  stloc.1
0x61503  leave.s  loc_6150F
0x61505  ldloc.0
0x61506  brfalse.s loc_6150E
0x61508  ldloc.0
0x61509  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6150e  endfinally
0x6150f  ldloc.1
0x61510  ret
```
