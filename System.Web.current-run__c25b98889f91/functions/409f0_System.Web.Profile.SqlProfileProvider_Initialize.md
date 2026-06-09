# System.Web.Profile.SqlProfileProvider::Initialize

- ea: `0x409f0`
- end: `0x40b2d`
- name: `System.Web.Profile.SqlProfileProvider::Initialize`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x24280`
- `0x34f20`
- `0x34fa0`
- `0x409f0`
- `0x58390`
- `0x583f0`
- `0x58700`

## string_xrefs

- `0x40a02`: `config`
- `0x40aba`: `commandTimeout`
- `0x40ace`: `commandTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x409f0  ldc.i4   0x12C
0x409f5  ldstr    aFeatureNotSupp// "Feature_not_supported_at_this_level"
0x409fa  call     void System.Web.HttpRuntime::CheckAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level, string errorMessageId)
0x409ff  ldarg.2
0x40a00  brtrue.s loc_40A0D
0x40a02  ldstr    aConfig// "config"
0x40a07  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x40a0c  throw
0x40a0d  ldarg.1
0x40a0e  brfalse.s loc_40A19
0x40a10  ldarg.1
0x40a11  callvirt instance int32 [mscorlib]System.String::get_Length()
0x40a16  ldc.i4.1
0x40a17  bge.s    loc_40A20
0x40a19  ldstr    aSqlprofileprov// "SqlProfileProvider"
0x40a1e  starg.s  1
0x40a20  ldarg.2
0x40a21  ldstr    aDescription// "description"
0x40a26  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x40a2b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40a30  brfalse.s loc_40A52
0x40a32  ldarg.2
0x40a33  ldstr    aDescription// "description"
0x40a38  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x40a3d  ldarg.2
0x40a3e  ldstr    aDescription// "description"
0x40a43  ldstr    aProfilesqlprov// "ProfileSqlProvider_description"
0x40a48  call     string System.Web.SR::GetString(string name)
0x40a4d  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x40a52  ldarg.0
0x40a53  ldarg.1
0x40a54  ldarg.2
0x40a55  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x40a5a  ldarg.0
0x40a5b  ldc.i4.0
0x40a5c  stfld    int32 System.Web.Profile.SqlProfileProvider::_SchemaVersionCheck
0x40a61  ldarg.0
0x40a62  ldarg.2
0x40a63  call     string System.Web.Util.SecUtility::GetConnectionString(class [System]System.Collections.Specialized.NameValueCollection config)
0x40a68  stfld    string System.Web.Profile.SqlProfileProvider::_sqlConnectionString
0x40a6d  ldarg.0
0x40a6e  ldarg.2
0x40a6f  ldstr    aApplicationnam// "applicationName"
0x40a74  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x40a79  stfld    string System.Web.Profile.SqlProfileProvider::_AppName
0x40a7e  ldarg.0
0x40a7f  ldfld    string System.Web.Profile.SqlProfileProvider::_AppName
0x40a84  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40a89  brfalse.s loc_40A96
0x40a8b  ldarg.0
0x40a8c  call     string System.Web.Util.SecUtility::GetDefaultAppName()
0x40a91  stfld    string System.Web.Profile.SqlProfileProvider::_AppName
0x40a96  ldarg.0
0x40a97  ldfld    string System.Web.Profile.SqlProfileProvider::_AppName
0x40a9c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x40aa1  ldc.i4   0x100
0x40aa6  ble.s    loc_40AB8
0x40aa8  ldstr    aProviderApplic// "Provider_application_name_too_long"
0x40aad  call     string System.Web.SR::GetString(string name)
0x40ab2  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x40ab7  throw
0x40ab8  ldarg.0
0x40ab9  ldarg.2
0x40aba  ldstr    aCommandtimeout// "commandTimeout"
0x40abf  ldc.i4.s 0x1E
0x40ac1  ldc.i4.1
0x40ac2  ldc.i4.0
0x40ac3  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x40ac8  stfld    int32 System.Web.Profile.SqlProfileProvider::_CommandTimeout
0x40acd  ldarg.2
0x40ace  ldstr    aCommandtimeout// "commandTimeout"
0x40ad3  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x40ad8  ldarg.2
0x40ad9  ldstr    aConnectionstri// "connectionStringName"
0x40ade  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x40ae3  ldarg.2
0x40ae4  ldstr    aConnectionstri_0// "connectionString"
0x40ae9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x40aee  ldarg.2
0x40aef  ldstr    aApplicationnam// "applicationName"
0x40af4  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x40af9  ldarg.2
0x40afa  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x40aff  ldc.i4.0
0x40b00  ble.s    loc_40B2C
0x40b02  ldarg.2
0x40b03  ldc.i4.0
0x40b04  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0x40b09  stloc.0
0x40b0a  ldloc.0
0x40b0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40b10  brtrue.s loc_40B2C
0x40b12  ldstr    aProviderUnreco// "Provider_unrecognized_attribute"
0x40b17  ldc.i4.1
0x40b18  newarr   [mscorlib]System.Object
0x40b1d  dup
0x40b1e  ldc.i4.0
0x40b1f  ldloc.0
0x40b20  stelem.ref
0x40b21  call     string System.Web.SR::GetString(string name, object[] args)
0x40b26  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x40b2b  throw
0x40b2c  ret
```
