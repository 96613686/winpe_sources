# System.Web.Hosting.ApplicationManager::CreateAppDomainWithHostingEnvironment

- ea: `0x15f4b0`
- end: `0x15fed3`
- name: `System.Web.Hosting.ApplicationManager::CreateAppDomainWithHostingEnvironment`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x15f480`

## callees

- `0x243e0`
- `0x29c10`
- `0x29d90`
- `0x30230`
- `0x30f70`
- `0x30ff0`
- `0x315d0`
- `0x34f20`
- `0x34fa0`
- `0x4eda0`
- `0x4ee60`
- `0x58dd0`
- `0x58ff0`
- `0x13d880`
- `0x13d8a0`
- `0x140f60`
- `0x142e20`
- `0x149de0`
- `0x14a220`
- `0x14a2d0`
- `0x1506b0`
- `0x1507a0`
- `0x1507d0`
- `0x150830`
- `0x15a2d0`
- `0x15a370`
- `0x15a3b0`
- `0x15c350`
- `0x15f4b0`
- `0x15fee0`
- `0x15ffb0`
- `0x15ffc0`
- `0x1603d0`
- `0x160460`
- `0x1604b0`
- `0x160650`
- `0x160680`
- `0x1608f0`
- `0x160950`
- `0x160980`
- `0x1609a0`
- `0x1609c0`
- `0x1609d0`
- `0x160ca0`
- `0x160cb0`
- `0x162770`
- `0x162780`
- `0x162790`
- `0x1627a0`
- `0x1627c0`

## string_xrefs

- `0x15fadb`: `system.web/compilation`
- `0x15f6e3`: `Config_section_not_present`
- `0x15fa4b`: `Config_section_not_present`
- `0x15f77c`: `aspnet:UseTaskFriendlySynchronizationContext`
- `0x15fac8`: `system.web/securityPolicy`
- `0x15f918`: `system.web/caching/cache`
- `0x15f585`: `System.Web.Extensions, PublicKey=0024000004800000940000000602000000240000525341310004000001000100b5fc90e7027f67871e773a8fde8938c81dd402ba65b9201d60593e96c492651e889cc13f1415ebb53fac1131ae0bd333c5ee6021672d9718ea31a8aebd0da0072f25d87dba6fc90ffd598ed4da35e44c398c454307e8e33b8426143daec9f596836f97c8f74750e5975c64e2189f45def46b2a2b1247adc3652bf5c308055da9`
- `0x15f5ad`: `System.Web.ApplicationServices, PublicKey=0024000004800000940000000602000000240000525341310004000001000100b5fc90e7027f67871e773a8fde8938c81dd402ba65b9201d60593e96c492651e889cc13f1415ebb53fac1131ae0bd333c5ee6021672d9718ea31a8aebd0da0072f25d87dba6fc90ffd598ed4da35e44c398c454307e8e33b8426143daec9f596836f97c8f74750e5975c64e2189f45def46b2a2b1247adc3652bf5c308055da9`
- `0x15f5ed`: `ConfigurationBuilders.IgnoreLoadFailure`
- `0x15f8e2`: `aspnet:DisableFcnDaclRead`
- `0x15f9c9`: `.defaultObjectCacheProvider`
- `0x15fdbb`: `Cannot_create_AppDomain`
- `0x15fe94`: `Cannot_create_HostEnv`

## pseudocode

```c

```

## disassembly

```asm
0x15f4b0  ldarg.2
0x15f4b1  callvirt instance string System.Web.Hosting.IApplicationHost::GetPhysicalPath()
0x15f4b6  stloc.0
0x15f4b7  ldloc.0
0x15f4b8  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x15f4bd  call     bool System.Web.Util.StringUtil::StringEndsWith(string s, char c)
0x15f4c2  brtrue.s loc_15F4D9
0x15f4c4  ldloc.0
0x15f4c5  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x15f4ca  stloc.s  0x20
0x15f4cc  ldloca.s 0x20
0x15f4ce  call     instance string [mscorlib]System.Char::ToString()
0x15f4d3  call     string [mscorlib]System.String::Concat(string, string)
0x15f4d8  stloc.0
0x15f4d9  ldarg.1
0x15f4da  call     string System.Web.Hosting.ApplicationManager::ConstructAppDomainId(string id)
0x15f4df  stloc.1
0x15f4e0  ldarg.1
0x15f4e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f4e6  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x15f4eb  ldloc.0
0x15f4ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f4f1  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x15f4f6  call     string [mscorlib]System.String::Concat(string, string)
0x15f4fb  call     int32 System.Web.Util.StringUtil::GetStringHashCode(string s)
0x15f500  stloc.s  0x21
0x15f502  ldloca.s 0x21
0x15f504  ldstr    aX// "x"
0x15f509  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f50e  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x15f513  stloc.2
0x15f514  ldarg.2
0x15f515  callvirt instance string System.Web.Hosting.IApplicationHost::GetVirtualPath()
0x15f51a  call     class System.Web.VirtualPath System.Web.VirtualPath::Create(string virtualPath)
0x15f51f  stloc.3
0x15f520  ldc.i4.s 0x14
0x15f522  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x15f527  stloc.s  4
0x15f529  newobj   instance void [mscorlib]System.AppDomainSetup::.ctor()
0x15f52e  stloc.s  5
0x15f530  newobj   instance void AppDomainSwitches::.ctor()
0x15f535  stloc.s  6
0x15f537  ldloc.1
0x15f538  ldarg.1
0x15f539  ldloc.2
0x15f53a  ldloc.0
0x15f53b  ldloc.3
0x15f53c  ldloc.s  5
0x15f53e  ldloc.s  4
0x15f540  call     void System.Web.Hosting.ApplicationManager::PopulateDomainBindings(string domainId, string appId, string appName, string appPath, class System.Web.VirtualPath appVPath, class [mscorlib]System.AppDomainSetup setup, class [mscorlib]System.Collections.IDictionary dict)
0x15f545  ldnull
0x15f546  stloc.s  7
0x15f548  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x15f54d  stloc.s  8
0x15f54f  ldnull
0x15f550  stloc.s  9
0x15f552  ldarg.2
0x15f553  callvirt instance string System.Web.Hosting.IApplicationHost::GetSiteID()
0x15f558  stloc.s  0xA
0x15f55a  ldloc.3
0x15f55b  callvirt instance string System.Web.VirtualPath::get_VirtualPathStringNoTrailingSlash()
0x15f560  stloc.s  0xB
0x15f562  ldc.i4.0
0x15f563  stloc.s  0xC
0x15f565  ldnull
0x15f566  stloc.s  0xD
0x15f568  ldnull
0x15f569  stloc.s  0xE
0x15f56b  ldnull
0x15f56c  stloc.s  0xF
0x15f56e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Policy.StrongName>::.ctor()
0x15f573  stloc.s  0x10
0x15f575  ldc.i4.7
0x15f576  newarr   [mscorlib]System.String
0x15f57b  dup
0x15f57c  ldc.i4.0
0x15f57d  ldstr    aSystemWebPubli// "System.Web, PublicKey=00240000048000009"...
0x15f582  stelem.ref
0x15f583  dup
0x15f584  ldc.i4.1
0x15f585  ldstr    aSystemWebExten// "System.Web.Extensions, PublicKey=002400"...
0x15f58a  stelem.ref
0x15f58b  dup
0x15f58c  ldc.i4.2
0x15f58d  ldstr    aSystemWebAbstr// "System.Web.Abstractions, PublicKey=0024"...
0x15f592  stelem.ref
0x15f593  dup
0x15f594  ldc.i4.3
0x15f595  ldstr    aSystemWebRouti// "System.Web.Routing, PublicKey=002400000"...
0x15f59a  stelem.ref
0x15f59b  dup
0x15f59c  ldc.i4.4
0x15f59d  ldstr    aSystemWebDynam_0// "System.Web.DynamicData, PublicKey=00240"...
0x15f5a2  stelem.ref
0x15f5a3  dup
0x15f5a4  ldc.i4.5
0x15f5a5  ldstr    aSystemWebDatav// "System.Web.DataVisualization, PublicKey"...
0x15f5aa  stelem.ref
0x15f5ab  dup
0x15f5ac  ldc.i4.6
0x15f5ad  ldstr    aSystemWebAppli// "System.Web.ApplicationServices, PublicK"...
0x15f5b2  stelem.ref
0x15f5b3  stloc.s  0x11
0x15f5b5  ldnull
0x15f5b6  stloc.s  0x12
0x15f5b8  ldnull
0x15f5b9  stloc.s  0x13
0x15f5bb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x15f5c0  stloc.s  0x14
0x15f5c2  ldc.i4.0
0x15f5c3  stloc.s  0x15
0x15f5c5  ldarg.3
0x15f5c6  brfalse.s loc_15F5E1
0x15f5c8  ldarg.3
0x15f5c9  callvirt instance valuetype System.Web.Hosting.HostingEnvironmentFlags System.Web.Hosting.HostingEnvironmentParameters::get_HostingFlags()
0x15f5ce  stloc.s  0x15
0x15f5d0  ldloc.s  0x15
0x15f5d2  ldc.i4.8
0x15f5d3  and
0x15f5d4  brfalse.s loc_15F5E1
0x15f5d6  ldc.i4.1
0x15f5d7  stloc.s  0xC
0x15f5d9  ldloc.s  5
0x15f5db  ldc.i4.3
0x15f5dc  callvirt instance void [mscorlib]System.AppDomainSetup::set_LoaderOptimization(valuetype [mscorlib]System.LoaderOptimization)
0x15f5e1  nop
0x15f5e2  ldc.i4.0
0x15f5e3  stloc.s  0x22
0x15f5e5  ldc.i4.0
0x15f5e6  stloc.s  0x23
0x15f5e8  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x15f5ed  ldstr    aConfigurationb// "ConfigurationBuilders.IgnoreLoadFailure"
0x15f5f2  ldc.i4.1
0x15f5f3  box      [mscorlib]System.Boolean
0x15f5f8  callvirt instance void [mscorlib]System.AppDomain::SetData(string, object)
0x15f5fd  ldarg.2
0x15f5fe  callvirt instance native int System.Web.Hosting.IApplicationHost::GetConfigToken()
0x15f603  stloc.s  0x14
0x15f605  ldloc.s  0x14
0x15f607  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x15f60c  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x15f611  brfalse.s loc_15F61C
0x15f613  ldloc.s  0x14
0x15f615  newobj   instance void System.Web.ImpersonationContext::.ctor(native int token)
0x15f61a  stloc.s  0x13
0x15f61c  nop
0x15f61d  ldarg.1
0x15f61e  call     class [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo System.Web.Hosting.ProcessHost::GetExistingCustomLoaderFailureAndClear(string appId)
0x15f623  stloc.s  0x25
0x15f625  ldloc.s  0x25
0x15f627  brfalse.s loc_15F630
0x15f629  ldloc.s  0x25
0x15f62b  callvirt instance void [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Throw()
0x15f630  ldsfld   bool EnvironmentInfo::IsStringHashCodeRandomizationDetected
0x15f635  brfalse.s loc_15F647
0x15f637  ldstr    aRequireStableS// "Require_stable_string_hash_codes"
0x15f63c  call     string System.Web.SR::GetString(string name)
0x15f641  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x15f646  throw
0x15f647  ldc.i4.0
0x15f648  stloc.s  0x26
0x15f64a  ldloc.s  0xC
0x15f64c  brfalse.s loc_15F67D
0x15f64e  ldarg.3
0x15f64f  callvirt instance string System.Web.Hosting.HostingEnvironmentParameters::get_IISExpressVersion()
0x15f654  brfalse.s loc_15F67D
0x15f656  ldc.i4.1
0x15f657  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x15f65c  stloc.s  0xF
0x15f65e  ldloc.s  5
0x15f660  ldloc.s  0x11
0x15f662  callvirt instance void [mscorlib]System.AppDomainSetup::set_PartialTrustVisibleAssemblies(string[])
0x15f667  ldloc.s  0xA
0x15f669  ldloc.s  0xB
0x15f66b  ldarg.3
0x15f66c  callvirt instance string System.Web.Hosting.HostingEnvironmentParameters::get_IISExpressVersion()
0x15f671  call     class [System.Configuration]System.Configuration.Configuration System.Web.Hosting.ApplicationManager::GetAppConfigIISExpress(string siteID, string appSegment, string iisExpressVersion)
0x15f676  stloc.s  0xD
0x15f678  ldc.i4.1
0x15f679  stloc.s  0x26
0x15f67b  br.s     loc_15F6CC
0x15f67d  ldarg.2
0x15f67e  isinst   System.Web.Hosting.ISAPIApplicationHost
0x15f683  brfalse.s loc_15F6BE
0x15f685  ldstr    aF_0// "f"
0x15f68a  ldloc.s  0xA
0x15f68c  ldloc.3
0x15f68d  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x15f692  call     string [mscorlib]System.String::Concat(string, string, string)
0x15f697  stloc.s  0x29
0x15f699  call     class System.Web.Caching.Cache System.Web.HttpRuntime::get_Cache()
0x15f69e  callvirt instance class System.Web.Caching.CacheStoreProvider System.Web.Caching.Cache::get_InternalCache()
0x15f6a3  ldloc.s  0x29
0x15f6a5  callvirt instance object System.Web.Caching.CacheStoreProvider::Remove(string key)
0x15f6aa  castclass System.Web.Configuration.MapPathCacheInfo
0x15f6af  stloc.s  0x2A
0x15f6b1  ldloc.s  0xB
0x15f6b3  ldloc.s  0xA
0x15f6b5  call     class [System.Configuration]System.Configuration.Configuration System.Web.Configuration.WebConfigurationManager::OpenWebConfiguration(string path, string site)
0x15f6ba  stloc.s  0xD
0x15f6bc  br.s     loc_15F6CC
0x15f6be  ldarg.2
0x15f6bf  ldloc.s  0xA
0x15f6c1  ldloc.s  0xB
0x15f6c3  ldloc.3
0x15f6c4  ldloc.0
0x15f6c5  call     class [System.Configuration]System.Configuration.Configuration System.Web.Hosting.ApplicationManager::GetAppConfigGeneric(class System.Web.Hosting.IApplicationHost appHost, string siteID, string appSegment, class System.Web.VirtualPath virtualPath, string physicalPath)
0x15f6ca  stloc.s  0xD
0x15f6cc  ldloc.s  0xD
0x15f6ce  ldstr    aSystemWebHttpr// "system.web/httpRuntime"
0x15f6d3  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x15f6d8  castclass System.Web.Configuration.HttpRuntimeSection
0x15f6dd  stloc.s  0x27
0x15f6df  ldloc.s  0x27
0x15f6e1  brtrue.s loc_15F701
0x15f6e3  ldstr    aConfigSectionN_0// "Config_section_not_present"
0x15f6e8  ldc.i4.1
0x15f6e9  newarr   [mscorlib]System.Object
0x15f6ee  dup
0x15f6ef  ldc.i4.0
0x15f6f0  ldstr    aHttpruntime// "httpRuntime"
0x15f6f5  stelem.ref
0x15f6f6  call     string System.Web.SR::GetString(string name, object[] args)
0x15f6fb  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x15f700  throw
0x15f701  ldloc.s  0x27
0x15f703  callvirt instance class [System]System.Runtime.Versioning.FrameworkName System.Web.Configuration.HttpRuntimeSection::GetTargetFrameworkName()
0x15f708  stloc.s  0x28
0x15f70a  ldloc.s  0x28
0x15f70c  ldnull
0x15f70d  call     bool [System]System.Runtime.Versioning.FrameworkName::op_Inequality(class [System]System.Runtime.Versioning.FrameworkName, class [System]System.Runtime.Versioning.FrameworkName)
0x15f712  brfalse.s loc_15F722
0x15f714  ldloc.s  8
0x15f716  ldstr    aAspnetTargetfr// "ASPNET_TARGETFRAMEWORK"
0x15f71b  ldloc.s  0x28
0x15f71d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x15f722  ldloc.s  0x26
0x15f724  brtrue   loc_15FC64
0x15f729  ldloc.s  0x27
0x15f72b  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.Configuration.HttpRuntimeSection::get_DefaultRegexMatchTimeout()
0x15f730  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x15f735  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x15f73a  brfalse.s loc_15F754
0x15f73c  ldloc.s  8
0x15f73e  ldstr    aRegexDefaultMa// "REGEX_DEFAULT_MATCH_TIMEOUT"
0x15f743  ldloc.s  0x27
0x15f745  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.Configuration.HttpRuntimeSection::get_DefaultRegexMatchTimeout()
0x15f74a  box      [mscorlib]System.TimeSpan
0x15f74f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x15f754  ldloc.s  0x28
0x15f756  ldnull
0x15f757  call     bool [System]System.Runtime.Versioning.FrameworkName::op_Inequality(class [System]System.Runtime.Versioning.FrameworkName, class [System]System.Runtime.Versioning.FrameworkName)
0x15f75c  brfalse.s loc_15F76C
0x15f75e  ldloc.s  5
0x15f760  ldloc.s  0x28
0x15f762  callvirt instance string [mscorlib]System.Object::ToString()
0x15f767  callvirt instance void [mscorlib]System.AppDomainSetup::set_TargetFrameworkName(string)
0x15f76c  ldloc.s  0xD
0x15f76e  callvirt instance class [System.Configuration]System.Configuration.AppSettingsSection [System.Configuration]System.Configuration.Configuration::get_AppSettings()
0x15f773  stloc.s  0x2B
0x15f775  ldloc.s  0x2B
0x15f777  callvirt instance class [System.Configuration]System.Configuration.KeyValueConfigurationCollection [System.Configuration]System.Configuration.AppSettingsSection::get_Settings()
0x15f77c  ldstr    aAspnetUsetaskf// "aspnet:UseTaskFriendlySynchronizationCo"...
0x15f781  callvirt instance class [System.Configuration]System.Configuration.KeyValueConfigurationElement [System.Configuration]System.Configuration.KeyValueConfigurationCollection::get_Item(string)
0x15f786  stloc.s  0x2C
0x15f788  ldloc.s  0x2C
0x15f78a  brfalse.s loc_15F79C
0x15f78c  ldloc.s  0x2C
0x15f78e  callvirt instance string [System.Configuration]System.Configuration.KeyValueConfigurationElement::get_Value()
0x15f793  ldloca.s 0x22
0x15f795  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x15f79a  brtrue.s loc_15F7B0
0x15f79c  ldloc.s  0x28
0x15f79e  newobj   instance void System.Web.Util.BinaryCompatibility::.ctor(class [System]System.Runtime.Versioning.FrameworkName frameworkName)
0x15f7a3  call     instance bool System.Web.Util.BinaryCompatibility::get_TargetsAtLeastFramework45()
0x15f7a8  brtrue.s loc_15F7AD
0x15f7aa  ldc.i4.0
0x15f7ab  br.s     loc_15F7AE
0x15f7ad  ldc.i4.1
0x15f7ae  stloc.s  0x22
0x15f7b0  ldloc.s  0x2B
0x15f7b2  callvirt instance class [System.Configuration]System.Configuration.KeyValueConfigurationCollection [System.Configuration]System.Configuration.AppSettingsSection::get_Settings()
0x15f7b7  ldstr    aAspnetUserando// "aspnet:UseRandomizedStringHashAlgorithm"
0x15f7bc  callvirt instance class [System.Configuration]System.Configuration.KeyValueConfigurationElement [System.Configuration]System.Configuration.KeyValueConfigurationCollection::get_Item(string)
0x15f7c1  stloc.s  0x2D
0x15f7c3  ldc.i4.0
0x15f7c4  stloc.s  0x2E
0x15f7c6  ldloc.s  0x2D
0x15f7c8  brfalse.s loc_15F7E3
0x15f7ca  ldloc.s  0x2D
0x15f7cc  callvirt instance string [System.Configuration]System.Configuration.KeyValueConfigurationElement::get_Value()
0x15f7d1  ldloca.s 0x2E
0x15f7d3  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x15f7d8  brfalse.s loc_15F7E3
0x15f7da  ldloc.s  6
0x15f7dc  ldloc.s  0x2E
0x15f7de  stfld    bool AppDomainSwitches::UseRandomizedStringHashAlgorithm
0x15f7e3  ldnull
0x15f7e4  stloc.s  0x2F
0x15f7e6  ldloc.s  0x2B
  ... truncated ...
```
