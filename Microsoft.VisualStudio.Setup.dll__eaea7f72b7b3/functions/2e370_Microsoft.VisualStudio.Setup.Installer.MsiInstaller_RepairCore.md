# Microsoft.VisualStudio.Setup.Installer.MsiInstaller::RepairCore

- ea: `0x2e370`
- end: `0x2e4e3`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiInstaller::RepairCore`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2b940`
- `0x2bee0`
- `0x2c050`
- `0x2e370`
- `0x2e860`
- `0x2ea20`
- `0x2eac0`
- `0x2ec40`
- `0x2f290`
- `0x35350`
- `0x6cca0`

## string_xrefs

- `0x2e3c1`: `InvalidInputPaths`
- `0x2e43a`: ` REINSTALL=ALL  REINSTALLMODE="cmuse" IGNOREDEPENDENCIES=ALL `
- `0x2e467`: `Repairing MSI package '{0}' using compatible ProductCode '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x2e370  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x2e375  stloc.0
0x2e376  ldloc.0
0x2e377  ldarg.0
0x2e378  stfld    class Microsoft.VisualStudio.Setup.Installer.MsiInstaller <>c__DisplayClass18_0::<>4__this
0x2e37d  ldloc.0
0x2e37e  ldarg.0
0x2e37f  ldarg.2
0x2e380  call     T0x2B000174
0x2e385  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e38a  ldarg.0
0x2e38b  ldloc.0
0x2e38c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e391  call     instance void Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package)
0x2e396  ldloc.0
0x2e397  ldnull
0x2e398  stfld    string <>c__DisplayClass18_0::installerFile
0x2e39d  ldloc.0
0x2e39e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e3a3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e3a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e3ad  brfalse.s loc_2E3CC
0x2e3af  ldarg.0
0x2e3b0  ldarg.3
0x2e3b1  ldarg.2
0x2e3b2  ldloc.0
0x2e3b3  ldflda   string <>c__DisplayClass18_0::installerFile
0x2e3b8  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x2e3bd  brtrue.s loc_2E3CC
0x2e3bf  ldc.i4.4
0x2e3c0  ldc.i4.0
0x2e3c1  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2e3c6  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2e3cb  ret
0x2e3cc  ldarg.0
0x2e3cd  ldftn    instance valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::OnMessage(valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.InstallMessage messageType, class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.Record record, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageButtons buttons, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageIcon icon, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageDefaultButton defaultButton)
0x2e3d3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler::.ctor(object object, native int method)
0x2e3d8  ldc.i4.0
0x2e3d9  ldarg.0
0x2e3da  ldfld    bool Microsoft.VisualStudio.Setup.Installer.MsiInstaller::msiZapDisabled
0x2e3df  newobj   instance void Microsoft.VisualStudio.Setup.Installer.MsiUserInterfaceHandler::.ctor(class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler handler, [opt] bool force, [opt] bool msiZapDisabled)
0x2e3e4  stloc.1
0x2e3e5  ldarg.2
0x2e3e6  brfalse.s loc_2E3FB
0x2e3e8  ldarg.0
0x2e3e9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService Microsoft.VisualStudio.Setup.Installer.MsiInstaller::windowsInstallerService
0x2e3ee  ldarg.0
0x2e3ef  ldarg.2
0x2e3f0  ldnull
0x2e3f1  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetLogFileName([opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string installerFile)
0x2e3f6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::EnableLog(string)
0x2e3fb  ldloc.0
0x2e3fc  ldarg.0
0x2e3fd  ldloc.0
0x2e3fe  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e403  ldarg.1
0x2e404  call     instance string Microsoft.VisualStudio.Setup.Installer.MsiInstaller::GetStandardMSIProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage msiPkg, [opt] string installDir)
0x2e409  stfld    string <>c__DisplayClass18_0::properties
0x2e40e  ldloc.0
0x2e40f  ldfld    string <>c__DisplayClass18_0::installerFile
0x2e414  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e419  brtrue.s loc_2E433
0x2e41b  ldloc.0
0x2e41c  ldarg.0
0x2e41d  ldloc.0
0x2e41e  ldfld    string <>c__DisplayClass18_0::installerFile
0x2e423  ldloc.0
0x2e424  ldfld    string <>c__DisplayClass18_0::properties
0x2e429  call     instance string Microsoft.VisualStudio.Setup.Installer.MsiInstaller::AppendPatchPropertyIfApplicable(string installerFile, string currentCommandLine)
0x2e42e  stfld    string <>c__DisplayClass18_0::properties
0x2e433  ldloc.0
0x2e434  ldloc.0
0x2e435  ldfld    string <>c__DisplayClass18_0::properties
0x2e43a  ldstr    aReinstallAllRe// " REINSTALL=ALL  REINSTALLMODE=\"cmuse\""...
0x2e43f  call     string [mscorlib]System.String::Concat(string, string)
0x2e444  stfld    string <>c__DisplayClass18_0::properties
0x2e449  ldloc.0
0x2e44a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e44f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e454  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e459  brtrue.s loc_2E4B5
0x2e45b  ldarg.0
0x2e45c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e461  dup
0x2e462  brtrue.s loc_2E467
0x2e464  pop
0x2e465  br.s     loc_2E493
0x2e467  ldstr    aRepairingMsiPa// "Repairing MSI package '{0}' using compa"...
0x2e46c  ldc.i4.2
0x2e46d  newarr   [mscorlib]System.Object
0x2e472  dup
0x2e473  ldc.i4.0
0x2e474  ldloc.0
0x2e475  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e47a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2e47f  stelem.ref
0x2e480  dup
0x2e481  ldc.i4.1
0x2e482  ldloc.0
0x2e483  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e488  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2e48d  stelem.ref
0x2e48e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2e493  ldarg.0
0x2e494  ldloc.0
0x2e495  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e49a  ldloc.0
0x2e49b  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass18_0::<RepairCore>b__0()
0x2e4a1  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2e4a6  ldarg.0
0x2e4a7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.MsiInstaller::retryCodes
0x2e4ac  ldc.i4.2
0x2e4ad  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DoAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2e4b2  stloc.2
0x2e4b3  leave.s  loc_2E4E1
0x2e4b5  ldarg.0
0x2e4b6  ldloc.0
0x2e4b7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage <>c__DisplayClass18_0::msiPkg
0x2e4bc  ldloc.0
0x2e4bd  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass18_0::<RepairCore>b__1()
0x2e4c3  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2e4c8  ldarg.0
0x2e4c9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.MsiInstaller::retryCodes
0x2e4ce  ldc.i4.2
0x2e4cf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DoAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2e4d4  stloc.2
0x2e4d5  leave.s  loc_2E4E1
0x2e4d7  ldloc.1
0x2e4d8  brfalse.s loc_2E4E0
0x2e4da  ldloc.1
0x2e4db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e4e0  endfinally
0x2e4e1  ldloc.2
0x2e4e2  ret
```
