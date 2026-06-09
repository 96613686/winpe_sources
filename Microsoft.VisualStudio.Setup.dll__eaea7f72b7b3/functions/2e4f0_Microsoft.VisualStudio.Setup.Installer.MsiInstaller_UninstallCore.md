# Microsoft.VisualStudio.Setup.Installer.MsiInstaller::UninstallCore

- ea: `0x2e4f0`
- end: `0x2e688`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiInstaller::UninstallCore`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x2b940`
- `0x2bee0`
- `0x2c050`
- `0x2e4f0`
- `0x2e860`
- `0x2e910`
- `0x2ea20`
- `0x2ec40`
- `0x2f290`
- `0x35350`
- `0x6cdc0`

## string_xrefs

- `0x2e61a`: `InvalidInputPaths`
- `0x2e5b4`: `Uninstalling MSI package '{0}' using compatible ProductCode '{1}'.`
- `0x2e62e`: ` REMOVE=ALL `

## pseudocode

```c

```

## disassembly

```asm
0x2e4f0  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x2e4f5  stloc.0
0x2e4f6  ldloc.0
0x2e4f7  ldarg.0
0x2e4f8  stfld    class Microsoft.VisualStudio.Setup.Installer.MsiInstaller <>c__DisplayClass19_0::<>4__this
0x2e4fd  ldloc.0
0x2e4fe  ldarg.0
0x2e4ff  ldarg.2
0x2e500  call     T0x2B000174
0x2e505  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e50a  ldarg.0
0x2e50b  ldloc.0
0x2e50c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e511  call     instance void Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package)
0x2e516  ldarg.0
0x2e517  ldftn    instance valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::OnMessage(valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.InstallMessage messageType, class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.Record record, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageButtons buttons, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageIcon icon, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageDefaultButton defaultButton)
0x2e51d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler::.ctor(object object, native int method)
0x2e522  ldc.i4.0
0x2e523  ldarg.0
0x2e524  ldfld    bool Microsoft.VisualStudio.Setup.Installer.MsiInstaller::msiZapDisabled
0x2e529  newobj   instance void Microsoft.VisualStudio.Setup.Installer.MsiUserInterfaceHandler::.ctor(class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler handler, [opt] bool force, [opt] bool msiZapDisabled)
0x2e52e  stloc.1
0x2e52f  ldarg.2
0x2e530  brfalse.s loc_2E545
0x2e532  ldarg.0
0x2e533  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService Microsoft.VisualStudio.Setup.Installer.MsiInstaller::windowsInstallerService
0x2e538  ldarg.0
0x2e539  ldarg.2
0x2e53a  ldnull
0x2e53b  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetLogFileName([opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string installerFile)
0x2e540  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::EnableLog(string)
0x2e545  ldloc.0
0x2e546  ldnull
0x2e547  stfld    string <>c__DisplayClass19_0::installerFile
0x2e54c  ldloc.0
0x2e54d  ldarg.0
0x2e54e  ldloc.0
0x2e54f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e554  ldarg.1
0x2e555  call     instance string Microsoft.VisualStudio.Setup.Installer.MsiInstaller::GetStandardMSIProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage msiPkg, [opt] string installDir)
0x2e55a  stfld    string <>c__DisplayClass19_0::properties
0x2e55f  ldloc.0
0x2e560  ldloc.0
0x2e561  ldfld    string <>c__DisplayClass19_0::properties
0x2e566  ldstr    aIgnoredependen// " IGNOREDEPENDENCIES=ALL "
0x2e56b  call     string [mscorlib]System.String::Concat(string, string)
0x2e570  stfld    string <>c__DisplayClass19_0::properties
0x2e575  ldloc.0
0x2e576  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e57b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e580  dup
0x2e581  brtrue.s loc_2E58F
0x2e583  pop
0x2e584  ldloc.0
0x2e585  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e58a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2e58f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e594  brtrue.s loc_2E605
0x2e596  ldloc.0
0x2e597  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e59c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e5a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e5a6  brtrue.s loc_2E5E0
0x2e5a8  ldarg.0
0x2e5a9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e5ae  dup
0x2e5af  brtrue.s loc_2E5B4
0x2e5b1  pop
0x2e5b2  br.s     loc_2E5E0
0x2e5b4  ldstr    aUninstallingMs// "Uninstalling MSI package '{0}' using co"...
0x2e5b9  ldc.i4.2
0x2e5ba  newarr   [mscorlib]System.Object
0x2e5bf  dup
0x2e5c0  ldc.i4.0
0x2e5c1  ldloc.0
0x2e5c2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e5c7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2e5cc  stelem.ref
0x2e5cd  dup
0x2e5ce  ldc.i4.1
0x2e5cf  ldloc.0
0x2e5d0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e5d5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e5da  stelem.ref
0x2e5db  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2e5e0  ldarg.0
0x2e5e1  ldloc.0
0x2e5e2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e5e7  ldloc.0
0x2e5e8  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass19_0::<UninstallCore>b__0()
0x2e5ee  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2e5f3  ldarg.0
0x2e5f4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.MsiInstaller::retryCodes
0x2e5f9  ldc.i4.3
0x2e5fa  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DoAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2e5ff  stloc.2
0x2e600  leave    loc_2E686
0x2e605  ldarg.3
0x2e606  brfalse.s loc_2E65F
0x2e608  ldarg.0
0x2e609  ldarg.3
0x2e60a  ldarg.2
0x2e60b  ldloc.0
0x2e60c  ldflda   string <>c__DisplayClass19_0::installerFile
0x2e611  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x2e616  brtrue.s loc_2E627
0x2e618  ldc.i4.4
0x2e619  ldc.i4.0
0x2e61a  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2e61f  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2e624  stloc.2
0x2e625  leave.s  loc_2E686
0x2e627  ldloc.0
0x2e628  ldloc.0
0x2e629  ldfld    string <>c__DisplayClass19_0::properties
0x2e62e  ldstr    aRemoveAll// " REMOVE=ALL "
0x2e633  call     string [mscorlib]System.String::Concat(string, string)
0x2e638  stfld    string <>c__DisplayClass19_0::properties
0x2e63d  ldarg.0
0x2e63e  ldloc.0
0x2e63f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e644  ldloc.0
0x2e645  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass19_0::<UninstallCore>b__1()
0x2e64b  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2e650  ldarg.0
0x2e651  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.MsiInstaller::retryCodes
0x2e656  ldc.i4.3
0x2e657  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DoAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2e65c  stloc.2
0x2e65d  leave.s  loc_2E686
0x2e65f  ldarg.0
0x2e660  ldc.i4.0
0x2e661  ldloc.0
0x2e662  ldfld    string <>c__DisplayClass19_0::installerFile
0x2e667  ldloc.0
0x2e668  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass19_0::msiPkg
0x2e66d  ldc.i4.3
0x2e66e  ldloc.0
0x2e66f  ldfld    string <>c__DisplayClass19_0::properties
0x2e674  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::ReturnMsiCode(int32 code, string installerFile, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage msiPackage, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, string properties)
0x2e679  stloc.2
0x2e67a  leave.s  loc_2E686
0x2e67c  ldloc.1
0x2e67d  brfalse.s loc_2E685
0x2e67f  ldloc.1
0x2e680  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e685  endfinally
0x2e686  ldloc.2
0x2e687  ret
```
