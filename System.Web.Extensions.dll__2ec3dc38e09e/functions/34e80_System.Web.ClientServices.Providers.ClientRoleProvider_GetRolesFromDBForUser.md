# System.Web.ClientServices.Providers.ClientRoleProvider::GetRolesFromDBForUser

- ea: `0x34e80`
- end: `0x35094`
- name: `System.Web.ClientServices.Providers.ClientRoleProvider::GetRolesFromDBForUser`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x349e0`

## callees

- `0x33690`
- `0x34e80`
- `0x37320`
- `0x37370`
- `0x37cb0`
- `0x37cd0`
- `0x380e0`

## string_xrefs

- `0x34f44`: `@RolesCachedDate`
- `0x34f49`: `RolesCachedDate_`
- `0x34f37`: `SELECT PropertyValue FROM UserProperties WHERE PropertyName = @RolesCachedDate`

## pseudocode

```c

```

## disassembly

```asm
0x34e80  ldarg.0
0x34e81  ldnull
0x34e82  stfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x34e87  ldarg.0
0x34e88  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34e8d  stfld    valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientRoleProvider::_CacheExpiryDate
0x34e92  ldarg.0
0x34e93  ldarg.1
0x34e94  stfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34e99  ldarg.0
0x34e9a  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingFileSystemStore
0x34e9f  brtrue.s loc_34EA9
0x34ea1  ldarg.0
0x34ea2  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34ea7  brfalse.s loc_34F04
0x34ea9  ldarg.1
0x34eaa  ldarg.0
0x34eab  ldfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x34eb0  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x34eb5  stloc.0
0x34eb6  ldloc.0
0x34eb7  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_Roles()
0x34ebc  brtrue.s loc_34EC0
0x34ebe  ldc.i4.0
0x34ebf  ret
0x34ec0  ldarg.0
0x34ec1  ldloc.0
0x34ec2  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_Roles()
0x34ec7  stfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x34ecc  ldarg.0
0x34ecd  ldloc.0
0x34ece  callvirt instance valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientData::get_RolesCachedDateUtc()
0x34ed3  stloc.1
0x34ed4  ldloca.s 1
0x34ed6  ldarg.0
0x34ed7  ldfld    int32 System.Web.ClientServices.Providers.ClientRoleProvider::_CacheTimeout
0x34edc  conv.r8
0x34edd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x34ee2  stfld    valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientRoleProvider::_CacheExpiryDate
0x34ee7  call     bool System.Web.ClientServices.ConnectivityStatus::get_IsOffline()
0x34eec  brtrue.s loc_34F02
0x34eee  ldarg.0
0x34eef  ldfld    valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientRoleProvider::_CacheExpiryDate
0x34ef4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34ef9  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x34efe  brfalse.s loc_34F02
0x34f00  ldc.i4.0
0x34f01  ret
0x34f02  ldc.i4.1
0x34f03  ret
0x34f04  ldarg.0
0x34f05  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34f0a  ldarg.0
0x34f0b  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34f10  ldarg.0
0x34f11  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionStringProvider
0x34f16  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x34f1b  stloc.2
0x34f1c  ldnull
0x34f1d  stloc.3
0x34f1e  ldloc.2
0x34f1f  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x34f24  stloc.3
0x34f25  ldloc.2
0x34f26  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34f2b  stloc.s  4
0x34f2d  ldloc.s  4
0x34f2f  ldloc.3
0x34f30  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34f35  ldloc.s  4
0x34f37  ldstr    aSelectProperty_2// "SELECT PropertyValue FROM UserPropertie"...
0x34f3c  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34f41  ldloc.2
0x34f42  ldloc.s  4
0x34f44  ldstr    aRolescacheddat// "@RolesCachedDate"
0x34f49  ldstr    aRolescacheddat_0// "RolesCachedDate_"
0x34f4e  ldarg.0
0x34f4f  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34f54  call     string [mscorlib]System.String::Concat(string, string)
0x34f59  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34f5e  ldloc.s  4
0x34f60  callvirt instance object [System.Data]System.Data.Common.DbCommand::ExecuteScalar()
0x34f65  isinst   [mscorlib]System.String
0x34f6a  stloc.s  5
0x34f6c  ldloc.s  5
0x34f6e  brtrue.s loc_34F78
0x34f70  ldc.i4.0
0x34f71  stloc.s  8
0x34f73  leave    loc_35091
0x34f78  ldloc.s  5
0x34f7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34f7f  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x34f84  stloc.s  6
0x34f86  ldarg.0
0x34f87  ldloc.s  6
0x34f89  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTimeUtc(int64)
0x34f8e  stloc.1
0x34f8f  ldloca.s 1
0x34f91  ldarg.0
0x34f92  ldfld    int32 System.Web.ClientServices.Providers.ClientRoleProvider::_CacheTimeout
0x34f97  conv.r8
0x34f98  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x34f9d  stfld    valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientRoleProvider::_CacheExpiryDate
0x34fa2  call     bool System.Web.ClientServices.ConnectivityStatus::get_IsOffline()
0x34fa7  brtrue.s loc_34FC3
0x34fa9  ldarg.0
0x34faa  ldfld    valuetype [mscorlib]System.DateTime System.Web.ClientServices.Providers.ClientRoleProvider::_CacheExpiryDate
0x34faf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34fb4  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x34fb9  brfalse.s loc_34FC3
0x34fbb  ldc.i4.0
0x34fbc  stloc.s  8
0x34fbe  leave    loc_35091
0x34fc3  ldloc.2
0x34fc4  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34fc9  stloc.s  4
0x34fcb  ldloc.s  4
0x34fcd  ldloc.3
0x34fce  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34fd3  ldloc.s  4
0x34fd5  ldstr    aSelectRolename// "SELECT RoleName FROM Roles WHERE UserNa"...
0x34fda  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34fdf  ldloc.2
0x34fe0  ldloc.s  4
0x34fe2  ldstr    aUsername_0// "@UserName"
0x34fe7  ldarg.0
0x34fe8  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_CurrentUser
0x34fed  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34ff2  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x34ff7  stloc.s  7
0x34ff9  ldloc.s  4
0x34ffb  callvirt instance class [System.Data]System.Data.Common.DbDataReader [System.Data]System.Data.Common.DbCommand::ExecuteReader()
0x35000  stloc.s  9
0x35002  br.s     loc_35014
0x35004  ldloc.s  7
0x35006  ldloc.s  9
0x35008  ldc.i4.0
0x35009  callvirt instance string [System.Data]System.Data.Common.DbDataReader::GetString(int32)
0x3500e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x35013  pop
0x35014  ldloc.s  9
0x35016  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x3501b  brtrue.s loc_35004
0x3501d  leave.s  loc_3502B
0x3501f  ldloc.s  9
0x35021  brfalse.s loc_3502A
0x35023  ldloc.s  9
0x35025  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3502a  endfinally
0x3502b  ldarg.0
0x3502c  ldloc.s  7
0x3502e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x35033  newarr   [mscorlib]System.String
0x35038  stfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x3503d  ldc.i4.0
0x3503e  stloc.s  0xA
0x35040  br.s     loc_3505F
0x35042  ldarg.0
0x35043  ldfld    string[] System.Web.ClientServices.Providers.ClientRoleProvider::_Roles
0x35048  ldloc.s  0xA
0x3504a  ldloc.s  7
0x3504c  ldloc.s  0xA
0x3504e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x35053  castclass [mscorlib]System.String
0x35058  stelem.ref
0x35059  ldloc.s  0xA
0x3505b  ldc.i4.1
0x3505c  add
0x3505d  stloc.s  0xA
0x3505f  ldloc.s  0xA
0x35061  ldloc.s  7
0x35063  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x35068  blt.s    loc_35042
0x3506a  ldc.i4.1
0x3506b  stloc.s  8
0x3506d  leave.s  loc_35091
0x3506f  pop
0x35070  ldloc.3
0x35071  brfalse.s loc_3507B
0x35073  ldloc.3
0x35074  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x35079  ldnull
0x3507a  stloc.3
0x3507b  rethrow
0x3507d  ldloc.3
0x3507e  brfalse.s loc_35086
0x35080  ldloc.3
0x35081  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x35086  endfinally
0x35087  ldloc.2
0x35088  brfalse.s loc_35090
0x3508a  ldloc.2
0x3508b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35090  endfinally
0x35091  ldloc.s  8
0x35093  ret
```
