# Microsoft.ReportingServices.Library.DBInterface::AddDataSource

- ea: `0x9a60`
- end: `0x9da8`
- name: `Microsoft.ReportingServices.Library.DBInterface::AddDataSource`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x9a60`

## string_xrefs

- `0x9aa8`: `@DSID`
- `0x9b61`: `@LinkID`
- `0x9b80`: `@LinkPath`
- `0x9c0e`: `@Extension`
- `0x9d42`: `DBInterface.AddDataSource - read something when not expected to read`
- `0x9d87`: `DBInterface.AddDataSource - expected to read something but got nothing`

## pseudocode

```c

```

## disassembly

```asm
0x9a60  ldarg.s  6
0x9a62  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9a67  stobj    [mscorlib]System.Guid
0x9a6c  ldarg.s  7
0x9a6e  ldc.i4.0
0x9a6f  stind.i4
0x9a70  ldarg.s  8
0x9a72  ldnull
0x9a73  stind.ref
0x9a74  ldarg.0
0x9a75  ldstr    aAdddatasource// "AddDataSource"
0x9a7a  ldnull
0x9a7b  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x9a80  stloc.0
0x9a81  ldloc.0
0x9a82  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9a87  ldstr    aAuthtype// "@AuthType"
0x9a8c  ldarg.0
0x9a8d  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x9a92  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x9a97  box      [mscorlib]System.Int32
0x9a9c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9aa1  pop
0x9aa2  ldloc.0
0x9aa3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9aa8  ldstr    aDsid// "@DSID"
0x9aad  ldarg.3
0x9aae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ID()
0x9ab3  box      [mscorlib]System.Guid
0x9ab8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9abd  pop
0x9abe  ldarg.s  5
0x9ac0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ac5  brtrue.s loc_9ADA
0x9ac7  ldloc.0
0x9ac8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9acd  ldstr    aEditsessionid// "@EditSessionID"
0x9ad2  ldarg.s  5
0x9ad4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9ad9  pop
0x9ada  ldarg.1
0x9adb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ae0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9ae5  brfalse.s loc_9AFE
0x9ae7  ldloc.0
0x9ae8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9aed  ldstr    aItemid_0// "@ItemID"
0x9af2  ldarg.1
0x9af3  box      [mscorlib]System.Guid
0x9af8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9afd  pop
0x9afe  ldarg.2
0x9aff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9b04  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9b09  brfalse.s loc_9B22
0x9b0b  ldloc.0
0x9b0c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9b11  ldstr    aSubscriptionid// "@SubscriptionID"
0x9b16  ldarg.2
0x9b17  box      [mscorlib]System.Guid
0x9b1c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9b21  pop
0x9b22  ldarg.3
0x9b23  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalName()
0x9b28  brfalse.s loc_9B3E
0x9b2a  ldloc.0
0x9b2b  ldstr    aName_0// "@Name"
0x9b30  ldc.i4.s 0xC
0x9b32  ldarg.3
0x9b33  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalName()
0x9b38  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9b3d  pop
0x9b3e  ldarg.3
0x9b3f  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_IsReference()
0x9b44  brfalse  loc_9C0D
0x9b49  ldarg.3
0x9b4a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_LinkID()
0x9b4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9b54  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9b59  brfalse.s loc_9B77
0x9b5b  ldloc.0
0x9b5c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9b61  ldstr    aLinkid// "@LinkID"
0x9b66  ldarg.3
0x9b67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_LinkID()
0x9b6c  box      [mscorlib]System.Guid
0x9b71  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9b76  pop
0x9b77  ldarg.3
0x9b78  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_DataSourceReference()
0x9b7d  brfalse.s loc_9B9A
0x9b7f  ldloc.0
0x9b80  ldstr    aLinkpath// "@LinkPath"
0x9b85  ldc.i4.s 0xC
0x9b87  ldarg.s  4
0x9b89  ldarg.3
0x9b8a  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_DataSourceReference()
0x9b8f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0x9b94  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9b99  pop
0x9b9a  ldloc.0
0x9b9b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9ba0  ldstr    aCredentialretr// "@CredentialRetrieval"
0x9ba5  ldc.i4.1
0x9ba6  box      [mscorlib]System.Int32
0x9bab  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9bb0  pop
0x9bb1  ldloc.0
0x9bb2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9bb7  ldstr    aFlags// "@Flags"
0x9bbc  ldarg.3
0x9bbd  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_FlagsForCatalogSerialization()
0x9bc2  box      [mscorlib]System.Int32
0x9bc7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9bcc  pop
0x9bcd  ldarg.3
0x9bce  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectionStringEncrypted()
0x9bd3  brfalse.s loc_9BEC
0x9bd5  ldloc.0
0x9bd6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9bdb  ldstr    aOriginalconnec_0// "@OriginalConnectionString"
0x9be0  ldarg.3
0x9be1  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectionStringEncrypted()
0x9be6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9beb  pop
0x9bec  ldloc.0
0x9bed  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9bf2  ldstr    aOriginalconnec_1// "@OriginalConnectStringExpressionBased"
0x9bf7  ldarg.3
0x9bf8  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectStringExpressionBased()
0x9bfd  box      [mscorlib]System.Boolean
0x9c02  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9c07  pop
0x9c08  br       loc_9D0D
0x9c0d  ldloc.0
0x9c0e  ldstr    aExtension// "@Extension"
0x9c13  ldc.i4.s 0xC
0x9c15  ldarg.3
0x9c16  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x9c1b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9c20  pop
0x9c21  ldloc.0
0x9c22  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9c27  ldstr    aCredentialretr// "@CredentialRetrieval"
0x9c2c  ldarg.3
0x9c2d  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo/CredentialsRetrievalOption [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x9c32  box      [mscorlib]System.Int32
0x9c37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9c3c  pop
0x9c3d  ldarg.3
0x9c3e  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Prompt()
0x9c43  brfalse.s loc_9C59
0x9c45  ldloc.0
0x9c46  ldstr    aPrompt// "@Prompt"
0x9c4b  ldc.i4.s 0xB
0x9c4d  ldarg.3
0x9c4e  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Prompt()
0x9c53  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9c58  pop
0x9c59  ldarg.3
0x9c5a  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ConnectionStringEncrypted()
0x9c5f  brfalse.s loc_9C78
0x9c61  ldloc.0
0x9c62  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9c67  ldstr    aConnectionstri_0// "@ConnectionString"
0x9c6c  ldarg.3
0x9c6d  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ConnectionStringEncrypted()
0x9c72  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9c77  pop
0x9c78  ldarg.3
0x9c79  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectionStringEncrypted()
0x9c7e  brfalse.s loc_9C97
0x9c80  ldloc.0
0x9c81  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9c86  ldstr    aOriginalconnec_0// "@OriginalConnectionString"
0x9c8b  ldarg.3
0x9c8c  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectionStringEncrypted()
0x9c91  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9c96  pop
0x9c97  ldarg.3
0x9c98  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_UserNameEncrypted()
0x9c9d  brfalse.s loc_9CB6
0x9c9f  ldloc.0
0x9ca0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9ca5  ldstr    aUsername_0// "@UserName"
0x9caa  ldarg.3
0x9cab  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_UserNameEncrypted()
0x9cb0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9cb5  pop
0x9cb6  ldarg.3
0x9cb7  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_PasswordEncrypted()
0x9cbc  brfalse.s loc_9CD5
0x9cbe  ldloc.0
0x9cbf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9cc4  ldstr    aPassword_0// "@Password"
0x9cc9  ldarg.3
0x9cca  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_PasswordEncrypted()
0x9ccf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9cd4  pop
0x9cd5  ldloc.0
0x9cd6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9cdb  ldstr    aFlags// "@Flags"
0x9ce0  ldarg.3
0x9ce1  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_FlagsForCatalogSerialization()
0x9ce6  box      [mscorlib]System.Int32
0x9ceb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9cf0  pop
0x9cf1  ldloc.0
0x9cf2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9cf7  ldstr    aOriginalconnec_1// "@OriginalConnectStringExpressionBased"
0x9cfc  ldarg.3
0x9cfd  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalConnectStringExpressionBased()
0x9d02  box      [mscorlib]System.Boolean
0x9d07  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9d0c  pop
0x9d0d  ldloc.0
0x9d0e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9d13  ldstr    aVersion// "@Version"
0x9d18  call     int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption::get_CurrentVersion()
0x9d1d  box      [mscorlib]System.Int32
0x9d22  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9d27  pop
0x9d28  ldloc.0
0x9d29  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x9d2e  stloc.1
0x9d2f  ldloc.1
0x9d30  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x9d35  brfalse.s loc_9D79
0x9d37  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x9d3c  ldarg.3
0x9d3d  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ReferenceByPath()
0x9d42  ldstr    aDbinterfaceAdd// "DBInterface.AddDataSource - read someth"...
0x9d47  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9d4c  ldarg.s  7
0x9d4e  ldloc.1
0x9d4f  ldc.i4.0
0x9d50  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x9d55  stind.i4
0x9d56  ldarg.s  6
0x9d58  ldloc.1
0x9d59  ldc.i4.1
0x9d5a  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x9d5f  stobj    [mscorlib]System.Guid
0x9d64  ldloc.1
0x9d65  ldc.i4.2
0x9d66  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x9d6b  brtrue.s loc_9D91
0x9d6d  ldarg.s  8
0x9d6f  ldloc.1
0x9d70  ldc.i4.2
0x9d71  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x9d76  stind.ref
0x9d77  leave.s  loc_9DA7
0x9d79  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x9d7e  ldarg.3
0x9d7f  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ReferenceByPath()
0x9d84  ldc.i4.0
0x9d85  ceq
0x9d87  ldstr    aDbinterfaceAdd_0// "DBInterface.AddDataSource - expected to"...
0x9d8c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9d91  leave.s  loc_9DA7
0x9d93  ldloc.1
0x9d94  brfalse.s loc_9D9C
0x9d96  ldloc.1
0x9d97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9d9c  endfinally
0x9d9d  ldloc.0
0x9d9e  brfalse.s loc_9DA6
0x9da0  ldloc.0
0x9da1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9da6  endfinally
0x9da7  ret
```
