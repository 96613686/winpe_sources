# Microsoft.VisualStudio.Setup.Extension.ExtensionService::ProductSupportsExtension

- ea: `0x366e0`
- end: `0x36854`
- name: `Microsoft.VisualStudio.Setup.Extension.ExtensionService::ProductSupportsExtension`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x35e30`
- `0x366e0`
- `0x36dd0`
- `0x36e90`
- `0x37280`
- `0x372a0`
- `0x372c0`
- `0x372d0`
- `0x37960`
- `0x379a0`
- `0x37ba0`
- `0x37cd0`
- `0x37cf0`
- `0x37d90`

## string_xrefs

- `0x36707`: `Extension has no installation targets and is assumed to be supported.`
- `0x36723`: `Failed to resolve {0} as an extension target. Extension is unsupported.`
- `0x3677f`: `Product version {0} does not support extensions with the MPF dependency`
- `0x3682c`: `No installation target supports id: {0}, version: {1}, and arch: {2}. Extension is unsupported.`

## pseudocode

```c

```

## disassembly

```asm
0x366e0  ldarg.1
0x366e1  brtrue.s loc_366E6
0x366e3  ldnull
0x366e4  br.s     loc_36704
0x366e6  ldarg.1
0x366e7  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x366ec  dup
0x366ed  brtrue.s loc_366F3
0x366ef  pop
0x366f0  ldnull
0x366f1  br.s     loc_36704
0x366f3  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_InstallationInformation()
0x366f8  dup
0x366f9  brtrue.s loc_366FF
0x366fb  pop
0x366fc  ldnull
0x366fd  br.s     loc_36704
0x366ff  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget[] Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation::get_InstallationTargets()
0x36704  brtrue.s loc_36718
0x36706  ldarg.0
0x36707  ldstr    aExtensionHasNo// "Extension has no installation targets a"...
0x3670c  call     T0x2B000003
0x36711  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x36716  ldc.i4.1
0x36717  ret
0x36718  ldarg.2
0x36719  ldloca.s 0
0x3671b  call     bool Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::TryGetTargetForProductId(string productId, [out] valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget& extensionTarget)
0x36720  brtrue.s loc_36739
0x36722  ldarg.0
0x36723  ldstr    aFailedToResolv// "Failed to resolve {0} as an extension t"...
0x36728  ldc.i4.1
0x36729  newarr   [mscorlib]System.Object
0x3672e  dup
0x3672f  ldc.i4.0
0x36730  ldarg.2
0x36731  stelem.ref
0x36732  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x36737  ldc.i4.0
0x36738  ret
0x36739  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Extension.ExtensionService::VersionRangeToIgnoreMPFDependency
0x3673e  ldarg.3
0x3673f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::Contains(class [mscorlib]System.Version)
0x36744  brtrue.s loc_36795
0x36746  ldarg.1
0x36747  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x3674c  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency[] Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_Dependencies()
0x36751  dup
0x36752  brtrue.s loc_36758
0x36754  pop
0x36755  ldc.i4.0
0x36756  br.s     loc_3677C
0x36758  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency, bool> <>c::<>9__20_0
0x3675d  dup
0x3675e  brtrue.s loc_36777
0x36760  pop
0x36761  ldsfld   class <>c <>c::<>9
0x36766  ldftn    instance bool <>c::<ProductSupportsExtension>b__20_0(class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency x)
0x3676c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency, bool>::.ctor(object, native int)
0x36771  dup
0x36772  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency, bool> <>c::<>9__20_0
0x36777  call     T0x2B000195
0x3677c  brfalse.s loc_36795
0x3677e  ldarg.0
0x3677f  ldstr    aProductVersion// "Product version {0} does not support ex"...
0x36784  ldc.i4.1
0x36785  newarr   [mscorlib]System.Object
0x3678a  dup
0x3678b  ldc.i4.0
0x3678c  ldarg.3
0x3678d  stelem.ref
0x3678e  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x36793  ldc.i4.0
0x36794  ret
0x36795  ldarg.1
0x36796  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x3679b  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_InstallationInformation()
0x367a0  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget[] Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation::get_InstallationTargets()
0x367a5  dup
0x367a6  ldarg.3
0x367a7  call     bool Microsoft.VisualStudio.Setup.Extension.ExtensionService::ShouldAllowPriorTarget(class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget[] installationTargets, class [mscorlib]System.Version targetProductVersion)
0x367ac  stloc.1
0x367ad  stloc.2
0x367ae  ldc.i4.0
0x367af  stloc.3
0x367b0  br.s     loc_36825
0x367b2  ldloc.2
0x367b3  ldloc.3
0x367b4  ldelem.ref
0x367b5  stloc.s  4
0x367b7  ldloc.s  4
0x367b9  callvirt instance string Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget::get_Version()
0x367be  ldloca.s 5
0x367c0  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::TryParse(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange&)
0x367c5  brfalse.s loc_36821
0x367c7  ldloc.s  5
0x367c9  ldarg.3
0x367ca  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::Contains(class [mscorlib]System.Version)
0x367cf  brtrue.s loc_367E3
0x367d1  ldloc.1
0x367d2  brfalse.s loc_36821
0x367d4  ldloc.s  5
0x367d6  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::AdjustVersionRangeForPriorTarget(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange)
0x367db  ldarg.3
0x367dc  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::Contains(class [mscorlib]System.Version)
0x367e1  brfalse.s loc_36821
0x367e3  ldloc.s  4
0x367e5  callvirt instance string Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget::get_Id()
0x367ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x367ef  brtrue.s loc_36821
0x367f1  ldloc.s  4
0x367f3  callvirt instance string Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget::get_ProductArchitecture()
0x367f8  stloc.s  6
0x367fa  ldarg.s  4
0x367fc  ldloc.s  6
0x367fe  call     bool Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::IsProductArchSupported(string productArch, string targetArch)
0x36803  brfalse.s loc_36821
0x36805  ldloc.s  4
0x36807  callvirt instance string Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationTarget::get_Id()
0x3680c  ldloca.s 7
0x3680e  call     bool Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::TryGetTargetForTargetId(string targetId, [out] valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget& extensionTarget)
0x36813  brfalse.s loc_36821
0x36815  ldloc.0
0x36816  ldloc.s  7
0x36818  call     bool Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::IsSupportedTarget(valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget installationTarget, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget supportedTarget)
0x3681d  brfalse.s loc_36821
0x3681f  ldc.i4.1
0x36820  ret
0x36821  ldloc.3
0x36822  ldc.i4.1
0x36823  add
0x36824  stloc.3
0x36825  ldloc.3
0x36826  ldloc.2
0x36827  ldlen
0x36828  conv.i4
0x36829  blt.s    loc_367B2
0x3682b  ldarg.0
0x3682c  ldstr    aNoInstallation_0// "No installation target supports id: {0}"...
0x36831  ldc.i4.3
0x36832  newarr   [mscorlib]System.Object
0x36837  dup
0x36838  ldc.i4.0
0x36839  ldarg.2
0x3683a  stelem.ref
0x3683b  dup
0x3683c  ldc.i4.1
0x3683d  ldarg.3
0x3683e  stelem.ref
0x3683f  dup
0x36840  ldc.i4.2
0x36841  ldarg.s  4
0x36843  dup
0x36844  brtrue.s loc_3684C
0x36846  pop
0x36847  ldsfld   string [mscorlib]System.String::Empty
0x3684c  stelem.ref
0x3684d  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x36852  ldc.i4.0
0x36853  ret
```
