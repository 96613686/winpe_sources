# System.Web.ClientServices.Providers.ClientSettingsProvider::Initialize

- ea: `0x35330`
- end: `0x35524`
- name: `System.Web.ClientServices.Providers.ClientSettingsProvider::Initialize`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x28210`
- `0x35330`
- `0x35840`
- `0x372f0`
- `0x37300`

## string_xrefs

- `0x35407`: `serviceUri`
- `0x35498`: `serviceUri`
- `0x3533b`: `ClientSettingsProvider.ServiceUri`

## pseudocode

```c

```

## disassembly

```asm
0x35330  ldc.i4.0
0x35331  stsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x35336  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x3533b  ldstr    aClientsettings// "ClientSettingsProvider.ServiceUri"
0x35340  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x35345  stloc.0
0x35346  ldloc.0
0x35347  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3534c  brtrue.s loc_35354
0x3534e  ldloc.0
0x3534f  call     void System.Web.ClientServices.Providers.ClientSettingsProvider::set_ServiceUri(string value)
0x35354  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x35359  ldstr    aClientsettings_0// "ClientSettingsProvider.ConnectionString"...
0x3535e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x35363  stloc.0
0x35364  ldloc.0
0x35365  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3536a  brtrue.s loc_353B0
0x3536c  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x35371  ldloc.0
0x35372  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x35377  brfalse.s loc_353A7
0x35379  ldarg.0
0x3537a  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x3537f  ldloc.0
0x35380  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x35385  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ProviderName()
0x3538a  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionStringProvider
0x3538f  ldarg.0
0x35390  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x35395  ldloc.0
0x35396  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x3539b  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ConnectionString()
0x353a0  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x353a5  br.s     loc_353BB
0x353a7  ldarg.0
0x353a8  ldloc.0
0x353a9  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x353ae  br.s     loc_353BB
0x353b0  ldarg.0
0x353b1  call     string System.Web.ClientServices.Providers.SqlHelper::GetDefaultConnectionString()
0x353b6  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x353bb  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x353c0  ldstr    aClientsettings_1// "ClientSettingsProvider.HonorCookieExpir"...
0x353c5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x353ca  stloc.0
0x353cb  ldloc.0
0x353cc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x353d1  brtrue.s loc_353E8
0x353d3  ldarg.0
0x353d4  ldloc.0
0x353d5  ldstr    aTrue// "true"
0x353da  ldc.i4.5
0x353db  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x353e0  ldc.i4.0
0x353e1  ceq
0x353e3  stfld    bool System.Web.ClientServices.Providers.ClientSettingsProvider::_HonorCookieExpiry
0x353e8  ldarg.1
0x353e9  brtrue.s loc_353F8
0x353eb  ldarg.0
0x353ec  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x353f1  callvirt instance string [mscorlib]System.Object::ToString()
0x353f6  starg.s  1
0x353f8  ldarg.0
0x353f9  ldarg.1
0x353fa  ldarg.2
0x353fb  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x35400  ldarg.2
0x35401  brfalse  loc_354FE
0x35406  ldarg.2
0x35407  ldstr    aServiceuri// "serviceUri"
0x3540c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x35411  stloc.0
0x35412  ldloc.0
0x35413  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35418  brtrue.s loc_35420
0x3541a  ldloc.0
0x3541b  call     void System.Web.ClientServices.Providers.ClientSettingsProvider::set_ServiceUri(string value)
0x35420  ldarg.2
0x35421  ldstr    aConnectionstri// "connectionStringName"
0x35426  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3542b  stloc.0
0x3542c  ldloc.0
0x3542d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35432  brtrue.s loc_35476
0x35434  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x35439  ldloc.0
0x3543a  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x3543f  brfalse.s loc_3546F
0x35441  ldarg.0
0x35442  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x35447  ldloc.0
0x35448  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x3544d  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ProviderName()
0x35452  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionStringProvider
0x35457  ldarg.0
0x35458  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x3545d  ldloc.0
0x3545e  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x35463  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ConnectionString()
0x35468  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x3546d  br.s     loc_35476
0x3546f  ldarg.0
0x35470  ldloc.0
0x35471  stfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x35476  ldarg.2
0x35477  ldstr    aName// "name"
0x3547c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x35481  ldarg.2
0x35482  ldstr    aDescription// "description"
0x35487  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x3548c  ldarg.2
0x3548d  ldstr    aConnectionstri// "connectionStringName"
0x35492  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x35497  ldarg.2
0x35498  ldstr    aServiceuri// "serviceUri"
0x3549d  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x354a2  ldarg.2
0x354a3  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x354a8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x354ad  stloc.1
0x354ae  br.s     loc_354E3
0x354b0  ldloc.1
0x354b1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x354b6  castclass [mscorlib]System.String
0x354bb  stloc.2
0x354bc  ldloc.2
0x354bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x354c2  brtrue.s loc_354E3
0x354c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x354c9  call     string System.Web.Resources.AtlasWeb::get_AttributeNotRecognized()
0x354ce  ldc.i4.1
0x354cf  newarr   [mscorlib]System.Object
0x354d4  dup
0x354d5  ldc.i4.0
0x354d6  ldloc.2
0x354d7  stelem.ref
0x354d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x354dd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x354e2  throw
0x354e3  ldloc.1
0x354e4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x354e9  brtrue.s loc_354B0
0x354eb  leave.s  loc_354FE
0x354ed  ldloc.1
0x354ee  isinst   [mscorlib]System.IDisposable
0x354f3  stloc.3
0x354f4  ldloc.3
0x354f5  brfalse.s loc_354FD
0x354f7  ldloc.3
0x354f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x354fd  endfinally
0x354fe  ldarg.0
0x354ff  ldfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionString
0x35504  call     int32 System.Web.ClientServices.Providers.SqlHelper::IsSpecialConnectionString(string connectionString)
0x35509  stloc.s  4
0x3550b  ldloc.s  4
0x3550d  ldc.i4.1
0x3550e  beq.s    loc_35516
0x35510  ldloc.s  4
0x35512  ldc.i4.2
0x35513  beq.s    loc_3551D
0x35515  ret
0x35516  ldc.i4.1
0x35517  stsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingFileSystemStore
0x3551c  ret
0x3551d  ldc.i4.1
0x3551e  stsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x35523  ret
```
