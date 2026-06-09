# Microsoft.ReportingServices.Library.DBInterface::IsUserContextOwner

- ea: `0x7070`
- end: `0x713e`
- name: `Microsoft.ReportingServices.Library.DBInterface::IsUserContextOwner`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x7070`
- `0xf570`

## string_xrefs

- `0x709f`: `@UserSid`
- `0x7083`: `@CommentID`
- `0x7071`: `CommentBelongsToUser`
- `0x7127`: `CommentBelongsToUser returned something not 0 or 1.`

## pseudocode

```c

```

## disassembly

```asm
0x7070  ldarg.0
0x7071  ldstr    aCommentbelongs// "CommentBelongsToUser"
0x7076  ldnull
0x7077  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x707c  stloc.0
0x707d  ldloc.0
0x707e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7083  ldstr    aCommentid_0// "@CommentID"
0x7088  ldc.i4.0
0x7089  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x708e  ldarg.1
0x708f  box      [mscorlib]System.Int64
0x7094  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7099  ldloc.0
0x709a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x709f  ldstr    aUsersid// "@UserSid"
0x70a4  ldc.i4.s 0x15
0x70a6  ldc.i4.s 0x55
0x70a8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x70ad  ldarg.0
0x70ae  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x70b3  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x70b8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x70bd  ldloc.0
0x70be  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x70c3  ldstr    aUsername_0// "@UserName"
0x70c8  ldc.i4.s 0xC
0x70ca  ldc.i4   0x104
0x70cf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x70d4  ldarg.0
0x70d5  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x70da  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x70df  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x70e4  ldloc.0
0x70e5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x70ea  ldstr    aAuthtype// "@AuthType"
0x70ef  ldc.i4.8
0x70f0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x70f5  ldarg.0
0x70f6  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x70fb  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x7100  box      [mscorlib]System.Int32
0x7105  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x710a  ldloc.0
0x710b  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x7110  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x7115  stloc.1
0x7116  ldloc.1
0x7117  brfalse.s loc_711F
0x7119  ldloc.1
0x711a  ldc.i4.1
0x711b  beq.s    loc_7123
0x711d  br.s     loc_7127
0x711f  ldc.i4.0
0x7120  stloc.2
0x7121  leave.s  loc_713C
0x7123  ldc.i4.1
0x7124  stloc.2
0x7125  leave.s  loc_713C
0x7127  ldstr    aCommentbelongs_0// "CommentBelongsToUser returned something"...
0x712c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x7131  throw
0x7132  ldloc.0
0x7133  brfalse.s loc_713B
0x7135  ldloc.0
0x7136  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x713b  endfinally
0x713c  ldloc.2
0x713d  ret
```
