# System.Web.Hosting.HostingEnvironment::get_CacheStoreProviderSettings

- ea: `0x161f00`
- end: `0x161ff7`
- name: `System.Web.Hosting.HostingEnvironment::get_CacheStoreProviderSettings`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x186750`
- `0x186820`

## callees

- `0x34fa0`
- `0x13d880`
- `0x13d8a0`
- `0x15c330`
- `0x161f00`

## string_xrefs

- `0x161f21`: `system.web/caching/cache`
- `0x161fcf`: `.defaultObjectCacheProvider`

## pseudocode

```c

```

## disassembly

```asm
0x161f00  ldsfld   class [System]System.Collections.Specialized.NameValueCollection System.Web.Hosting.HostingEnvironment::_cacheProviderSettings
0x161f05  brtrue   loc_161FE3
0x161f0a  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x161f0f  callvirt instance bool [mscorlib]System.AppDomain::IsDefaultAppDomain()
0x161f14  brfalse  loc_161FCA
0x161f19  ldnull
0x161f1a  call     class [System.Configuration]System.Configuration.Configuration System.Web.Configuration.WebConfigurationManager::OpenWebConfiguration(string path)
0x161f1f  stloc.0
0x161f20  ldloc.0
0x161f21  ldstr    aSystemWebCachi// "system.web/caching/cache"
0x161f26  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x161f2b  castclass System.Web.Configuration.CacheSection
0x161f30  stloc.1
0x161f31  ldloc.1
0x161f32  brfalse  loc_161FE3
0x161f37  ldloc.1
0x161f38  callvirt instance string System.Web.Configuration.CacheSection::get_DefaultProvider()
0x161f3d  brfalse  loc_161FE3
0x161f42  ldloc.1
0x161f43  callvirt instance string System.Web.Configuration.CacheSection::get_DefaultProvider()
0x161f48  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x161f4d  brtrue   loc_161FE3
0x161f52  ldloc.1
0x161f53  callvirt instance class [System.Configuration]System.Configuration.ProviderSettingsCollection System.Web.Configuration.CacheSection::get_Providers()
0x161f58  stloc.2
0x161f59  ldloc.2
0x161f5a  brfalse.s loc_161F65
0x161f5c  ldloc.2
0x161f5d  callvirt instance int32 [System.Configuration]System.Configuration.ConfigurationElementCollection::get_Count()
0x161f62  ldc.i4.1
0x161f63  bge.s    loc_161F75
0x161f65  ldstr    aDefProviderNot// "Def_provider_not_found"
0x161f6a  call     string System.Web.SR::GetString(string name)
0x161f6f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x161f74  throw
0x161f75  ldloc.2
0x161f76  ldloc.1
0x161f77  callvirt instance string System.Web.Configuration.CacheSection::get_DefaultProvider()
0x161f7c  callvirt instance class [System.Configuration]System.Configuration.ProviderSettings [System.Configuration]System.Configuration.ProviderSettingsCollection::get_Item(string)
0x161f81  stloc.3
0x161f82  ldloc.3
0x161f83  brtrue.s loc_161F95
0x161f85  ldstr    aDefProviderNot// "Def_provider_not_found"
0x161f8a  call     string System.Web.SR::GetString(string name)
0x161f8f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x161f94  throw
0x161f95  ldloc.3
0x161f96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ProviderSettings::get_Parameters()
0x161f9b  stloc.s  4
0x161f9d  ldloc.s  4
0x161f9f  ldstr    aName// "name"
0x161fa4  ldloc.3
0x161fa5  callvirt instance string [System.Configuration]System.Configuration.ProviderSettings::get_Name()
0x161faa  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x161faf  ldloc.s  4
0x161fb1  ldstr    aType// "type"
0x161fb6  ldloc.3
0x161fb7  callvirt instance string [System.Configuration]System.Configuration.ProviderSettings::get_Type()
0x161fbc  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x161fc1  ldloc.s  4
0x161fc3  stsfld   class [System]System.Collections.Specialized.NameValueCollection System.Web.Hosting.HostingEnvironment::_cacheProviderSettings
0x161fc8  br.s     loc_161FE3
0x161fca  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x161fcf  ldstr    aDefaultobjectc// ".defaultObjectCacheProvider"
0x161fd4  callvirt instance object [mscorlib]System.AppDomain::GetData(string)
0x161fd9  isinst   [System]System.Collections.Specialized.NameValueCollection
0x161fde  stsfld   class [System]System.Collections.Specialized.NameValueCollection System.Web.Hosting.HostingEnvironment::_cacheProviderSettings
0x161fe3  ldsfld   class [System]System.Collections.Specialized.NameValueCollection System.Web.Hosting.HostingEnvironment::_cacheProviderSettings
0x161fe8  brfalse.s loc_161FF5
0x161fea  ldsfld   class [System]System.Collections.Specialized.NameValueCollection System.Web.Hosting.HostingEnvironment::_cacheProviderSettings
0x161fef  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(class [System]System.Collections.Specialized.NameValueCollection)
0x161ff4  ret
0x161ff5  ldnull
0x161ff6  ret
```
