# System.Web.ClientServices.Providers.ClientRoleProvider::Initialize

- ea: `0x34800`
- end: `0x349b0`
- name: `System.Web.ClientServices.Providers.ClientRoleProvider::Initialize`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x28210`
- `0x34800`
- `0x350d0`
- `0x372f0`
- `0x37300`

## string_xrefs

- `0x34803`: `config`
- `0x34818`: `serviceUri`
- `0x3493b`: `serviceUri`
- `0x34828`: `cacheTimeout`
- `0x34925`: `cacheTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x34800  ldarg.2
0x34801  brtrue.s loc_3480E
0x34803  ldstr    aConfig// "config"
0x34808  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3480d  throw
0x3480e  ldarg.0
0x3480f  ldarg.1
0x34810  ldarg.2
0x34811  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x34816  ldarg.0
0x34817  ldarg.2
0x34818  ldstr    aServiceuri// "serviceUri"
0x3481d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34822  call     instance void System.Web.ClientServices.Providers.ClientRoleProvider::set_ServiceUri(string value)
0x34827  ldarg.2
0x34828  ldstr    aCachetimeout// "cacheTimeout"
0x3482d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34832  stloc.0
0x34833  ldloc.0
0x34834  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34839  brtrue.s loc_3484C
0x3483b  ldarg.0
0x3483c  ldloc.0
0x3483d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34842  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x34847  stfld    int32 System.Web.ClientServices.Providers.ClientRoleProvider::_CacheTimeout
0x3484c  ldarg.0
0x3484d  ldarg.2
0x3484e  ldstr    aConnectionstri// "connectionStringName"
0x34853  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34858  stfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x3485d  ldarg.0
0x3485e  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34863  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34868  brfalse.s loc_34877
0x3486a  ldarg.0
0x3486b  call     string System.Web.ClientServices.Providers.SqlHelper::GetDefaultConnectionString()
0x34870  stfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34875  br.s     loc_348BF
0x34877  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x3487c  ldarg.0
0x3487d  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34882  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x34887  brfalse.s loc_348BF
0x34889  ldarg.0
0x3488a  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x3488f  ldarg.0
0x34890  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x34895  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x3489a  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ProviderName()
0x3489f  stfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionStringProvider
0x348a4  ldarg.0
0x348a5  call     class [System.Configuration]System.Configuration.ConnectionStringSettingsCollection [System.Configuration]System.Configuration.ConfigurationManager::get_ConnectionStrings()
0x348aa  ldarg.0
0x348ab  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x348b0  callvirt instance class [System.Configuration]System.Configuration.ConnectionStringSettings [System.Configuration]System.Configuration.ConnectionStringSettingsCollection::get_Item(string)
0x348b5  callvirt instance string [System.Configuration]System.Configuration.ConnectionStringSettings::get_ConnectionString()
0x348ba  stfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x348bf  ldarg.0
0x348c0  ldfld    string System.Web.ClientServices.Providers.ClientRoleProvider::_ConnectionString
0x348c5  call     int32 System.Web.ClientServices.Providers.SqlHelper::IsSpecialConnectionString(string connectionString)
0x348ca  stloc.1
0x348cb  ldloc.1
0x348cc  ldc.i4.1
0x348cd  beq.s    loc_348D5
0x348cf  ldloc.1
0x348d0  ldc.i4.2
0x348d1  beq.s    loc_348DE
0x348d3  br.s     loc_348E5
0x348d5  ldarg.0
0x348d6  ldc.i4.1
0x348d7  stfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingFileSystemStore
0x348dc  br.s     loc_348E5
0x348de  ldarg.0
0x348df  ldc.i4.1
0x348e0  stfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_UsingIsolatedStore
0x348e5  ldarg.2
0x348e6  ldstr    aHonorcookieexp// "honorCookieExpiry"
0x348eb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x348f0  stloc.0
0x348f1  ldloc.0
0x348f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x348f7  brtrue.s loc_3490E
0x348f9  ldarg.0
0x348fa  ldloc.0
0x348fb  ldstr    aTrue// "true"
0x34900  ldc.i4.5
0x34901  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x34906  ldc.i4.0
0x34907  ceq
0x34909  stfld    bool System.Web.ClientServices.Providers.ClientRoleProvider::_HonorCookieExpiry
0x3490e  ldarg.2
0x3490f  ldstr    aName// "name"
0x34914  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x34919  ldarg.2
0x3491a  ldstr    aDescription// "description"
0x3491f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x34924  ldarg.2
0x34925  ldstr    aCachetimeout// "cacheTimeout"
0x3492a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x3492f  ldarg.2
0x34930  ldstr    aConnectionstri// "connectionStringName"
0x34935  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x3493a  ldarg.2
0x3493b  ldstr    aServiceuri// "serviceUri"
0x34940  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x34945  ldarg.2
0x34946  ldstr    aHonorcookieexp// "honorCookieExpiry"
0x3494b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x34950  ldarg.2
0x34951  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x34956  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x3495b  stloc.2
0x3495c  br.s     loc_34991
0x3495e  ldloc.2
0x3495f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x34964  castclass [mscorlib]System.String
0x34969  stloc.3
0x3496a  ldloc.3
0x3496b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34970  brtrue.s loc_34991
0x34972  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34977  call     string System.Web.Resources.AtlasWeb::get_AttributeNotRecognized()
0x3497c  ldc.i4.1
0x3497d  newarr   [mscorlib]System.Object
0x34982  dup
0x34983  ldc.i4.0
0x34984  ldloc.3
0x34985  stelem.ref
0x34986  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3498b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x34990  throw
0x34991  ldloc.2
0x34992  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34997  brtrue.s loc_3495E
0x34999  leave.s  loc_349AF
0x3499b  ldloc.2
0x3499c  isinst   [mscorlib]System.IDisposable
0x349a1  stloc.s  4
0x349a3  ldloc.s  4
0x349a5  brfalse.s loc_349AE
0x349a7  ldloc.s  4
0x349a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x349ae  endfinally
0x349af  ret
```
