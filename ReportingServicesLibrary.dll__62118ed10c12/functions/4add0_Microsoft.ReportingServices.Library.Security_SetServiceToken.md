# Microsoft.ReportingServices.Library.Security::SetServiceToken

- ea: `0x4add0`
- end: `0x4aeb0`
- name: `Microsoft.ReportingServices.Library.Security::SetServiceToken`
- size: `224`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x21ff0`
- `0x4bb00`
- `0x4bb20`

## callees

- `0xf570`
- `0x4add0`

## string_xrefs

- `0x4ae5f`: `@ServiceToken`
- `0x4ae27`: `@UserSid`
- `0x4adfc`: `SetUserServiceToken`

## pseudocode

```c

```

## disassembly

```asm
0x4add0  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_IsInitialized()
0x4add5  brtrue.s loc_4ADE3
0x4add7  ldarg.0
0x4add8  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x4addd  ldc.i4.1
0x4adde  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection(bool)
0x4ade3  ldarg.1
0x4ade4  brtrue.s loc_4ADE9
0x4ade6  ldnull
0x4ade7  br.s     loc_4ADFA
0x4ade9  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.CatalogEncryption::get_Instance()
0x4adee  ldarg.1
0x4adef  callvirt instance string [Microsoft.ReportingServices.Hybrid]Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::ToJson()
0x4adf4  ldnull
0x4adf5  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption::EncryptToString(string, string)
0x4adfa  stloc.0
0x4adfb  ldarg.0
0x4adfc  ldstr    aSetuserservice// "SetUserServiceToken"
0x4ae01  ldnull
0x4ae02  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4ae07  stloc.1
0x4ae08  ldloc.1
0x4ae09  ldstr    aUsername_0// "@UserName"
0x4ae0e  ldc.i4.s 0xC
0x4ae10  ldarg.0
0x4ae11  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ae16  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x4ae1b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4ae20  pop
0x4ae21  ldloc.1
0x4ae22  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4ae27  ldstr    aUsersid// "@UserSid"
0x4ae2c  ldarg.0
0x4ae2d  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ae32  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x4ae37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4ae3c  pop
0x4ae3d  ldloc.1
0x4ae3e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4ae43  ldstr    aAuthtype// "@AuthType"
0x4ae48  ldarg.0
0x4ae49  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4ae4e  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x4ae53  box      [mscorlib]System.Int32
0x4ae58  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4ae5d  pop
0x4ae5e  ldloc.1
0x4ae5f  ldstr    aServicetoken// "@ServiceToken"
0x4ae64  ldc.i4.s 0xB
0x4ae66  ldloc.0
0x4ae67  dup
0x4ae68  brtrue.s loc_4AE70
0x4ae6a  pop
0x4ae6b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x4ae70  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4ae75  pop
0x4ae76  ldloc.1
0x4ae77  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x4ae7c  pop
0x4ae7d  ldarg.0
0x4ae7e  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x4ae83  leave.s  loc_4AE8F
0x4ae85  ldloc.1
0x4ae86  brfalse.s loc_4AE8E
0x4ae88  ldloc.1
0x4ae89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ae8e  endfinally
0x4ae8f  leave.s  loc_4AEAF
0x4ae91  ldarg.0
0x4ae92  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x4ae97  dup
0x4ae98  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x4ae9d  brfalse.s loc_4AEA1
0x4ae9f  rethrow
0x4aea1  ldnull
0x4aea2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x4aea7  throw
0x4aea8  ldarg.0
0x4aea9  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Disconnect()
0x4aeae  endfinally
0x4aeaf  ret
```
