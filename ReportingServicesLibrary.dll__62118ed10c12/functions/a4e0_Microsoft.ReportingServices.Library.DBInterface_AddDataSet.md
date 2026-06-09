# Microsoft.ReportingServices.Library.DBInterface::AddDataSet

- ea: `0xa4e0`
- end: `0xa639`
- name: `Microsoft.ReportingServices.Library.DBInterface::AddDataSet`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4630`
- `0xa4e0`

## string_xrefs

- `0xa599`: `@LinkID`
- `0xa5ba`: `@LinkPath`
- `0xa5f7`: `DBInterface.AddDataSet - read something when not expected to read`

## pseudocode

```c

```

## disassembly

```asm
0xa4e0  ldarg.s  5
0xa4e2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa4e7  stobj    [mscorlib]System.Guid
0xa4ec  ldarg.s  6
0xa4ee  ldnull
0xa4ef  stind.ref
0xa4f0  ldarg.0
0xa4f1  ldstr    aAdddataset// "AddDataSet"
0xa4f6  ldnull
0xa4f7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0xa4fc  stloc.0
0xa4fd  ldloc.0
0xa4fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0xa503  ldstr    aAuthtype// "@AuthType"
0xa508  ldarg.0
0xa509  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0xa50e  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0xa513  box      [mscorlib]System.Int32
0xa518  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa51d  pop
0xa51e  ldloc.0
0xa51f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0xa524  ldstr    aId_1// "@ID"
0xa529  ldarg.2
0xa52a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_ID()
0xa52f  box      [mscorlib]System.Guid
0xa534  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa539  pop
0xa53a  ldarg.s  4
0xa53c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa541  brtrue.s loc_A556
0xa543  ldloc.0
0xa544  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0xa549  ldstr    aEditsessionid// "@EditSessionID"
0xa54e  ldarg.s  4
0xa550  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa555  pop
0xa556  ldloc.0
0xa557  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0xa55c  ldstr    aItemid_0// "@ItemID"
0xa561  ldarg.1
0xa562  box      [mscorlib]System.Guid
0xa567  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa56c  pop
0xa56d  ldloc.0
0xa56e  ldstr    aName_0// "@Name"
0xa573  ldc.i4.s 0xC
0xa575  ldarg.2
0xa576  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_DataSetName()
0xa57b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0xa580  pop
0xa581  ldarg.2
0xa582  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_LinkedSharedDataSetID()
0xa587  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa58c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa591  brfalse.s loc_A5B1
0xa593  ldloc.0
0xa594  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0xa599  ldstr    aLinkid// "@LinkID"
0xa59e  ldarg.2
0xa59f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_LinkedSharedDataSetID()
0xa5a4  box      [mscorlib]System.Guid
0xa5a9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa5ae  pop
0xa5af  br.s     loc_A5D3
0xa5b1  ldarg.2
0xa5b2  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_AbsolutePath()
0xa5b7  brfalse.s loc_A5D3
0xa5b9  ldloc.0
0xa5ba  ldstr    aLinkpath// "@LinkPath"
0xa5bf  ldc.i4.s 0xC
0xa5c1  ldarg.3
0xa5c2  ldarg.2
0xa5c3  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_AbsolutePath()
0xa5c8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0xa5cd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0xa5d2  pop
0xa5d3  ldloc.0
0xa5d4  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0xa5d9  stloc.1
0xa5da  ldloc.1
0xa5db  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa5e0  brfalse.s loc_A622
0xa5e2  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xa5e7  ldarg.2
0xa5e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::get_LinkedSharedDataSetID()
0xa5ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa5f2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa5f7  ldstr    aDbinterfaceAdd_1// "DBInterface.AddDataSet - read something"...
0xa5fc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xa601  ldarg.s  5
0xa603  ldloc.1
0xa604  ldc.i4.0
0xa605  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0xa60a  stobj    [mscorlib]System.Guid
0xa60f  ldloc.1
0xa610  ldc.i4.1
0xa611  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xa616  brtrue.s loc_A622
0xa618  ldarg.s  6
0xa61a  ldloc.1
0xa61b  ldc.i4.1
0xa61c  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0xa621  stind.ref
0xa622  leave.s  loc_A638
0xa624  ldloc.1
0xa625  brfalse.s loc_A62D
0xa627  ldloc.1
0xa628  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa62d  endfinally
0xa62e  ldloc.0
0xa62f  brfalse.s loc_A637
0xa631  ldloc.0
0xa632  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa637  endfinally
0xa638  ret
```
