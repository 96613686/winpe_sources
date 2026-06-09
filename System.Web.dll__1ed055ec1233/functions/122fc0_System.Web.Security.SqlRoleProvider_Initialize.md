# System.Web.Security.SqlRoleProvider::Initialize

- ea: `0x122fc0`
- end: `0x1230f9`
- name: `System.Web.Security.SqlRoleProvider::Initialize`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x24280`
- `0x34f20`
- `0x34fa0`
- `0x58390`
- `0x583f0`
- `0x58700`
- `0x122fc0`

## string_xrefs

- `0x122fd2`: `config`
- `0x12302f`: `commandTimeout`
- `0x1230bb`: `commandTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x122fc0  ldc.i4   0x12C
0x122fc5  ldstr    aFeatureNotSupp// "Feature_not_supported_at_this_level"
0x122fca  call     void System.Web.HttpRuntime::CheckAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level, string errorMessageId)
0x122fcf  ldarg.2
0x122fd0  brtrue.s loc_122FDD
0x122fd2  ldstr    aConfig// "config"
0x122fd7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x122fdc  throw
0x122fdd  ldarg.1
0x122fde  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x122fe3  brfalse.s loc_122FEC
0x122fe5  ldstr    aSqlroleprovide// "SqlRoleProvider"
0x122fea  starg.s  1
0x122fec  ldarg.2
0x122fed  ldstr    aDescription// "description"
0x122ff2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x122ff7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x122ffc  brfalse.s loc_12301E
0x122ffe  ldarg.2
0x122fff  ldstr    aDescription// "description"
0x123004  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x123009  ldarg.2
0x12300a  ldstr    aDescription// "description"
0x12300f  ldstr    aRolesqlprovide// "RoleSqlProvider_description"
0x123014  call     string System.Web.SR::GetString(string name)
0x123019  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x12301e  ldarg.0
0x12301f  ldarg.1
0x123020  ldarg.2
0x123021  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x123026  ldarg.0
0x123027  ldc.i4.0
0x123028  stfld    int32 System.Web.Security.SqlRoleProvider::_SchemaVersionCheck
0x12302d  ldarg.0
0x12302e  ldarg.2
0x12302f  ldstr    aCommandtimeout// "commandTimeout"
0x123034  ldc.i4.s 0x1E
0x123036  ldc.i4.1
0x123037  ldc.i4.0
0x123038  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x12303d  stfld    int32 System.Web.Security.SqlRoleProvider::_CommandTimeout
0x123042  ldarg.0
0x123043  ldarg.2
0x123044  call     string System.Web.Util.SecUtility::GetConnectionString(class [System]System.Collections.Specialized.NameValueCollection config)
0x123049  stfld    string System.Web.Security.SqlRoleProvider::_sqlConnectionString
0x12304e  ldarg.0
0x12304f  ldarg.2
0x123050  ldstr    aApplicationnam// "applicationName"
0x123055  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12305a  stfld    string System.Web.Security.SqlRoleProvider::_AppName
0x12305f  ldarg.0
0x123060  ldfld    string System.Web.Security.SqlRoleProvider::_AppName
0x123065  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12306a  brfalse.s loc_123077
0x12306c  ldarg.0
0x12306d  call     string System.Web.Util.SecUtility::GetDefaultAppName()
0x123072  stfld    string System.Web.Security.SqlRoleProvider::_AppName
0x123077  ldarg.0
0x123078  ldfld    string System.Web.Security.SqlRoleProvider::_AppName
0x12307d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123082  ldc.i4   0x100
0x123087  ble.s    loc_123099
0x123089  ldstr    aProviderApplic// "Provider_application_name_too_long"
0x12308e  call     string System.Web.SR::GetString(string name)
0x123093  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x123098  throw
0x123099  ldarg.2
0x12309a  ldstr    aConnectionstri_0// "connectionString"
0x12309f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1230a4  ldarg.2
0x1230a5  ldstr    aConnectionstri// "connectionStringName"
0x1230aa  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1230af  ldarg.2
0x1230b0  ldstr    aApplicationnam// "applicationName"
0x1230b5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1230ba  ldarg.2
0x1230bb  ldstr    aCommandtimeout// "commandTimeout"
0x1230c0  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1230c5  ldarg.2
0x1230c6  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x1230cb  ldc.i4.0
0x1230cc  ble.s    loc_1230F8
0x1230ce  ldarg.2
0x1230cf  ldc.i4.0
0x1230d0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0x1230d5  stloc.0
0x1230d6  ldloc.0
0x1230d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1230dc  brtrue.s loc_1230F8
0x1230de  ldstr    aProviderUnreco// "Provider_unrecognized_attribute"
0x1230e3  ldc.i4.1
0x1230e4  newarr   [mscorlib]System.Object
0x1230e9  dup
0x1230ea  ldc.i4.0
0x1230eb  ldloc.0
0x1230ec  stelem.ref
0x1230ed  call     string System.Web.SR::GetString(string name, object[] args)
0x1230f2  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1230f7  throw
0x1230f8  ret
```
