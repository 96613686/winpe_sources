# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallCoreInternal

- ea: `0x322d0`
- end: `0x327c7`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallCoreInternal`
- size: `1271`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x10ef0`
- `0x119a0`
- `0x2b900`
- `0x2b920`
- `0x2b9e0`
- `0x2bb70`
- `0x2c050`
- `0x31bd0`
- `0x32020`
- `0x32270`
- `0x322d0`
- `0x327d0`
- `0x32ff0`
- `0x33010`
- `0x33140`
- `0x331c0`
- `0x33e80`
- `0x34070`
- `0x34140`
- `0x341e0`
- `0x342d0`
- `0x34540`
- `0x3cea0`

## string_xrefs

- `0x323e7`: `InvalidInputPaths`
- `0x327b4`: `InvalidExtensionDir`

## pseudocode

```c

```

## disassembly

```asm
0x322d0  ldloca.s 0
0x322d2  ldarg.0
0x322d3  stfld    class Microsoft.VisualStudio.Setup.Installer.VsixInstaller <>c__DisplayClass34_0::<>4__this
0x322d8  ldloca.s 0
0x322da  ldarg.2
0x322db  stfld    string <>c__DisplayClass34_0::installDir
0x322e0  ldloca.s 0
0x322e2  ldarg.3
0x322e3  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x322e8  ldarg.0
0x322e9  ldloc.0
0x322ea  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x322ef  call     T0x2B000183
0x322f4  stloc.1
0x322f5  ldloca.s 0
0x322f7  ldarg.0
0x322f8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x322fd  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x32302  ldloc.0
0x32303  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x32308  ldloc.1
0x32309  ldloc.0
0x3230a  ldfld    string <>c__DisplayClass34_0::installDir
0x3230f  call     void Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage, string installDir)
0x32314  ldloca.s 0
0x32316  ldnull
0x32317  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x3231c  ldloca.s 0
0x3231e  ldloc.0
0x3231f  ldfld    string <>c__DisplayClass34_0::installDir
0x32324  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::AddBackslashIfNotPresent(string)
0x32329  stfld    string <>c__DisplayClass34_0::installDir
0x3232e  ldarg.0
0x3232f  ldarg.1
0x32330  ldloc.0
0x32331  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x32336  ldloca.s 2
0x32338  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x3233d  brfalse.s loc_3234F
0x3233f  ldloc.0
0x32340  ldfld    string <>c__DisplayClass34_0::installDir
0x32345  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x3234a  brtrue   loc_323F4
0x3234f  ldarg.0
0x32350  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x32355  dup
0x32356  brtrue.s loc_32365
0x32358  pop
0x32359  ldloca.s 4
0x3235b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x32361  ldloc.s  4
0x32363  br.s     loc_3236F
0x32365  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.IEngineContext::get_BootstrapperAction()
0x3236a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x3236f  stloc.3
0x32370  ldloca.s 3
0x32372  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::GetValueOrDefault()
0x32377  ldc.i4.2
0x32378  bne.un.s loc_323D4
0x3237a  ldloc.0
0x3237b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x32380  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_Payloads()
0x32385  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload, bool> <>c::<>9__34_0
0x3238a  dup
0x3238b  brtrue.s loc_323A4
0x3238d  pop
0x3238e  ldsfld   class <>c <>c::<>9
0x32393  ldftn    instance bool <>c::<InstallCoreInternal>b__34_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload p)
0x32399  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload, bool>::.ctor(object, native int)
0x3239e  dup
0x3239f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload, bool> <>c::<>9__34_0
0x323a4  call     T0x2B000184
0x323a9  brfalse.s loc_323D4
0x323ab  ldloc.0
0x323ac  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x323b1  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsAlphaPack(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x323b6  brfalse.s loc_323D4
0x323b8  ldarg.0
0x323b9  ldloc.0
0x323ba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x323bf  ldc.i4.1
0x323c0  ldc.i4.0
0x323c1  ldloca.s 5
0x323c3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x323c9  ldloc.s  5
0x323cb  ldnull
0x323cc  ldnull
0x323cd  ldnull
0x323ce  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x323d3  ret
0x323d4  ldarg.0
0x323d5  ldloc.0
0x323d6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x323db  ldc.i4.1
0x323dc  ldc.i4.0
0x323dd  ldloca.s 5
0x323df  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x323e5  ldloc.s  5
0x323e7  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x323ec  ldnull
0x323ed  ldnull
0x323ee  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x323f3  ret
0x323f4  ldloca.s 0
0x323f6  ldc.i4.0
0x323f7  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType <>c__DisplayClass34_0::rebootPending
0x323fc  ldloca.s 6
0x323fe  ldloc.0
0x323ff  ldfld    string <>c__DisplayClass34_0::installDir
0x32404  stfld    string <>c__DisplayClass34_1::layoutDir
0x32409  ldarg.0
0x3240a  ldarg.0
0x3240b  ldloc.0
0x3240c  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x32411  ldloc.1
0x32412  ldloc.2
0x32413  ldloc.0
0x32414  ldfld    string <>c__DisplayClass34_0::installDir
0x32419  ldloca.s 6
0x3241b  ldflda   string <>c__DisplayClass34_1::layoutDir
0x32420  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string installerFile, string installDir, string& layoutDir)
0x32425  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::.ctor(var<u1>)
0x3242a  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x3242f  ldloca.s 7
0x32431  ldarg.0
0x32432  ldloc.1
0x32433  ldloc.2
0x32434  call     instance class Microsoft.VisualStudio.Setup.Services.FileLogger Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetLoggerForPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, string installerFile)
0x32439  stfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x3243e  ldarg.0
0x3243f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x32444  ldc.i4.0
0x32445  call     T0x2B00005B
0x3244a  dup
0x3244b  brtrue.s loc_32453
0x3244d  pop
0x3244e  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Services.WindowsRegistry::Default
0x32453  stloc.s  8
0x32455  ldloc.s  7
0x32457  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x3245c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExtractionOpenPackage
0x32461  ldc.i4.1
0x32462  newarr   [mscorlib]System.Object
0x32467  dup
0x32468  ldc.i4.0
0x32469  ldloc.2
0x3246a  stelem.ref
0x3246b  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string format, object[] args)
0x32470  ldarg.0
0x32471  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x32476  ldloc.2
0x32477  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x3247c  stloc.s  9
0x3247e  ldarg.0
0x3247f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackageReader Microsoft.VisualStudio.Setup.Installer.VsixInstaller::compressedPackageReader
0x32484  ldloc.s  9
0x32486  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackageReader::Open(class [mscorlib]System.IO.Stream)
0x3248b  stloc.s  0xA
0x3248d  ldloc.s  0xA
0x3248f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ICompressedPackageSignatureInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage::GetSignatureInfo()
0x32494  stloc.s  0xC
0x32496  ldloca.s 0xB
0x32498  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri>::.ctor()
0x3249d  stfld    class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri> <>c__DisplayClass34_3::signatureParts
0x324a2  ldloc.s  0xC
0x324a4  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ICompressedPackageSignatureInfo::get_IsSigned()
0x324a9  brfalse.s loc_32508
0x324ab  ldloc.s  0xB
0x324ad  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri> <>c__DisplayClass34_3::signatureParts
0x324b2  ldloc.s  0xC
0x324b4  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ICompressedPackageSignatureInfo::get_SignatureOrigin()
0x324b9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri>::Add(var<u1>)
0x324be  pop
0x324bf  ldloc.s  0xC
0x324c1  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.IPackageSignature> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ICompressedPackageSignatureInfo::get_Signatures()
0x324c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.IPackageSignature>::GetEnumerator()
0x324cb  stloc.s  0xD
0x324cd  br.s     loc_324F1
0x324cf  ldloc.s  0xD
0x324d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.IPackageSignature>::get_Current()
0x324d6  stloc.s  0xE
0x324d8  ldloc.s  0xB
0x324da  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri> <>c__DisplayClass34_3::signatureParts
0x324df  ldloc.s  0xE
0x324e1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.IPackageSignature::get_SignaturePart()
0x324e6  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::get_Uri()
0x324eb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Uri>::Add(var<u1>)
0x324f0  pop
0x324f1  ldloc.s  0xD
0x324f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x324f8  brtrue.s loc_324CF
0x324fa  leave.s  loc_32508
0x324fc  ldloc.s  0xD
0x324fe  brfalse.s loc_32507
0x32500  ldloc.s  0xD
0x32502  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32507  endfinally
0x32508  ldarg.0
0x32509  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x3250e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::GetValueOrDefault()
0x32513  ldc.i4.2
0x32514  bne.un.s loc_32530
0x32516  ldarg.0
0x32517  ldloc.1
0x32518  ldloc.0
0x32519  ldfld    string <>c__DisplayClass34_0::installDir
0x3251e  call     instance string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetExtensionDir(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, string installDir)
0x32523  stloc.s  0xF
0x32525  ldarg.0
0x32526  ldloc.s  0xA
0x32528  ldloc.s  0xF
0x3252a  call     instance string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CreateVsixV3CertificateInformation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage package, [opt] string installDir)
0x3252f  pop
0x32530  ldloca.s 0
0x32532  ldarg.0
0x32533  ldloc.1
0x32534  ldloc.s  0xA
0x32536  ldc.i4.1
0x32537  ldloc.s  7
0x32539  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x3253e  ldc.i4.0
0x3253f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetEmbeddedVsixPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity vsix, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage package, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, bool isManifestCached)
0x32544  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x32549  ldloc.0
0x3254a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x3254f  brfalse.s loc_3257E
0x32551  ldarg.0
0x32552  ldarg.0
0x32553  ldloc.0
0x32554  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x32559  ldloc.0
0x3255a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x3255f  ldloc.2
0x32560  ldloc.0
0x32561  ldfld    string <>c__DisplayClass34_0::installDir
0x32566  ldloca.s 6
0x32568  ldflda   string <>c__DisplayClass34_1::layoutDir
0x3256d  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string installerFile, string installDir, string& layoutDir)
0x32572  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::.ctor(var<u1>)
0x32577  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x3257c  br.s     loc_325A6
0x3257e  ldarg.0
0x3257f  ldloc.0
0x32580  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass34_0::pkg
0x32585  ldc.i4.1
0x32586  ldc.i4.0
0x32587  ldc.i4   0x643
0x3258c  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x32591  ldnull
0x32592  ldnull
0x32593  ldloc.s  7
0x32595  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x3259a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x3259f  stloc.s  0x10
0x325a1  leave    loc_327C4
0x325a6  ldloca.s 0xB
0x325a8  ldarg.0
0x325a9  ldloc.1
0x325aa  ldloc.0
0x325ab  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x325b0  call     instance string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetNgenConfigApplication(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variableMapping)
0x325b5  stfld    string <>c__DisplayClass34_3::defaultNgenApplication
0x325ba  ldloc.s  7
0x325bc  ldfld    class Microsoft.VisualStudio.Setup.Services.FileLogger <>c__DisplayClass34_2::logger
0x325c1  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExtractionQueryParts
0x325c6  call     T0x2B000003
0x325cb  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string format, object[] args)
0x325d0  ldloca.s 0xB
0x325d2  ldarg.0
0x325d3  ldloc.0
0x325d4  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_0::nonEnvironmentVars
0x325d9  ldloc.0
0x325da  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x325df  dup
0x325e0  brtrue.s loc_325E6
0x325e2  pop
0x325e3  ldnull
0x325e4  br.s     loc_325EB
0x325e6  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_FolderMappings()
0x325eb  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetResolvedFolderMappings(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> folderMappings)
0x325f0  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass34_3::resolvedFolderMapping
0x325f5  ldloca.s 0xB
0x325f7  ldarg.0
0x325f8  ldarg.0
0x325f9  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x325fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::get_Value()
0x32603  ldloc.1
0x32604  call     instance bool Microsoft.VisualStudio.Setup.Installer.VsixInstaller::CanOverwriteFiles(valuetype Microsoft.VisualStudio.Setup.Installer.VsixType vsixType, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsix)
0x32609  ldc.i4.0
0x3260a  ceq
0x3260c  stfld    bool <>c__DisplayClass34_3::preventFileOverwrite
0x32611  ldloca.s 0xB
0x32613  ldnull
0x32614  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass34_3::result
0x32619  ldloca.s 0xB
0x3261b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart>::.ctor()
0x32620  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart> <>c__DisplayClass34_3::partsToApplyLast
0x32625  ldloc.0
0x32626  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage <>c__DisplayClass34_0::embeddedVsixPkg
0x3262b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile>::get_Files()
  ... truncated ...
```
