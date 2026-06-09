# Microsoft.VisualStudio.Setup.Installer.InstallerBase::PlanExecuteAction

- ea: `0x2bba0`
- end: `0x2bd68`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerBase::PlanExecuteAction`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2c510`

## callees

- `0x74c0`
- `0x7760`
- `0x103d0`
- `0x2b920`
- `0x2b940`
- `0x2b960`
- `0x2bba0`
- `0x2bd80`
- `0x2c170`
- `0x2d380`

## string_xrefs

- `0x2bcef`: `' is found present，doesn't participate in ref count, and manifest is missing, it will be marked as permanent.`
- `0x2bd43`: `' is found present on deeper detection but manifest is not present so it will not be uninstalled.`

## pseudocode

```c

```

## disassembly

```asm
0x2bba0  ldarg.0
0x2bba1  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::Initialize()
0x2bba6  ldarg.0
0x2bba7  ldarg.1
0x2bba8  ldarg.s  6
0x2bbaa  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetPackageNameForLogging(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, string localPath)
0x2bbaf  stloc.0
0x2bbb0  ldarg.3
0x2bbb1  ldc.i4.0
0x2bbb2  stind.i4
0x2bbb3  ldarg.1
0x2bbb4  brfalse.s loc_2BC34
0x2bbb6  ldarg.1
0x2bbb7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ApplicabilityState()
0x2bbbc  dup
0x2bbbd  brtrue.s loc_2BBCC
0x2bbbf  pop
0x2bbc0  ldloca.s 4
0x2bbc2  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x2bbc8  ldloc.s  4
0x2bbca  br.s     loc_2BBD6
0x2bbcc  call     instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState::get_IsValid()
0x2bbd1  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2bbd6  stloc.2
0x2bbd7  ldc.i4.0
0x2bbd8  stloc.3
0x2bbd9  ldloca.s 2
0x2bbdb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x2bbe0  ldloc.3
0x2bbe1  ceq
0x2bbe3  ldloca.s 2
0x2bbe5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2bbea  and
0x2bbeb  brfalse.s loc_2BC34
0x2bbed  ldarg.0
0x2bbee  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2bbf3  ldstr    aSkippingNonApp// "Skipping non-applicable package "
0x2bbf8  ldarg.1
0x2bbf9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2bbfe  ldstr    asc_82BA2// ": "
0x2bc03  call     string [mscorlib]System.Environment::get_NewLine()
0x2bc08  ldarg.1
0x2bc09  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ApplicabilityState()
0x2bc0e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityMessage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState::get_InvalidMessages()
0x2bc13  call     T0x2B00016E
0x2bc18  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2bc1d  call     T0x2B000003
0x2bc22  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2bc27  ldarg.s  4
0x2bc29  ldc.i4.1
0x2bc2a  stind.i4
0x2bc2b  ldc.i4.1
0x2bc2c  ldc.i4.0
0x2bc2d  ldnull
0x2bc2e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2bc33  ret
0x2bc34  ldarg.0
0x2bc35  ldarg.1
0x2bc36  ldarg.s  4
0x2bc38  ldarg.s  5
0x2bc3a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetCurrentPackageState(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState& currentState, valuetype [mscorlib]System.Nullable`1<bool> softDetectionHint)
0x2bc3f  stloc.1
0x2bc40  ldloc.1
0x2bc41  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Type()
0x2bc46  ldc.i4.1
0x2bc47  beq.s    loc_2BC4B
0x2bc49  ldloc.1
0x2bc4a  ret
0x2bc4b  ldarg.s  4
0x2bc4d  ldind.i4
0x2bc4e  stloc.s  5
0x2bc50  ldloc.s  5
0x2bc52  switch   loc_2BC8B, loc_2BC6C, loc_2BC8B, loc_2BC6C
0x2bc67  br       loc_2BD5F
0x2bc6c  ldarg.2
0x2bc6d  ldc.i4.1
0x2bc6e  sub
0x2bc6f  ldc.i4.1
0x2bc70  ble.un.s loc_2BC7B
0x2bc72  ldarg.2
0x2bc73  ldc.i4.3
0x2bc74  beq.s    loc_2BC83
0x2bc76  br       loc_2BD5F
0x2bc7b  ldarg.3
0x2bc7c  ldc.i4.1
0x2bc7d  stind.i4
0x2bc7e  br       loc_2BD5F
0x2bc83  ldarg.3
0x2bc84  ldc.i4.0
0x2bc85  stind.i4
0x2bc86  br       loc_2BD5F
0x2bc8b  ldarg.2
0x2bc8c  ldc.i4.1
0x2bc8d  sub
0x2bc8e  switch   loc_2BCA4, loc_2BD0C, loc_2BD25
0x2bc9f  br       loc_2BD5F
0x2bca4  ldarg.3
0x2bca5  ldc.i4.0
0x2bca6  stind.i4
0x2bca7  ldarg.1
0x2bca8  brfalse  loc_2BD5F
0x2bcad  ldarg.0
0x2bcae  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_CacheService()
0x2bcb3  brfalse  loc_2BD5F
0x2bcb8  ldarg.0
0x2bcb9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_CacheService()
0x2bcbe  ldarg.1
0x2bcbf  ldc.i4.0
0x2bcc0  ldc.i4.0
0x2bcc1  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsCached(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, bool, bool)
0x2bcc6  brtrue   loc_2BD5F
0x2bccb  ldarg.0
0x2bccc  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2bcd1  newobj   instance void Microsoft.VisualStudio.Setup.DependencyActionManager::.ctor(class [mscorlib]System.IServiceProvider services)
0x2bcd6  ldarg.1
0x2bcd7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.DependencyActionManager::GetExistingDependencies(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package)
0x2bcdc  call     T0x2B000015
0x2bce1  brtrue.s loc_2BD5F
0x2bce3  ldarg.0
0x2bce4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2bce9  ldstr    aPackage_0// "Package '"
0x2bcee  ldloc.0
0x2bcef  ldstr    aIsFoundPresent// "' is found present，doesn't participate "...
0x2bcf4  call     string [mscorlib]System.String::Concat(string, string, string)
0x2bcf9  call     T0x2B000003
0x2bcfe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2bd03  ldarg.1
0x2bd04  ldc.i4.1
0x2bd05  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::set_IsPermanent(bool)
0x2bd0a  br.s     loc_2BD5F
0x2bd0c  ldarg.3
0x2bd0d  ldc.i4.2
0x2bd0e  stind.i4
0x2bd0f  ldarg.s  4
0x2bd11  ldind.i4
0x2bd12  ldc.i4.2
0x2bd13  bne.un.s loc_2BD5F
0x2bd15  ldarg.1
0x2bd16  ldloca.s 6
0x2bd18  call     valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CompatiblePresent Microsoft.VisualStudio.Setup.Extensions::IsCompatibleVersionPresent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package, [out] class [mscorlib]System.Version& compatibleVersion)
0x2bd1d  ldc.i4.2
0x2bd1e  bne.un.s loc_2BD5F
0x2bd20  ldarg.3
0x2bd21  ldc.i4.0
0x2bd22  stind.i4
0x2bd23  br.s     loc_2BD5F
0x2bd25  ldarga.s 5
0x2bd27  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2bd2c  brfalse.s loc_2BD37
0x2bd2e  ldarga.s 5
0x2bd30  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2bd35  brtrue.s loc_2BD5C
0x2bd37  ldarg.0
0x2bd38  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2bd3d  ldstr    aPackage_0// "Package '"
0x2bd42  ldloc.0
0x2bd43  ldstr    aIsFoundPresent_0// "' is found present on deeper detection "...
0x2bd48  call     string [mscorlib]System.String::Concat(string, string, string)
0x2bd4d  call     T0x2B000003
0x2bd52  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2bd57  ldarg.3
0x2bd58  ldc.i4.0
0x2bd59  stind.i4
0x2bd5a  br.s     loc_2BD5F
0x2bd5c  ldarg.3
0x2bd5d  ldc.i4.3
0x2bd5e  stind.i4
0x2bd5f  ldc.i4.1
0x2bd60  ldc.i4.0
0x2bd61  ldnull
0x2bd62  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2bd67  ret
```
