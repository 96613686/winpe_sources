# Microsoft.ReportingServices.Library.Security::GetServiceTokenFromCatalog

- ea: `0x4ab20`
- end: `0x4abe5`
- name: `Microsoft.ReportingServices.Library.Security::GetServiceTokenFromCatalog`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x21070`
- `0x4bac0`
- `0x4bae0`

## callees

- `0xf570`
- `0x4ab20`

## string_xrefs

- `0x4ab4e`: `@UserSid`
- `0x4ab23`: `GetUserServiceToken`

## pseudocode

```c

```

## disassembly

```asm
0x4ab20  ldnull
0x4ab21  stloc.0
0x4ab22  ldarg.0
0x4ab23  ldstr    aGetuserservice_0// "GetUserServiceToken"
0x4ab28  ldnull
0x4ab29  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4ab2e  stloc.1
0x4ab2f  ldloc.1
0x4ab30  ldstr    aUsername_0// "@UserName"
0x4ab35  ldc.i4.s 0xC
0x4ab37  ldarg.0
0x4ab38  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ab3d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x4ab42  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4ab47  pop
0x4ab48  ldloc.1
0x4ab49  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4ab4e  ldstr    aUsersid// "@UserSid"
0x4ab53  ldarg.0
0x4ab54  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ab59  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x4ab5e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4ab63  pop
0x4ab64  ldloc.1
0x4ab65  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4ab6a  ldstr    aAuthtype// "@AuthType"
0x4ab6f  ldarg.0
0x4ab70  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ab75  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x4ab7a  box      [mscorlib]System.Int32
0x4ab7f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4ab84  pop
0x4ab85  ldloc.1
0x4ab86  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x4ab8b  stloc.2
0x4ab8c  ldarg.0
0x4ab8d  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x4ab92  ldloc.2
0x4ab93  isinst   [mscorlib]System.DBNull
0x4ab98  brfalse.s loc_4AB9E
0x4ab9a  ldnull
0x4ab9b  stloc.3
0x4ab9c  leave.s  loc_4ABE3
0x4ab9e  ldloc.2
0x4ab9f  castclass [mscorlib]System.String
0x4aba4  stloc.0
0x4aba5  leave.s  loc_4ABB1
0x4aba7  ldloc.1
0x4aba8  brfalse.s loc_4ABB0
0x4abaa  ldloc.1
0x4abab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4abb0  endfinally
0x4abb1  leave.s  loc_4ABD1
0x4abb3  ldarg.0
0x4abb4  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x4abb9  dup
0x4abba  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x4abbf  brfalse.s loc_4ABC3
0x4abc1  rethrow
0x4abc3  ldnull
0x4abc4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x4abc9  throw
0x4abca  ldarg.0
0x4abcb  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Disconnect()
0x4abd0  endfinally
0x4abd1  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.CatalogEncryption::get_Instance()
0x4abd6  ldloc.0
0x4abd7  ldnull
0x4abd8  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(string, string)
0x4abdd  call     class [Microsoft.ReportingServices.Hybrid]Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken [Microsoft.ReportingServices.Hybrid]Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::FromJson(string)
0x4abe2  ret
0x4abe3  ldloc.3
0x4abe4  ret
```
