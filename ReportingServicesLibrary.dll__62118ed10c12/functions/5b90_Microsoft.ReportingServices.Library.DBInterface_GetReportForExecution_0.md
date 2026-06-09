# Microsoft.ReportingServices.Library.DBInterface::GetReportForExecution_0

- ea: `0x5b90`
- end: `0x6114`
- name: `Microsoft.ReportingServices.Library.DBInterface::GetReportForExecution_0`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5b30`

## callees

- `0x4630`
- `0x5ae0`
- `0x5b90`
- `0x7950`
- `0xee80`
- `0xef30`
- `0xef40`
- `0x47f90`
- `0x5fac0`

## string_xrefs

- `0x5cc4`: `@OwnerSid`
- `0x5cd2`: `@OwnerSid`
- `0x5ee3`: `No end time found for expiring cache on minutes`

## pseudocode

```c

```

## disassembly

```asm
0x5b90  ldc.i4.0
0x5b91  stloc.0
0x5b92  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5b97  stloc.1
0x5b98  ldarg.s  0xD
0x5b9a  call     int32 Microsoft.ReportingServices.Library.ExecutionOptions::get_Live()
0x5b9f  stind.i4
0x5ba0  ldarg.3
0x5ba1  ldc.i4.0
0x5ba2  stind.i1
0x5ba3  ldarg.s  4
0x5ba5  ldc.i4.0
0x5ba6  stind.i4
0x5ba7  ldarg.s  5
0x5ba9  ldnull
0x5baa  stind.ref
0x5bab  ldarg.s  6
0x5bad  ldnull
0x5bae  stind.ref
0x5baf  ldarg.s  7
0x5bb1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bb6  stobj    [mscorlib]System.Guid
0x5bbb  ldarg.s  8
0x5bbd  ldnull
0x5bbe  stind.ref
0x5bbf  ldarg.s  9
0x5bc1  ldnull
0x5bc2  stind.ref
0x5bc3  ldarg.s  0xA
0x5bc5  ldnull
0x5bc6  stind.ref
0x5bc7  ldarg.s  0xB
0x5bc9  ldnull
0x5bca  stind.ref
0x5bcb  ldarg.s  0xC
0x5bcd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bd2  stobj    [mscorlib]System.Guid
0x5bd7  ldarg.s  0xE
0x5bd9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5bde  stobj    [mscorlib]System.DateTime
0x5be3  ldarg.s  0x11
0x5be5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5bea  stobj    [mscorlib]System.DateTime
0x5bef  ldarg.s  0xF
0x5bf1  ldc.i4.0
0x5bf2  stind.i1
0x5bf3  ldarg.s  0x10
0x5bf5  ldc.i4.0
0x5bf6  stind.i1
0x5bf7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bfc  stloc.2
0x5bfd  ldc.i4.1
0x5bfe  stloc.3
0x5bff  ldarg.s  0x12
0x5c01  ldind.u1
0x5c02  brtrue.s loc_5C14
0x5c04  ldarg.0
0x5c05  ldstr    aGetreportforex// "GetReportForExecution"
0x5c0a  ldnull
0x5c0b  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x5c10  stloc.s  4
0x5c12  br.s     loc_5C22
0x5c14  ldarg.0
0x5c15  ldarg.0
0x5c16  call     instance string Microsoft.ReportingServices.Library.DBInterface::get_GetReportForExecutionQuery()
0x5c1b  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string)
0x5c20  stloc.s  4
0x5c22  ldloc.s  4
0x5c24  stloc.s  5
0x5c26  ldarg.1
0x5c27  ldloc.s  4
0x5c29  ldc.i4.1
0x5c2a  ldarg.0
0x5c2b  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x5c30  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::BindItemPathToCommand(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand, bool, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x5c35  ldloc.s  4
0x5c37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c3c  ldstr    aAuthtype// "@AuthType"
0x5c41  ldarg.0
0x5c42  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x5c47  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x5c4c  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType
0x5c51  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5c56  ldc.i4.8
0x5c57  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5c5c  ldloc.s  4
0x5c5e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c63  ldstr    aParamshash// "@ParamsHash"
0x5c68  ldarg.2
0x5c69  call     T0x2B000002
0x5c6e  box      [mscorlib]System.Int32
0x5c73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5c78  ldc.i4.8
0x5c79  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5c7e  ldarg.s  0x12
0x5c80  ldind.u1
0x5c81  brfalse  loc_5D0B
0x5c86  ldloc.s  4
0x5c88  ldstr    aQueryparams// "@QueryParams"
0x5c8d  ldc.i4.s 0xB
0x5c8f  ldarg.2
0x5c90  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5c95  pop
0x5c96  ldloc.s  4
0x5c98  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c9d  ldstr    aEditsessionid// "@EditSessionID"
0x5ca2  callvirt instance bool [System.Data]System.Data.Common.DbParameterCollection::Contains(string)
0x5ca7  brtrue.s loc_5CBD
0x5ca9  ldloc.s  4
0x5cab  ldstr    aEditsessionid// "@EditSessionID"
0x5cb0  ldc.i4.s 0x16
0x5cb2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5cb7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5cbc  pop
0x5cbd  ldloc.s  4
0x5cbf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cc4  ldstr    aOwnersid// "@OwnerSid"
0x5cc9  callvirt instance bool [System.Data]System.Data.Common.DbParameterCollection::Contains(string)
0x5cce  brtrue.s loc_5CE4
0x5cd0  ldloc.s  4
0x5cd2  ldstr    aOwnersid// "@OwnerSid"
0x5cd7  ldc.i4.s 0x15
0x5cd9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5cde  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5ce3  pop
0x5ce4  ldloc.s  4
0x5ce6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ceb  ldstr    aOwnername// "@OwnerName"
0x5cf0  callvirt instance bool [System.Data]System.Data.Common.DbParameterCollection::Contains(string)
0x5cf5  brtrue.s loc_5D0B
0x5cf7  ldloc.s  4
0x5cf9  ldstr    aOwnername// "@OwnerName"
0x5cfe  ldc.i4.s 0xC
0x5d00  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d05  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5d0a  pop
0x5d0b  ldloc.s  4
0x5d0d  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x5d12  stloc.s  6
0x5d14  ldloc.s  6
0x5d16  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x5d1b  brtrue.s loc_5D25
0x5d1d  ldc.i4.0
0x5d1e  stloc.s  7
0x5d20  leave    loc_6111
0x5d25  ldarg.s  4
0x5d27  ldloc.s  6
0x5d29  ldc.i4.0
0x5d2a  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x5d2f  stind.i4
0x5d30  ldloc.s  6
0x5d32  ldc.i4.1
0x5d33  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d38  brtrue.s loc_5D49
0x5d3a  ldarg.s  7
0x5d3c  ldloc.s  6
0x5d3e  ldc.i4.1
0x5d3f  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5d44  stobj    [mscorlib]System.Guid
0x5d49  ldloc.s  6
0x5d4b  ldc.i4.2
0x5d4c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d51  brtrue.s loc_5D5E
0x5d53  ldarg.s  8
0x5d55  ldloc.s  6
0x5d57  ldc.i4.2
0x5d58  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5d5d  stind.ref
0x5d5e  ldloc.s  6
0x5d60  ldc.i4.3
0x5d61  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d66  brtrue.s loc_5D73
0x5d68  ldarg.s  9
0x5d6a  ldloc.s  6
0x5d6c  ldc.i4.3
0x5d6d  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5d72  stind.ref
0x5d73  ldloc.s  6
0x5d75  ldc.i4.4
0x5d76  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d7b  brtrue.s loc_5D88
0x5d7d  ldarg.s  0xA
0x5d7f  ldloc.s  6
0x5d81  ldc.i4.4
0x5d82  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5d87  stind.ref
0x5d88  ldloc.s  6
0x5d8a  ldc.i4.5
0x5d8b  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5d90  brtrue.s loc_5D9D
0x5d92  ldarg.s  0xB
0x5d94  ldloc.s  6
0x5d96  ldc.i4.5
0x5d97  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x5d9c  stind.ref
0x5d9d  ldloc.s  6
0x5d9f  ldc.i4.6
0x5da0  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5da5  brtrue.s loc_5DB6
0x5da7  ldarg.s  0xC
0x5da9  ldloc.s  6
0x5dab  ldc.i4.6
0x5dac  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5db1  stobj    [mscorlib]System.Guid
0x5db6  ldloc.s  6
0x5db8  ldc.i4.7
0x5db9  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5dbe  brtrue.s loc_5DCA
0x5dc0  ldarg.3
0x5dc1  ldloc.s  6
0x5dc3  ldc.i4.7
0x5dc4  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x5dc9  stind.i1
0x5dca  ldarg.3
0x5dcb  ldind.u1
0x5dcc  brfalse  loc_5F2B
0x5dd1  ldloc.s  6
0x5dd3  ldc.i4.8
0x5dd4  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5dd9  brtrue.s loc_5E26
0x5ddb  ldloc.s  6
0x5ddd  ldc.i4.8
0x5dde  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5de3  stloc.s  9
0x5de5  ldc.i4.0
0x5de6  stloc.s  0xA
0x5de8  ldloc.s  6
0x5dea  ldc.i4.s 9
0x5dec  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5df1  brtrue.s loc_5DFE
0x5df3  ldloc.s  6
0x5df5  ldc.i4.s 9
0x5df7  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x5dfc  stloc.s  0xA
0x5dfe  ldc.i4.0
0x5dff  stloc.s  0xB
0x5e01  ldloc.s  6
0x5e03  ldc.i4.s 0x10
0x5e05  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5e0a  brtrue.s loc_5E17
0x5e0c  ldloc.s  6
0x5e0e  ldc.i4.s 0x10
0x5e10  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x5e15  stloc.s  0xB
0x5e17  ldarg.s  6
0x5e19  ldloc.s  9
0x5e1b  ldc.i4.0
0x5e1c  ldloc.s  0xA
0x5e1e  ldloc.s  0xB
0x5e20  call     class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportSnapshot::Create(valuetype [mscorlib]System.Guid snapshotDataID, bool isPermanentSnapshot, bool dependsOnUser, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags)
0x5e25  stind.ref
0x5e26  ldarg.s  0x10
0x5e28  ldc.i4.1
0x5e29  stind.i1
0x5e2a  ldarg.s  0xF
0x5e2c  ldc.i4.1
0x5e2d  stind.i1
0x5e2e  ldloc.s  6
0x5e30  ldc.i4.s 0xA
0x5e32  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5e37  pop
0x5e38  ldarg.s  0xE
0x5e3a  ldloc.s  6
0x5e3c  ldc.i4.s 0xB
0x5e3e  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5e43  stobj    [mscorlib]System.DateTime
0x5e48  ldloc.s  6
0x5e4a  ldc.i4.s 0xC
0x5e4c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5e51  brtrue.s loc_5E63
0x5e53  ldarg.s  0x11
0x5e55  ldloc.s  6
0x5e57  ldc.i4.s 0xC
0x5e59  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5e5e  stobj    [mscorlib]System.DateTime
0x5e63  ldloc.s  6
0x5e65  ldc.i4.s 0xD
0x5e67  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5e6c  brtrue.s loc_5E78
0x5e6e  ldloc.s  6
0x5e70  ldc.i4.s 0xD
0x5e72  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x5e77  stloc.0
0x5e78  ldloc.s  6
0x5e7a  ldc.i4.s 0xE
0x5e7c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5e81  brtrue.s loc_5E8D
0x5e83  ldloc.s  6
0x5e85  ldc.i4.s 0xE
0x5e87  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5e8c  stloc.1
0x5e8d  ldnull
0x5e8e  stloc.s  8
0x5e90  ldloc.s  6
0x5e92  ldc.i4.s 0xF
0x5e94  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5e99  brtrue.s loc_5EA6
0x5e9b  ldloc.s  6
0x5e9d  ldc.i4.s 0xF
0x5e9f  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
  ... truncated ...
```
