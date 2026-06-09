# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::<InstallCoreInternal>g__install|34_1

- ea: `0x34540`
- end: `0x34984`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::<InstallCoreInternal>g__install|34_1`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x322d0`

## callees

- `0x1a0b0`
- `0x1a0d0`
- `0x2b1c0`
- `0x2b9a0`
- `0x2b9e0`
- `0x30300`
- `0x32f90`
- `0x32fc0`
- `0x330c0`
- `0x342d0`
- `0x34540`
- `0x3ce50`
- `0x3cea0`
- `0x3ceb0`
- `0x3df80`
- `0x3df90`
- `0x3e200`

## string_xrefs

- `0x3490b`: `VsixInstaller`
- `0x345a0`: `extension.vsixmanifest`
- `0x34663`: `The installation path: `
- `0x34669`: ` is outside of allowed directory: `
- `0x346e0`: `' already exists.`

## pseudocode

```c

```

## disassembly

```asm
0x34540  ldc.i4.0
0x34541  stloc.0
0x34542  ldarg.1
0x34543  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x34548  call     bool [WindowsBase]System.IO.Packaging.PackUriHelper::IsRelationshipPartUri(class [System]System.Uri)
0x3454d  brtrue   loc_34983
0x34552  ldarg.s  6
0x34554  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri> <>c__DisplayClass34_3::signatureParts
0x34559  ldarg.1
0x3455a  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3455f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri>::Contains(var<u1>)
0x34564  brtrue   loc_34983
0x34569  ldarg.0
0x3456a  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x3456f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::GetValueOrDefault()
0x34574  ldc.i4.2
0x34575  beq.s    loc_34592
0x34577  ldarg.1
0x34578  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3457d  callvirt instance string [System]System.Uri::get_OriginalString()
0x34582  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::RootDirectory
0x34587  ldc.i4.5
0x34588  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3458d  brfalse  loc_34983
0x34592  ldarg.2
0x34593  brfalse.s loc_345BC
0x34595  ldarg.1
0x34596  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3459b  callvirt instance string [System]System.Uri::get_OriginalString()
0x345a0  ldstr    aExtensionVsixm// "extension.vsixmanifest"
0x345a5  ldc.i4.5
0x345a6  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x345ab  ldc.i4.0
0x345ac  blt.s    loc_345BC
0x345ae  ldarg.s  6
0x345b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart> <>c__DisplayClass34_3::partsToApplyLast
0x345b5  ldarg.1
0x345b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart>::Add(var<u1>)
0x345bb  ret
0x345bc  ldarg.s  5
0x345be  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x345c3  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::PartProcessing
0x345c8  ldc.i4.1
0x345c9  newarr   [mscorlib]System.Object
0x345ce  dup
0x345cf  ldc.i4.0
0x345d0  ldarg.1
0x345d1  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x345d6  callvirt instance string [System]System.Uri::get_OriginalString()
0x345db  stelem.ref
0x345dc  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string format, object[] args)
0x345e1  ldarg.0
0x345e2  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x345e7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::GetValueOrDefault()
0x345ec  ldc.i4.2
0x345ed  bne.un.s loc_3461B
0x345ef  ldarg.s  4
0x345f1  ldfld    string <>c__DisplayClass34_1::layoutDir
0x345f6  stloc.3
0x345f7  ldarg.0
0x345f8  ldarg.1
0x345f9  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x345fe  callvirt instance string [System]System.Uri::get_OriginalString()
0x34603  ldarg.s  4
0x34605  ldfld    string <>c__DisplayClass34_1::layoutDir
0x3460a  ldarg.s  6
0x3460c  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_3::resolvedFolderMapping
0x34611  ldloca.s 3
0x34613  call     instance string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixV3LayoutForPart(string partPath, string layoutDir, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> resolvedFolderMappings, [out] string& layoutDirOfFile)
0x34618  stloc.1
0x34619  br.s     loc_34641
0x3461b  ldarg.3
0x3461c  ldfld    string <>c__DisplayClass34_0::installDir
0x34621  ldarg.1
0x34622  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x34627  callvirt instance string [System]System.Uri::get_OriginalString()
0x3462c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::RootDirectory
0x34631  callvirt instance int32 [mscorlib]System.String::get_Length()
0x34636  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3463b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x34640  stloc.1
0x34641  ldloc.1
0x34642  call     string [System]System.Uri::UnescapeDataString(string)
0x34647  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3464c  stloc.2
0x3464d  ldloc.2
0x3464e  ldarg.3
0x3464f  ldfld    string <>c__DisplayClass34_0::installDir
0x34654  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x34659  brtrue.s loc_346C3
0x3465b  ldarg.s  5
0x3465d  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x34662  ldnull
0x34663  ldstr    aTheInstallatio_0// "The installation path: "
0x34668  ldloc.2
0x34669  ldstr    aIsOutsideOfAll// " is outside of allowed directory: "
0x3466e  ldarg.3
0x3466f  ldfld    string <>c__DisplayClass34_0::installDir
0x34674  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x34679  call     T0x2B000003
0x3467e  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0x34683  ldarg.s  6
0x34685  ldarg.0
0x34686  ldarg.3
0x34687  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x3468c  ldc.i4.1
0x3468d  ldc.i4.0
0x3468e  call     string Microsoft.VisualStudio.Setup.Resources::get_FileInstallationPathInvalid_Args1()
0x34693  ldloc.2
0x34694  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x34699  call     string [mscorlib]System.String::Format(string, object)
0x3469e  stloc.s  4
0x346a0  ldarg.s  5
0x346a2  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x346a7  stloc.s  5
0x346a9  ldloca.s 6
0x346ab  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x346b1  ldloc.s  6
0x346b3  ldnull
0x346b4  ldloc.s  4
0x346b6  ldloc.s  5
0x346b8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x346bd  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass34_3::result
0x346c2  ret
0x346c3  ldarg.s  6
0x346c5  ldfld    bool <>c__DisplayClass34_3::preventFileOverwrite
0x346ca  brfalse.s loc_3470C
0x346cc  ldarg.0
0x346cd  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x346d2  ldloc.2
0x346d3  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x346d8  brfalse.s loc_3470C
0x346da  ldstr    aTheFile// "The file '"
0x346df  ldloc.2
0x346e0  ldstr    aAlreadyExists// "' already exists."
0x346e5  call     string [mscorlib]System.String::Concat(string, string, string)
0x346ea  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x346ef  stloc.s  7
0x346f1  ldarg.s  5
0x346f3  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x346f8  ldloc.s  7
0x346fa  ldstr    aExceptionOccur_0// "Exception occurred while overwriting fi"...
0x346ff  call     T0x2B000003
0x34704  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0x34709  ldloc.s  7
0x3470b  throw
0x3470c  ldarg.1
0x3470d  ldc.i4.3
0x3470e  ldc.i4.1
0x3470f  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x34714  stloc.s  8
0x34716  ldarg.0
0x34717  ldarg.1
0x34718  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3471d  callvirt instance string [System]System.Uri::get_OriginalString()
0x34722  ldloc.s  8
0x34724  ldloc.2
0x34725  ldloca.s 0
0x34727  ldloca.s 0xA
0x34729  ldarg.s  5
0x3472b  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x34730  call     instance bool Microsoft.VisualStudio.Setup.Installer.FileInstaller::CopyFile(string sourcePath, class [mscorlib]System.IO.Stream source, string destinationPath, [out] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType& rebootRequired, [out] string& actualDestinationPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x34735  stloc.s  9
0x34737  ldloc.s  9
0x34739  brfalse.s loc_3477B
0x3473b  ldarg.s  6
0x3473d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass34_3::usingGroupFiles
0x34742  ldarg.1
0x34743  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x34748  callvirt instance string [System]System.Uri::get_OriginalString()
0x3474d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x34752  brfalse.s loc_3477B
0x34754  ldarg.0
0x34755  call     instance class Microsoft.VisualStudio.Setup.Services.IGroupConfigService Microsoft.VisualStudio.Setup.Installer.VsixInstaller::get_GroupConfigService()
0x3475a  ldloc.s  0xA
0x3475c  ldloc.2
0x3475d  ldarg.s  6
0x3475f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass34_3::usingGroupFiles
0x34764  ldarg.1
0x34765  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3476a  callvirt instance string [System]System.Uri::get_OriginalString()
0x3476f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x34774  callvirt instance void Microsoft.VisualStudio.Setup.Services.IGroupConfigService::AddUsingGroupConfig(string configPath, string finalConfigPath, string groupName)
0x34779  br.s     loc_347BD
0x3477b  ldloc.s  9
0x3477d  brfalse.s loc_347BD
0x3477f  ldarg.s  6
0x34781  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass34_3::groupFiles
0x34786  ldarg.1
0x34787  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x3478c  callvirt instance string [System]System.Uri::get_OriginalString()
0x34791  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x34796  brfalse.s loc_347BD
0x34798  ldarg.0
0x34799  call     instance class Microsoft.VisualStudio.Setup.Services.IGroupConfigService Microsoft.VisualStudio.Setup.Installer.VsixInstaller::get_GroupConfigService()
0x3479e  ldloc.s  0xA
0x347a0  ldloc.2
0x347a1  ldarg.s  6
0x347a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass34_3::groupFiles
0x347a8  ldarg.1
0x347a9  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x347ae  callvirt instance string [System]System.Uri::get_OriginalString()
0x347b3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x347b8  callvirt instance void Microsoft.VisualStudio.Setup.Services.IGroupConfigService::AddGroupConfig(string configPath, string finalConfigPath, string groupName)
0x347bd  ldloc.0
0x347be  ldarg.3
0x347bf  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType <>c__DisplayClass34_0::rebootPending
0x347c4  ble.s    loc_347CD
0x347c6  ldarg.3
0x347c7  ldloc.0
0x347c8  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType <>c__DisplayClass34_0::rebootPending
0x347cd  ldloc.s  9
0x347cf  brtrue.s loc_34815
0x347d1  ldarg.s  6
0x347d3  ldarg.0
0x347d4  ldarg.3
0x347d5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x347da  ldc.i4.1
0x347db  ldarg.3
0x347dc  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType <>c__DisplayClass34_0::rebootPending
0x347e1  call     string Microsoft.VisualStudio.Setup.Resources::get_FileInstallationFailed_Args1()
0x347e6  ldloc.2
0x347e7  call     string [mscorlib]System.String::Format(string, object)
0x347ec  stloc.s  4
0x347ee  ldarg.s  5
0x347f0  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x347f5  stloc.s  5
0x347f7  ldloca.s 6
0x347f9  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x347ff  ldloc.s  6
0x34801  ldnull
0x34802  ldloc.s  4
0x34804  ldloc.s  5
0x34806  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x3480b  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass34_3::result
0x34810  leave    loc_34983
0x34815  leave.s  loc_34823
0x34817  ldloc.s  8
0x34819  brfalse.s loc_34822
0x3481b  ldloc.s  8
0x3481d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34822  endfinally
0x34823  nop
0x34824  ldarg.3
0x34825  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x3482a  ldarg.1
0x3482b  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x34830  callvirt instance string [System]System.Uri::get_OriginalString()
0x34835  ldloc.2
0x34836  ldarg.s  6
0x34838  ldfld    string <>c__DisplayClass34_3::defaultNgenApplication
0x3483d  ldarg.3
0x3483e  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x34843  ldarg.s  5
0x34845  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x3484a  ldarg.0
0x3484b  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture Microsoft.VisualStudio.Setup.Installer.VsixInstaller::defaultArchitecture
0x34850  call     class Microsoft.VisualStudio.Setup.Installer.Ngen Microsoft.VisualStudio.Setup.Installer.Ngen::TryGetNgenForFile(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string fileName, string fileLocation, string defaultNgenConfigPath, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variableMapping, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture defaultNgenArchitecture)
0x34855  stloc.s  0xB
0x34857  ldloc.s  0xB
0x34859  brfalse.s loc_34868
0x3485b  ldarg.0
0x3485c  call     instance class Microsoft.VisualStudio.Setup.Services.INgenStateService Microsoft.VisualStudio.Setup.Installer.VsixInstaller::get_NgenStateService()
0x34861  ldloc.s  0xB
0x34863  callvirt instance void Microsoft.VisualStudio.Setup.Services.INgenStateService::PersistEntry(class Microsoft.VisualStudio.Setup.Installer.Ngen ngenForFile)
0x34868  leave    loc_34983
0x3486d  stloc.s  0xC
0x3486f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x34874  dup
0x34875  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLPACKAGEPROPERTY
0x3487a  ldarg.1
0x3487b  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x34880  callvirt instance string [System]System.Uri::get_OriginalString()
0x34885  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3488a  dup
0x3488b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEIDPROPERTY
0x34890  ldarg.3
0x34891  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x34896  dup
0x34897  brtrue.s loc_3489D
0x34899  pop
0x3489a  ldnull
0x3489b  br.s     loc_348A2
0x3489d  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x348a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x348a7  dup
0x348a8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x348ad  ldarg.3
0x348ae  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x348b3  dup
0x348b4  brtrue.s loc_348BA
0x348b6  pop
0x348b7  ldnull
0x348b8  br.s     loc_348C9
0x348ba  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_TelemetryCorrelatedParents()
0x348bf  ldstr    asc_82420// ";"
0x348c4  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x348c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x348ce  dup
0x348cf  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
  ... truncated ...
```
