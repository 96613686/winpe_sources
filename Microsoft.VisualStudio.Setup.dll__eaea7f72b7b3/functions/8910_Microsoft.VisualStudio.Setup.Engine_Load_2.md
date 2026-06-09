# Microsoft.VisualStudio.Setup.Engine::Load_2

- ea: `0x8910`
- end: `0x8eaf`
- name: `Microsoft.VisualStudio.Setup.Engine::Load_2`
- size: `1439`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x86e0`

## callees

- `0x7e40`
- `0x7e80`
- `0x7e90`
- `0x7ea0`
- `0x7eb0`
- `0x8910`
- `0x9b90`
- `0xcda0`
- `0xcde0`
- `0xcf60`
- `0xcf80`
- `0xcfe0`
- `0xd360`
- `0xe970`
- `0x1cce0`
- `0x1cda0`
- `0x1ce70`
- `0x1cf50`
- `0x1d030`
- `0x67c00`
- `0x67c30`
- `0x67c70`

## string_xrefs

- `0x8b1c`: `InstallationName`
- `0x8be1`: `ChannelsPath`
- `0x8bfa`: `ChannelsPath`
- `0x8c33`: `ChannelsPath`

## pseudocode

```c

```

## disassembly

```asm
0x8910  newobj   instance void <>c__DisplayClass147_0::.ctor()
0x8915  stloc.0
0x8916  ldarg.0
0x8917  call     instance void Microsoft.VisualStudio.Setup.Engine::ResetDependencyGraph()
0x891c  ldarg.0
0x891d  ldarg.1
0x891e  callvirt instance class [mscorlib]System.Version class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_ManifestVersion()
0x8923  call     instance void Microsoft.VisualStudio.Setup.Engine::set_ManifestVersion(class [mscorlib]System.Version value)
0x8928  ldarg.0
0x8929  ldarg.1
0x892a  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x892f  call     instance void Microsoft.VisualStudio.Setup.Engine::set_BuildVersion(class [mscorlib]System.Version value)
0x8934  ldarg.0
0x8935  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x893a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::LOADCATALOGMANIFESTVERSIONPROPERTY
0x893f  ldarg.0
0x8940  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Engine::get_ManifestVersion()
0x8945  callvirt instance string [mscorlib]System.Object::ToString()
0x894a  ldc.i4.0
0x894b  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0x8950  ldarg.0
0x8951  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8956  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::LOADCATALOGBUILDVERSIONPROPERTY
0x895b  ldarg.0
0x895c  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Engine::get_BuildVersion()
0x8961  callvirt instance string [mscorlib]System.Object::ToString()
0x8966  ldc.i4.0
0x8967  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0x896c  ldarg.0
0x896d  ldarg.1
0x896e  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionApplicabilityArtifacts::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog catalog)
0x8973  stfld    class Microsoft.VisualStudio.Setup.ExtensionApplicabilityArtifacts Microsoft.VisualStudio.Setup.Engine::extensionApplicabilityArtifacts
0x8978  ldarg.0
0x8979  ldarg.0
0x897a  ldfld    class Microsoft.VisualStudio.Setup.ExtensionApplicabilityArtifacts Microsoft.VisualStudio.Setup.Engine::extensionApplicabilityArtifacts
0x897f  call     instance void Microsoft.VisualStudio.Setup.Engine::UpdateExtensions(class Microsoft.VisualStudio.Setup.ExtensionApplicabilityArtifacts artifacts)
0x8984  ldloc.0
0x8985  ldarg.0
0x8986  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Engine::cache
0x898b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x8990  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x8995  ldarg.1
0x8996  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x899b  brfalse  loc_8E49
0x89a0  newobj   instance void <>c__DisplayClass147_1::.ctor()
0x89a5  dup
0x89a6  ldarg.0
0x89a7  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Engine::get_BuildVersion()
0x89ac  ldloc.0
0x89ad  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x89b2  dup
0x89b3  brtrue.s loc_89B9
0x89b5  pop
0x89b6  ldnull
0x89b7  br.s     loc_89CA
0x89b9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_CatalogInfo()
0x89be  dup
0x89bf  brtrue.s loc_89C5
0x89c1  pop
0x89c2  ldnull
0x89c3  br.s     loc_89CA
0x89c5  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo)
0x89ca  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x89cf  stfld    bool <>c__DisplayClass147_1::catalogVersionLowerThanInstance
0x89d4  ldftn    instance bool <>c__DisplayClass147_1::<Load>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage p)
0x89da  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x89df  stloc.1
0x89e0  ldarg.0
0x89e1  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> Microsoft.VisualStudio.Setup.Engine::packages
0x89e6  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::get_Keys()
0x89eb  ldloc.1
0x89ec  call     T0x2B00005E
0x89f1  brfalse  loc_8A95
0x89f6  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::VersionIndependent
0x89fb  ldarg.1
0x89fc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x8a01  ldarg.0
0x8a02  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x8a07  ldarg.0
0x8a08  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x8a0d  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DowngradeCandidatePicker::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x8a12  stloc.2
0x8a13  ldarg.0
0x8a14  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> Microsoft.VisualStudio.Setup.Engine::packages
0x8a19  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::get_Keys()
0x8a1e  ldloc.1
0x8a1f  call     T0x2B000012
0x8a24  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x8a29  stloc.3
0x8a2a  br.s     loc_8A81
0x8a2c  ldloc.3
0x8a2d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x8a32  stloc.s  4
0x8a34  ldloc.2
0x8a35  ldloc.s  4
0x8a37  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DowngradeCandidatePicker::Pick(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x8a3c  stloc.s  5
0x8a3e  ldloc.s  5
0x8a40  brfalse.s loc_8A4D
0x8a42  ldloc.s  4
0x8a44  ldloc.s  5
0x8a46  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::set_DowngradingPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x8a4b  br.s     loc_8A81
0x8a4d  ldarg.0
0x8a4e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x8a53  dup
0x8a54  brtrue.s loc_8A59
0x8a56  pop
0x8a57  br.s     loc_8A79
0x8a59  ldstr    aPackage_0// "Package '"
0x8a5e  ldloc.s  4
0x8a60  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x8a65  ldstr    aIsNotDowngrada// "' is not downgradable anymore because c"...
0x8a6a  call     string [mscorlib]System.String::Concat(string, string, string)
0x8a6f  call     T0x2B000003
0x8a74  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8a79  ldloc.s  4
0x8a7b  ldnull
0x8a7c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::set_DowngradingPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x8a81  ldloc.3
0x8a82  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a87  brtrue.s loc_8A2C
0x8a89  leave.s  loc_8A95
0x8a8b  ldloc.3
0x8a8c  brfalse.s loc_8A94
0x8a8e  ldloc.3
0x8a8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a94  endfinally
0x8a95  ldarg.1
0x8a96  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x8a9b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x8aa0  stloc.3
0x8aa1  br.s     loc_8ABA
0x8aa3  ldloc.3
0x8aa4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x8aa9  stloc.s  6
0x8aab  ldarg.0
0x8aac  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> Microsoft.VisualStudio.Setup.Engine::packages
0x8ab1  ldloc.s  6
0x8ab3  ldc.i4.1
0x8ab4  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::TryAdd(var<u1>, !!T0)
0x8ab9  pop
0x8aba  ldloc.3
0x8abb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8ac0  brtrue.s loc_8AA3
0x8ac2  leave.s  loc_8ACE
0x8ac4  ldloc.3
0x8ac5  brfalse.s loc_8ACD
0x8ac7  ldloc.3
0x8ac8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8acd  endfinally
0x8ace  ldarg.1
0x8acf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Info()
0x8ad4  brfalse  loc_8D98
0x8ad9  newobj   instance void <>c__DisplayClass147_2::.ctor()
0x8ade  stloc.s  7
0x8ae0  ldloc.s  7
0x8ae2  ldarg.1
0x8ae3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Info()
0x8ae8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_Id()
0x8aed  stfld    string <>c__DisplayClass147_2::installationName
0x8af2  ldloc.s  7
0x8af4  ldarg.1
0x8af5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Info()
0x8afa  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_ProductDisplayVersion()
0x8aff  stfld    string <>c__DisplayClass147_2::productDisplayVersion
0x8b04  ldloc.s  7
0x8b06  ldarg.1
0x8b07  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Info()
0x8b0c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_ProductSemanticVersion()
0x8b11  stfld    string <>c__DisplayClass147_2::productSemanticVersion
0x8b16  ldarg.0
0x8b17  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8b1c  ldstr    aInstallationna// "InstallationName"
0x8b21  ldloc.s  7
0x8b23  ldftn    instance string <>c__DisplayClass147_2::<Load>b__1()
0x8b29  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x8b2e  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0x8b33  ldarg.0
0x8b34  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8b39  ldsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductDisplayVersion
0x8b3e  ldloc.s  7
0x8b40  ldftn    instance string <>c__DisplayClass147_2::<Load>b__2()
0x8b46  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x8b4b  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0x8b50  ldarg.0
0x8b51  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8b56  ldsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ProductSemanticVersion
0x8b5b  ldloc.s  7
0x8b5d  ldftn    instance string <>c__DisplayClass147_2::<Load>b__3()
0x8b63  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x8b68  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0x8b6d  ldloc.s  7
0x8b6f  ldarg.0
0x8b70  ldarg.0
0x8b71  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Engine::get_ChannelUri()
0x8b76  ldarg.0
0x8b77  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Engine::get_InstallChannelUri()
0x8b7c  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Engine::SelectChannelUri(class [System]System.Uri channelUri, class [System]System.Uri installChannelUri)
0x8b81  stfld    class [System]System.Uri <>c__DisplayClass147_2::selectedUri
0x8b86  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x8b8b  dup
0x8b8c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDID
0x8b91  ldloc.s  7
0x8b93  ldfld    string <>c__DisplayClass147_2::installationName
0x8b98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8b9d  dup
0x8b9e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDBRANCH
0x8ba3  ldarg.1
0x8ba4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Info()
0x8ba9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_BuildBranch()
0x8bae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8bb3  dup
0x8bb4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDBUILDNUMBER
0x8bb9  ldarg.1
0x8bba  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x8bbf  callvirt instance string [mscorlib]System.Object::ToString()
0x8bc4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8bc9  dup
0x8bca  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDENGINEVERSION
0x8bcf  call     string Microsoft.VisualStudio.Setup.EngineInfo::get_EngineFileVersion()
0x8bd4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8bd9  stloc.s  8
0x8bdb  ldarg.0
0x8bdc  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8be1  ldstr    aChannelspath// "ChannelsPath"
0x8be6  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0x8beb  brfalse.s loc_8C10
0x8bed  ldloc.s  8
0x8bef  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDCHANNELSPATH
0x8bf4  ldarg.0
0x8bf5  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8bfa  ldstr    aChannelspath// "ChannelsPath"
0x8bff  callvirt instance string Microsoft.VisualStudio.Setup.VariableCollection::get_Item(string)
0x8c04  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x8c09  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8c0e  br.s     loc_8C4A
0x8c10  ldloc.s  7
0x8c12  ldfld    class [System]System.Uri <>c__DisplayClass147_2::selectedUri
0x8c17  ldnull
0x8c18  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x8c1d  brfalse.s loc_8C4A
0x8c1f  ldloc.s  7
0x8c21  ldfld    class [System]System.Uri <>c__DisplayClass147_2::selectedUri
0x8c26  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x8c2b  brfalse.s loc_8C4A
0x8c2d  ldarg.0
0x8c2e  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x8c33  ldstr    aChannelspath// "ChannelsPath"
0x8c38  ldloc.s  7
0x8c3a  ldftn    instance string <>c__DisplayClass147_2::<Load>b__4()
0x8c40  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x8c45  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0x8c4a  ldloc.0
0x8c4b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x8c50  brfalse  loc_8D6A
0x8c55  ldarg.0
0x8c56  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x8c5b  dup
0x8c5c  brtrue.s loc_8C61
0x8c5e  pop
0x8c5f  br.s     loc_8CA6
0x8c61  ldc.i4.5
0x8c62  newarr   [mscorlib]System.String
0x8c67  dup
0x8c68  ldc.i4.0
0x8c69  ldstr    aLoadingCatalog// "Loading catalog '"
0x8c6e  stelem.ref
0x8c6f  dup
0x8c70  ldc.i4.1
0x8c71  ldloc.s  7
0x8c73  ldfld    string <>c__DisplayClass147_2::installationName
0x8c78  stelem.ref
0x8c79  dup
0x8c7a  ldc.i4.2
0x8c7b  ldstr    aIntoEngineSess// "' into engine session '"
0x8c80  stelem.ref
0x8c81  dup
0x8c82  ldc.i4.3
0x8c83  ldloc.0
0x8c84  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x8c89  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstanceId()
0x8c8e  stelem.ref
0x8c8f  dup
0x8c90  ldc.i4.4
0x8c91  ldstr    asc_7F7FA// "'."
0x8c96  stelem.ref
0x8c97  call     string [mscorlib]System.String::Concat(string[])
0x8c9c  call     T0x2B000003
0x8ca1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8ca6  ldloc.0
0x8ca7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x8cac  ldloc.s  7
0x8cae  ldfld    string <>c__DisplayClass147_2::installationName
0x8cb3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationName(string)
0x8cb8  ldarg.0
0x8cb9  ldloc.0
0x8cba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass147_0::instance
0x8cbf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_CatalogInfo()
0x8cc4  call     instance void Microsoft.VisualStudio.Setup.Engine::ConfigureSignatureVerifier(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo catalogInfo)
  ... truncated ...
```
