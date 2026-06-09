# System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::Initialize

- ea: `0x33a20`
- end: `0x33bbc`
- name: `System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::Initialize`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x28210`
- `0x33a20`
- `0x33da0`
- `0x372f0`
- `0x37300`

## string_xrefs

- `0x33a23`: `config`
- `0x33a5a`: `serviceUri`
- `0x33b52`: `serviceUri`

## pseudocode

```c

```

## disassembly

```asm
0x33a20  ldarg.2
0x33a21  brtrue.s loc_33A2E
0x33a23  ldstr    aConfig// "config"
0x33a28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33a2d  throw
0x33a2e  ldarg.0
0x33a2f  ldarg.1
0x33a30  ldarg.2
0x33a31  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x33a36  ldarg.0
0x33a37  ldarg.2
0x33a38  ldstr    aCredentialspro// "credentialsProvider"
0x33a3d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33a42  stfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_GetCredentialsTypeName
0x33a47  ldarg.0
0x33a48  ldarg.2
0x33a49  ldstr    aConnectionstri// "connectionStringName"
0x33a4e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33a53  stfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33a58  ldarg.0
0x33a59  ldarg.2
0x33a5a  ldstr    aServiceuri// "serviceUri"
0x33a5f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33a64  call     instance void System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::set_ServiceUri(string value)
0x33a69  ldarg.0
0x33a6a  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33a6f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33a74  brfalse.s loc_33A83
0x33a76  ldarg.0
0x33a77  call     string System.Web.ClientServices.Providers.SqlHelper::GetDefaultConnectionString()
0x33a7c  stfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33a81  br.s     loc_33ACB
0x33a83  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x33a88  ldarg.0
0x33a89  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33a8e  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x33a93  brfalse.s loc_33ACB
0x33a95  ldarg.0
0x33a96  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x33a9b  ldarg.0
0x33a9c  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33aa1  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x33aa6  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ProviderName()
0x33aab  stfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionStringProvider
0x33ab0  ldarg.0
0x33ab1  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x33ab6  ldarg.0
0x33ab7  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33abc  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x33ac1  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ConnectionString()
0x33ac6  stfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33acb  ldarg.0
0x33acc  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x33ad1  call     int32 System.Web.ClientServices.Providers.SqlHelper::IsSpecialConnectionString(string connectionString)
0x33ad6  stloc.1
0x33ad7  ldloc.1
0x33ad8  ldc.i4.1
0x33ad9  beq.s    loc_33AE1
0x33adb  ldloc.1
0x33adc  ldc.i4.2
0x33add  beq.s    loc_33AEA
0x33adf  br.s     loc_33AF1
0x33ae1  ldarg.0
0x33ae2  ldc.i4.1
0x33ae3  stfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingFileSystemStore
0x33ae8  br.s     loc_33AF1
0x33aea  ldarg.0
0x33aeb  ldc.i4.1
0x33aec  stfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingIsolatedStore
0x33af1  ldarg.2
0x33af2  ldstr    aSavepasswordha// "savePasswordHashLocally"
0x33af7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33afc  stloc.0
0x33afd  ldloc.0
0x33afe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33b03  brtrue.s loc_33B1A
0x33b05  ldarg.0
0x33b06  ldloc.0
0x33b07  ldstr    aTrue// "true"
0x33b0c  ldc.i4.5
0x33b0d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x33b12  ldc.i4.0
0x33b13  ceq
0x33b15  stfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_SavePasswordHash
0x33b1a  ldarg.2
0x33b1b  ldstr    aSavepasswordha// "savePasswordHashLocally"
0x33b20  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b25  ldarg.2
0x33b26  ldstr    aName// "name"
0x33b2b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b30  ldarg.2
0x33b31  ldstr    aDescription// "description"
0x33b36  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b3b  ldarg.2
0x33b3c  ldstr    aCredentialspro// "credentialsProvider"
0x33b41  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b46  ldarg.2
0x33b47  ldstr    aConnectionstri// "connectionStringName"
0x33b4c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b51  ldarg.2
0x33b52  ldstr    aServiceuri// "serviceUri"
0x33b57  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33b5c  ldarg.2
0x33b5d  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x33b62  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x33b67  stloc.2
0x33b68  br.s     loc_33B9D
0x33b6a  ldloc.2
0x33b6b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x33b70  castclass [mscorlib]System.String
0x33b75  stloc.3
0x33b76  ldloc.3
0x33b77  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33b7c  brtrue.s loc_33B9D
0x33b7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33b83  call     string System.Web.Resources.AtlasWeb::get_AttributeNotRecognized()
0x33b88  ldc.i4.1
0x33b89  newarr   [mscorlib]System.Object
0x33b8e  dup
0x33b8f  ldc.i4.0
0x33b90  ldloc.3
0x33b91  stelem.ref
0x33b92  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x33b97  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33b9c  throw
0x33b9d  ldloc.2
0x33b9e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33ba3  brtrue.s loc_33B6A
0x33ba5  leave.s  loc_33BBB
0x33ba7  ldloc.2
0x33ba8  isinst   [mscorlib]System.IDisposable
0x33bad  stloc.s  4
0x33baf  ldloc.s  4
0x33bb1  brfalse.s loc_33BBA
0x33bb3  ldloc.s  4
0x33bb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33bba  endfinally
0x33bbb  ret
```
