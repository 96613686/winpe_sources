# System.Web.ClientServices.Providers.ClientRoleProvider::RemoveRolesFromDB

- ea: `0x34c20`
- end: `0x34d12`
- name: `System.Web.ClientServices.Providers.ClientRoleProvider::RemoveRolesFromDB`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x34b40`
- `0x34d20`

## callees

- `0x34c20`
- `0x37320`
- `0x37370`
- `0x37cc0`
- `0x37dd0`
- `0x380e0`

## string_xrefs

- `0x34c87`: `DELETE FROM Roles WHERE UserName = @UserName`
- `0x34cb9`: `DELETE FROM UserProperties WHERE PropertyName = @RolesCachedDate`
- `0x34cc5`: `@RolesCachedDate`
- `0x34cca`: `RolesCachedDate_`

## pseudocode

```c

```

## disassembly

```asm
0x34c20  ldarg.0
0x34c21  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34c26  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34c2b  brfalse.s loc_34C2E
0x34c2d  ret
0x34c2e  ldarg.0
0x34c2f  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingFileSystemStore
0x34c34  brtrue.s loc_34C3E
0x34c36  ldarg.0
0x34c37  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34c3c  brfalse.s loc_34C5E
0x34c3e  ldarg.0
0x34c3f  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34c44  ldarg.0
0x34c45  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34c4a  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x34c4f  stloc.0
0x34c50  ldloc.0
0x34c51  ldnull
0x34c52  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_Roles(string[] value)
0x34c57  ldloc.0
0x34c58  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x34c5d  ret
0x34c5e  ldarg.0
0x34c5f  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34c64  ldarg.0
0x34c65  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34c6a  ldarg.0
0x34c6b  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionStringProvider
0x34c70  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x34c75  stloc.1
0x34c76  ldnull
0x34c77  stloc.2
0x34c78  ldloc.1
0x34c79  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x34c7e  stloc.2
0x34c7f  ldloc.1
0x34c80  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34c85  stloc.3
0x34c86  ldloc.3
0x34c87  ldstr    aDeleteFromRole// "DELETE FROM Roles WHERE UserName = @Use"...
0x34c8c  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34c91  ldloc.1
0x34c92  ldloc.3
0x34c93  ldstr    aUsername_0// "@UserName"
0x34c98  ldarg.0
0x34c99  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34c9e  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34ca3  ldloc.3
0x34ca4  ldloc.2
0x34ca5  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34caa  ldloc.3
0x34cab  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34cb0  pop
0x34cb1  ldloc.1
0x34cb2  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34cb7  stloc.3
0x34cb8  ldloc.3
0x34cb9  ldstr    aDeleteFromUser_1// "DELETE FROM UserProperties WHERE Proper"...
0x34cbe  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34cc3  ldloc.1
0x34cc4  ldloc.3
0x34cc5  ldstr    aRolescacheddat// "@RolesCachedDate"
0x34cca  ldstr    aRolescacheddat_0// "RolesCachedDate_"
0x34ccf  ldarg.0
0x34cd0  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34cd5  call     string [mscorlib]System.String::Concat(string, string)
0x34cda  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34cdf  ldloc.3
0x34ce0  ldloc.2
0x34ce1  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34ce6  ldloc.3
0x34ce7  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34cec  pop
0x34ced  leave.s  loc_34D11
0x34cef  pop
0x34cf0  ldloc.2
0x34cf1  brfalse.s loc_34CFB
0x34cf3  ldloc.2
0x34cf4  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x34cf9  ldnull
0x34cfa  stloc.2
0x34cfb  rethrow
0x34cfd  ldloc.2
0x34cfe  brfalse.s loc_34D06
0x34d00  ldloc.2
0x34d01  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x34d06  endfinally
0x34d07  ldloc.1
0x34d08  brfalse.s loc_34D10
0x34d0a  ldloc.1
0x34d0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34d10  endfinally
0x34d11  ret
```
