# System.Web.ClientServices.Providers.ClientRoleProvider::StoreRolesForCurrentUser

- ea: `0x34d20`
- end: `0x34e74`
- name: `System.Web.ClientServices.Providers.ClientRoleProvider::StoreRolesForCurrentUser`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x349e0`

## callees

- `0x34c20`
- `0x34d20`
- `0x37320`
- `0x37370`
- `0x37cc0`
- `0x37ce0`
- `0x37dd0`
- `0x380e0`

## string_xrefs

- `0x34dff`: `@RolesCachedDate`
- `0x34e04`: `RolesCachedDate_`
- `0x34df3`: `INSERT INTO UserProperties (PropertyName, PropertyValue) VALUES(@RolesCachedDate, @Date)`

## pseudocode

```c

```

## disassembly

```asm
0x34d20  ldarg.0
0x34d21  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingFileSystemStore
0x34d26  brtrue.s loc_34D30
0x34d28  ldarg.0
0x34d29  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34d2e  brfalse.s loc_34D60
0x34d30  ldarg.0
0x34d31  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34d36  ldarg.0
0x34d37  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34d3c  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x34d41  stloc.1
0x34d42  ldloc.1
0x34d43  ldarg.0
0x34d44  ldfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x34d49  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_Roles(string[] value)
0x34d4e  ldloc.1
0x34d4f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34d54  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_RolesCachedDateUtc(valuetype [mscorlib]System.DateTime value)
0x34d59  ldloc.1
0x34d5a  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x34d5f  ret
0x34d60  ldarg.0
0x34d61  call     instance void System.Web.ClientServices.Providers.ClientRoleProvider::RemoveRolesFromDB()
0x34d66  ldnull
0x34d67  stloc.0
0x34d68  ldarg.0
0x34d69  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34d6e  ldarg.0
0x34d6f  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34d74  ldarg.0
0x34d75  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionStringProvider
0x34d7a  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x34d7f  stloc.2
0x34d80  ldloc.2
0x34d81  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x34d86  stloc.0
0x34d87  ldnull
0x34d88  stloc.3
0x34d89  ldarg.0
0x34d8a  ldfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x34d8f  stloc.s  4
0x34d91  ldc.i4.0
0x34d92  stloc.s  5
0x34d94  br.s     loc_34DE3
0x34d96  ldloc.s  4
0x34d98  ldloc.s  5
0x34d9a  ldelem.ref
0x34d9b  stloc.s  6
0x34d9d  ldloc.2
0x34d9e  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34da3  stloc.3
0x34da4  ldloc.3
0x34da5  ldstr    aInsertIntoRole// "INSERT INTO Roles(UserName, RoleName) V"...
0x34daa  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34daf  ldloc.2
0x34db0  ldloc.3
0x34db1  ldstr    aUsername_0// "@UserName"
0x34db6  ldarg.0
0x34db7  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34dbc  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34dc1  ldloc.2
0x34dc2  ldloc.3
0x34dc3  ldstr    aRolename// "@RoleName"
0x34dc8  ldloc.s  6
0x34dca  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34dcf  ldloc.3
0x34dd0  ldloc.0
0x34dd1  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34dd6  ldloc.3
0x34dd7  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34ddc  pop
0x34ddd  ldloc.s  5
0x34ddf  ldc.i4.1
0x34de0  add
0x34de1  stloc.s  5
0x34de3  ldloc.s  5
0x34de5  ldloc.s  4
0x34de7  ldlen
0x34de8  conv.i4
0x34de9  blt.s    loc_34D96
0x34deb  ldloc.2
0x34dec  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34df1  stloc.3
0x34df2  ldloc.3
0x34df3  ldstr    aInsertIntoUser_1// "INSERT INTO UserProperties (PropertyNam"...
0x34df8  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34dfd  ldloc.2
0x34dfe  ldloc.3
0x34dff  ldstr    aRolescacheddat// "@RolesCachedDate"
0x34e04  ldstr    aRolescacheddat_0// "RolesCachedDate_"
0x34e09  ldarg.0
0x34e0a  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34e0f  call     string [mscorlib]System.String::Concat(string, string)
0x34e14  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34e19  ldloc.2
0x34e1a  ldloc.3
0x34e1b  ldstr    aDate_1// "@Date"
0x34e20  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34e25  stloc.s  7
0x34e27  ldloca.s 7
0x34e29  call     instance int64 [mscorlib]System.DateTime::ToFileTimeUtc()
0x34e2e  stloc.s  8
0x34e30  ldloca.s 8
0x34e32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34e37  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x34e3c  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34e41  ldloc.3
0x34e42  ldloc.0
0x34e43  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34e48  ldloc.3
0x34e49  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34e4e  pop
0x34e4f  leave.s  loc_34E73
0x34e51  pop
0x34e52  ldloc.0
0x34e53  brfalse.s loc_34E5D
0x34e55  ldloc.0
0x34e56  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x34e5b  ldnull
0x34e5c  stloc.0
0x34e5d  rethrow
0x34e5f  ldloc.0
0x34e60  brfalse.s loc_34E68
0x34e62  ldloc.0
0x34e63  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x34e68  endfinally
0x34e69  ldloc.2
0x34e6a  brfalse.s loc_34E72
0x34e6c  ldloc.2
0x34e6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34e72  endfinally
0x34e73  ret
```
