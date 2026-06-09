# Microsoft.ReportingServices.Library.DBInterface::CreateEditSession

- ea: `0x6b90`
- end: `0x6d95`
- name: `Microsoft.ReportingServices.Library.DBInterface::CreateEditSession`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x6b90`
- `0xf310`
- `0xf570`

## string_xrefs

- `0x6c1a`: `@OwnerSid`
- `0x6d49`: `@DataCacheHash`
- `0x6ba9`: `itemPath`
- `0x6bcc`: `CreateEditSession`
- `0x6bf8`: `@ContextPath`

## pseudocode

```c

```

## disassembly

```asm
0x6b90  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6b95  ldarg.1
0x6b96  brfalse.s loc_6BA8
0x6b98  ldarg.1
0x6b99  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6b9e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ba3  ldc.i4.0
0x6ba4  ceq
0x6ba6  br.s     loc_6BA9
0x6ba8  ldc.i4.0
0x6ba9  ldstr    aItempath_0// "itemPath"
0x6bae  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6bb3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6bb8  ldarg.2
0x6bb9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6bbe  ldc.i4.0
0x6bbf  ceq
0x6bc1  ldstr    aEditsessionid_0// "editSessionID"
0x6bc6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6bcb  ldarg.0
0x6bcc  ldstr    aCreateeditsess// "CreateEditSession"
0x6bd1  ldnull
0x6bd2  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x6bd7  stloc.0
0x6bd8  ldloc.0
0x6bd9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6bde  ldstr    aEditsessionid// "@EditSessionID"
0x6be3  ldc.i4.s 0x16
0x6be5  ldc.i4.s 0x20
0x6be7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6bec  ldarg.2
0x6bed  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6bf2  ldloc.0
0x6bf3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6bf8  ldstr    aContextpath// "@ContextPath"
0x6bfd  ldc.i4.s 0xC
0x6bff  ldc.i4   0x1B8
0x6c04  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6c09  ldarg.1
0x6c0a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6c0f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6c14  ldloc.0
0x6c15  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6c1a  ldstr    aOwnersid// "@OwnerSid"
0x6c1f  ldc.i4.s 0x15
0x6c21  ldc.i4.s 0x55
0x6c23  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6c28  ldarg.0
0x6c29  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6c2e  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x6c33  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6c38  ldloc.0
0x6c39  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6c3e  ldstr    aOwnername// "@OwnerName"
0x6c43  ldc.i4.s 0xC
0x6c45  ldc.i4   0x104
0x6c4a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6c4f  ldarg.0
0x6c50  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6c55  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x6c5a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6c5f  ldloc.0
0x6c60  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6c65  ldstr    aAuthtype// "@AuthType"
0x6c6a  ldc.i4.8
0x6c6b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6c70  ldarg.0
0x6c71  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x6c76  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x6c7b  box      [mscorlib]System.Int32
0x6c80  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6c85  ldloc.0
0x6c86  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6c8b  ldstr    aTimeout// "@Timeout"
0x6c90  ldc.i4.8
0x6c91  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6c96  call     int32 Microsoft.ReportingServices.Library.Global::get_EditSessionTimeoutMinutes()
0x6c9b  box      [mscorlib]System.Int32
0x6ca0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6ca5  ldloc.0
0x6ca6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6cab  ldstr    aContent_0// "@Content"
0x6cb0  ldc.i4.7
0x6cb1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6cb6  ldarg.s  4
0x6cb8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6cbd  ldloc.0
0x6cbe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6cc3  ldstr    aDescription// "@Description"
0x6cc8  ldc.i4.s 0xB
0x6cca  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6ccf  ldarg.s  5
0x6cd1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6cd6  ldloc.0
0x6cd7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6cdc  ldstr    aProperty_0// "@Property"
0x6ce1  ldc.i4.s 0xB
0x6ce3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6ce8  ldarg.s  7
0x6cea  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6cef  ldloc.0
0x6cf0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6cf5  ldstr    aParameter// "@Parameter"
0x6cfa  ldc.i4.s 0xB
0x6cfc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6d01  ldarg.s  8
0x6d03  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6d08  ldloc.0
0x6d09  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6d0e  ldstr    aIntermediate// "@Intermediate"
0x6d13  ldc.i4.s 0xE
0x6d15  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6d1a  ldarg.s  6
0x6d1c  box      [mscorlib]System.Guid
0x6d21  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6d26  ldloc.0
0x6d27  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6d2c  ldstr    aName_0// "@Name"
0x6d31  ldc.i4.s 0xC
0x6d33  ldc.i4   0x1B8
0x6d38  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6d3d  ldarg.3
0x6d3e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6d43  ldloc.0
0x6d44  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6d49  ldstr    aDatacachehash// "@DataCacheHash"
0x6d4e  ldc.i4.s 0x15
0x6d50  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6d55  ldarg.s  9
0x6d57  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6d5c  ldloc.0
0x6d5d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6d62  ldstr    aNewitemid// "@NewItemID"
0x6d67  ldc.i4.s 0xE
0x6d69  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6d6e  dup
0x6d6f  ldc.i4.2
0x6d70  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x6d75  ldloc.0
0x6d76  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x6d7b  pop
0x6d7c  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x6d81  unbox.any [mscorlib]System.Guid
0x6d86  stloc.1
0x6d87  leave.s  loc_6D93
0x6d89  ldloc.0
0x6d8a  brfalse.s loc_6D92
0x6d8c  ldloc.0
0x6d8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d92  endfinally
0x6d93  ldloc.1
0x6d94  ret
```
