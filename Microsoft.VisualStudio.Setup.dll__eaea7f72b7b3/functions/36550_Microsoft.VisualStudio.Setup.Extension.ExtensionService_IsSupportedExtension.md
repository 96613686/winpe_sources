# Microsoft.VisualStudio.Setup.Extension.ExtensionService::IsSupportedExtension

- ea: `0x36550`
- end: `0x3665f`
- name: `Microsoft.VisualStudio.Setup.Extension.ExtensionService::IsSupportedExtension`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x35e00`
- `0x35e20`
- `0x35e30`
- `0x35e40`
- `0x36550`
- `0x36db0`
- `0x36dd0`
- `0x37960`
- `0x37c00`
- `0x37c40`

## string_xrefs

- `0x36575`: `Extension is not a per-machine extension and will be forced to be installed as per-machine.`
- `0x3658e`: `Extension is not a v3 vsix and is unsupported.`
- `0x365ac`: `Installer\Features`
- `0x365b1`: `ExtensionPack`
- `0x365c7`: `Extension is an extension pack and is not supported.`
- `0x3664c`: `Extension has requested to be hotloaded but is not a VisualStudio.Extensibility extension.`

## pseudocode

```c

```

## disassembly

```asm
0x36550  ldarg.1
0x36551  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x36556  brfalse.s loc_36584
0x36558  ldarg.1
0x36559  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x3655e  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_InstallationInformation()
0x36563  dup
0x36564  brtrue.s loc_3656A
0x36566  pop
0x36567  ldc.i4.1
0x36568  br.s     loc_36572
0x3656a  call     instance bool Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation::get_AllUsers()
0x3656f  ldc.i4.0
0x36570  ceq
0x36572  brfalse.s loc_36584
0x36574  ldarg.0
0x36575  ldstr    aExtensionIsNot// "Extension is not a per-machine extensio"...
0x3657a  call     T0x2B000003
0x3657f  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteVerbose(string message, object[] args)
0x36584  ldarg.1
0x36585  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_Type()
0x3658a  ldc.i4.2
0x3658b  beq.s    loc_3659F
0x3658d  ldarg.0
0x3658e  ldstr    aExtensionIsNot_0// "Extension is not a v3 vsix and is unsup"...
0x36593  call     T0x2B000003
0x36598  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x3659d  ldc.i4.1
0x3659e  ret
0x3659f  ldarg.0
0x365a0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService Microsoft.VisualStudio.Setup.Extension.ExtensionService::remoteSettingsService
0x365a5  dup
0x365a6  brtrue.s loc_365AC
0x365a8  pop
0x365a9  ldc.i4.0
0x365aa  br.s     loc_365BC
0x365ac  ldstr    aInstallerFeatu// "Installer\\Features"
0x365b1  ldstr    aExtensionpack// "ExtensionPack"
0x365b6  ldc.i4.1
0x365b7  callvirt T0x2B000120
0x365bc  brtrue.s loc_365D8
0x365be  ldarg.1
0x365bf  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionPackFile Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionPackFile()
0x365c4  brfalse.s loc_365D8
0x365c6  ldarg.0
0x365c7  ldstr    aExtensionIsAnE// "Extension is an extension pack and is n"...
0x365cc  call     T0x2B000003
0x365d1  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x365d6  ldc.i4.1
0x365d7  ret
0x365d8  ldarg.1
0x365d9  callvirt instance string Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x365de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x365e3  brtrue.s loc_3665D
0x365e5  ldnull
0x365e6  ldarg.1
0x365e7  callvirt instance string Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x365ec  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::ParseJson(class [mscorlib]System.IServiceProvider, string)
0x365f1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x365f6  call     T0x2B000192
0x365fb  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage, bool> <>c::<>9__18_0
0x36600  dup
0x36601  brtrue.s loc_3661A
0x36603  pop
0x36604  ldsfld   class <>c <>c::<>9
0x36609  ldftn    instance bool <>c::<IsSupportedExtension>b__18_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage x)
0x3660f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage, bool>::.ctor(object, native int)
0x36614  dup
0x36615  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage, bool> <>c::<>9__18_0
0x3661a  call     T0x2B000193
0x3661f  brfalse.s loc_3665D
0x36621  ldarg.1
0x36622  callvirt instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x36627  dup
0x36628  brtrue.s loc_3662E
0x3662a  pop
0x3662b  ldnull
0x3662c  br.s     loc_3663F
0x3662e  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_InstallationInformation()
0x36633  dup
0x36634  brtrue.s loc_3663A
0x36636  pop
0x36637  ldnull
0x36638  br.s     loc_3663F
0x3663a  call     instance string Microsoft.VisualStudio.Setup.Extension.Serialization.InstallationInformation::get_ExtensionType()
0x3663f  ldstr    aVisualstudioEx// "VisualStudio.Extensibility"
0x36644  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x36649  brfalse.s loc_3665D
0x3664b  ldarg.0
0x3664c  ldstr    aExtensionHasRe// "Extension has requested to be hotloaded"...
0x36651  call     T0x2B000003
0x36656  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x3665b  ldc.i4.1
0x3665c  ret
0x3665d  ldc.i4.0
0x3665e  ret
```
