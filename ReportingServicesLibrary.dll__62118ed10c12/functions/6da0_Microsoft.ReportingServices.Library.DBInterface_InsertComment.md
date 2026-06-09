# Microsoft.ReportingServices.Library.DBInterface::InsertComment

- ea: `0x6da0`
- end: `0x6feb`
- name: `Microsoft.ReportingServices.Library.DBInterface::InsertComment`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e20`
- `0x2e30`
- `0x2e40`
- `0x2e60`
- `0x2e70`
- `0x2e80`
- `0x2e90`
- `0x2ea0`
- `0x2eb0`
- `0x2ec0`
- `0x2ee0`
- `0x2f00`
- `0x2f10`
- `0x4630`
- `0x6da0`
- `0xf570`

## string_xrefs

- `0x6db3`: `@UserSid`
- `0x6da1`: `InsertComment`
- `0x6e78`: `@ThreadID`
- `0x6ea1`: `@AttachmentPath`
- `0x6ee9`: `CommentID`
- `0x6f3c`: `CreatedDate`
- `0x6f53`: `AttachmentPath`
- `0x6fa4`: `ThreadID`

## pseudocode

```c

```

## disassembly

```asm
0x6da0  ldarg.0
0x6da1  ldstr    aInsertcomment// "InsertComment"
0x6da6  ldnull
0x6da7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x6dac  stloc.0
0x6dad  ldloc.0
0x6dae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6db3  ldstr    aUsersid// "@UserSid"
0x6db8  ldc.i4.s 0x15
0x6dba  ldc.i4.s 0x55
0x6dbc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6dc1  ldarg.0
0x6dc2  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6dc7  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x6dcc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6dd1  ldloc.0
0x6dd2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6dd7  ldstr    aUsername_0// "@UserName"
0x6ddc  ldc.i4.s 0xC
0x6dde  ldc.i4   0x104
0x6de3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6de8  ldarg.0
0x6de9  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6dee  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x6df3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6df8  ldloc.0
0x6df9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6dfe  ldstr    aAuthtype// "@AuthType"
0x6e03  ldc.i4.8
0x6e04  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6e09  ldarg.0
0x6e0a  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6e0f  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x6e14  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType
0x6e19  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6e1e  ldloc.0
0x6e1f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6e24  ldstr    aItemid_0// "@ItemID"
0x6e29  ldc.i4.s 0xE
0x6e2b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6e30  ldarg.1
0x6e31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.Comment::get_ItemId()
0x6e36  box      [mscorlib]System.Guid
0x6e3b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6e40  ldloc.0
0x6e41  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6e46  ldstr    aText_0// "@Text"
0x6e4b  ldc.i4.s 0xC
0x6e4d  ldc.i4   0x800
0x6e52  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6e57  ldarg.1
0x6e58  callvirt instance string Microsoft.ReportingServices.Library.Comment::get_Text()
0x6e5d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6e62  ldarg.1
0x6e63  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Library.Comment::get_ThreadId()
0x6e68  stloc.1
0x6e69  ldloca.s 1
0x6e6b  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x6e70  brfalse.s loc_6E93
0x6e72  ldloc.0
0x6e73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6e78  ldstr    aThreadid// "@ThreadID"
0x6e7d  ldc.i4.0
0x6e7e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6e83  ldarg.1
0x6e84  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Library.Comment::get_ThreadId()
0x6e89  box      valuetype [mscorlib]System.Nullable`1<int64>
0x6e8e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6e93  ldarg.1
0x6e94  callvirt instance string Microsoft.ReportingServices.Library.Comment::get_AttachmentPath()
0x6e99  brfalse.s loc_6EBD
0x6e9b  ldloc.0
0x6e9c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6ea1  ldstr    aAttachmentpath// "@AttachmentPath"
0x6ea6  ldc.i4.s 0xC
0x6ea8  ldc.i4   0x1A9
0x6ead  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6eb2  ldarg.1
0x6eb3  callvirt instance string Microsoft.ReportingServices.Library.Comment::get_AttachmentPath()
0x6eb8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6ebd  ldloc.0
0x6ebe  ldc.i4.8
0x6ebf  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader(valuetype [System.Data]System.Data.CommandBehavior)
0x6ec4  stloc.2
0x6ec5  ldloc.2
0x6ec6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6ecb  brtrue.s loc_6ED5
0x6ecd  ldnull
0x6ece  stloc.s  8
0x6ed0  leave    loc_6FE8
0x6ed5  ldloc.2
0x6ed6  ldstr    aUsername// "UserName"
0x6edb  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6ee0  stloc.3
0x6ee1  newobj   instance void Microsoft.ReportingServices.Library.Comment::.ctor()
0x6ee6  dup
0x6ee7  ldloc.2
0x6ee8  ldloc.2
0x6ee9  ldstr    aCommentid// "CommentID"
0x6eee  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6ef3  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetInt64(int32)
0x6ef8  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_Id(int64 value)
0x6efd  dup
0x6efe  ldloc.2
0x6eff  ldloc.2
0x6f00  ldstr    aItemid// "ItemID"
0x6f05  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6f0a  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x6f0f  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_ItemId(valuetype [mscorlib]System.Guid value)
0x6f14  dup
0x6f15  ldloc.2
0x6f16  ldloc.3
0x6f17  ldloc.3
0x6f18  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserUtil::GetUserNameBySid(class [System.Data]System.Data.IDataRecord, int32, int32)
0x6f1d  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_UserName(string value)
0x6f22  dup
0x6f23  ldloc.2
0x6f24  ldloc.2
0x6f25  ldstr    aText// "Text"
0x6f2a  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6f2f  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x6f34  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_Text(string value)
0x6f39  dup
0x6f3a  ldloc.2
0x6f3b  ldloc.2
0x6f3c  ldstr    aCreateddate// "CreatedDate"
0x6f41  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6f46  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x6f4b  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_CreatedDate(valuetype [mscorlib]System.DateTime value)
0x6f50  stloc.s  4
0x6f52  ldloc.2
0x6f53  ldstr    aAttachmentpath_0// "AttachmentPath"
0x6f58  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6f5d  stloc.s  5
0x6f5f  ldloc.2
0x6f60  ldloc.s  5
0x6f62  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x6f67  brtrue.s loc_6F78
0x6f69  ldloc.s  4
0x6f6b  ldloc.2
0x6f6c  ldloc.s  5
0x6f6e  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x6f73  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_AttachmentPath(string value)
0x6f78  ldloc.2
0x6f79  ldstr    aModifieddate_0// "ModifiedDate"
0x6f7e  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6f83  stloc.s  6
0x6f85  ldloc.2
0x6f86  ldloc.s  6
0x6f88  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x6f8d  brtrue.s loc_6FA3
0x6f8f  ldloc.s  4
0x6f91  ldloc.2
0x6f92  ldloc.s  6
0x6f94  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x6f99  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x6f9e  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_ModifiedDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x6fa3  ldloc.2
0x6fa4  ldstr    aThreadid_0// "ThreadID"
0x6fa9  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x6fae  stloc.s  7
0x6fb0  ldloc.2
0x6fb1  ldloc.s  7
0x6fb3  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x6fb8  brtrue.s loc_6FCE
0x6fba  ldloc.s  4
0x6fbc  ldloc.2
0x6fbd  ldloc.s  7
0x6fbf  callvirt instance int64 [System.Data]System.Data.IDataRecord::GetInt64(int32)
0x6fc4  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x6fc9  callvirt instance void Microsoft.ReportingServices.Library.Comment::set_ThreadId(valuetype [mscorlib]System.Nullable`1<int64> value)
0x6fce  ldloc.s  4
0x6fd0  stloc.s  8
0x6fd2  leave.s  loc_6FE8
0x6fd4  ldloc.2
0x6fd5  brfalse.s loc_6FDD
0x6fd7  ldloc.2
0x6fd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6fdd  endfinally
0x6fde  ldloc.0
0x6fdf  brfalse.s loc_6FE7
0x6fe1  ldloc.0
0x6fe2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6fe7  endfinally
0x6fe8  ldloc.s  8
0x6fea  ret
```
