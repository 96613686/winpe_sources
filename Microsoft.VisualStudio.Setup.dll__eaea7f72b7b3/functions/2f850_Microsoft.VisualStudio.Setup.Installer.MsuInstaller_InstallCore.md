# Microsoft.VisualStudio.Setup.Installer.MsuInstaller::InstallCore

- ea: `0x2f850`
- end: `0x2faa9`
- name: `Microsoft.VisualStudio.Setup.Installer.MsuInstaller::InstallCore`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2b940`
- `0x2bee0`
- `0x2c050`
- `0x2c3f0`
- `0x2f850`
- `0x2fbf0`
- `0x6cf00`

## string_xrefs

- `0x2f8a4`: `PackageNoInstall`
- `0x2f8dd`: `InvalidInputPaths`
- `0x2f919`: `InvalidInputPaths`
- `0x2f954`: `InvalidInputPaths`
- `0x2f9bf`: `InvalidInputPaths`
- `0x2fa00`: `InvalidInputPaths`
- `0x2fa5c`: `InvalidInputPaths`
- `0x2f8bd`: `Local path '`
- `0x2f8fd`: `Could not get valid installer file path from package local path '`
- `0x2f934`: `Installer file '`

## pseudocode

```c

```

## disassembly

```asm
0x2f850  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x2f855  stloc.0
0x2f856  ldloc.0
0x2f857  ldarg.0
0x2f858  stfld    class Microsoft.VisualStudio.Setup.Installer.MsuInstaller <>c__DisplayClass5_0::<>4__this
0x2f85d  ldloc.0
0x2f85e  ldarg.0
0x2f85f  ldarg.3
0x2f860  ldnull
0x2f861  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetLogFileName([opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string installerFile)
0x2f866  stfld    string <>c__DisplayClass5_0::logFileName
0x2f86b  ldarg.0
0x2f86c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2f871  stloc.1
0x2f872  ldloc.0
0x2f873  ldarg.0
0x2f874  ldarg.3
0x2f875  call     T0x2B00017A
0x2f87a  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsuPackage <>c__DisplayClass5_0::msuPkg
0x2f87f  ldloc.0
0x2f880  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsuPackage <>c__DisplayClass5_0::msuPkg
0x2f885  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsuPackage::get_FileName()
0x2f88a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f88f  brfalse.s loc_2F8AF
0x2f891  ldloc.1
0x2f892  ldnull
0x2f893  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoInstall()
0x2f898  call     T0x2B000003
0x2f89d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f8a2  ldc.i4.4
0x2f8a3  ldc.i4.0
0x2f8a4  ldstr    aPackagenoinsta// "PackageNoInstall"
0x2f8a9  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2f8ae  ret
0x2f8af  ldsfld   string [mscorlib]System.String::Empty
0x2f8b4  stloc.2
0x2f8b5  ldarg.1
0x2f8b6  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x2f8bb  brtrue.s loc_2F8EF
0x2f8bd  ldstr    aLocalPath// "Local path '"
0x2f8c2  ldarg.1
0x2f8c3  ldstr    aIsNotValid// "' is not valid."
0x2f8c8  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f8cd  stloc.2
0x2f8ce  ldloc.1
0x2f8cf  ldnull
0x2f8d0  ldloc.2
0x2f8d1  call     T0x2B000003
0x2f8d6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f8db  ldc.i4.4
0x2f8dc  ldc.i4.0
0x2f8dd  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2f8e2  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2f8e7  dup
0x2f8e8  ldloc.2
0x2f8e9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2f8ee  ret
0x2f8ef  ldarg.0
0x2f8f0  ldarg.1
0x2f8f1  ldarg.3
0x2f8f2  ldloca.s 3
0x2f8f4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x2f8f9  brtrue.s loc_2F924
0x2f8fb  ldloc.1
0x2f8fc  ldnull
0x2f8fd  ldstr    aCouldNotGetVal// "Could not get valid installer file path"...
0x2f902  ldarg.1
0x2f903  ldstr    asc_7F7FA// "'."
0x2f908  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f90d  call     T0x2B000003
0x2f912  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f917  ldc.i4.4
0x2f918  ldc.i4.0
0x2f919  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2f91e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2f923  ret
0x2f924  ldloc.3
0x2f925  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f92a  brtrue.s loc_2F934
0x2f92c  ldloc.3
0x2f92d  call     bool [mscorlib]System.IO.File::Exists(string)
0x2f932  brtrue.s loc_2F966
0x2f934  ldstr    aInstallerFile// "Installer file '"
0x2f939  ldloc.3
0x2f93a  ldstr    aDoesNotExist// "' does not exist."
0x2f93f  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f944  stloc.2
0x2f945  ldloc.1
0x2f946  ldnull
0x2f947  ldloc.2
0x2f948  call     T0x2B000003
0x2f94d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f952  ldc.i4.4
0x2f953  ldc.i4.0
0x2f954  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2f959  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2f95e  dup
0x2f95f  ldloc.2
0x2f960  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2f965  ret
0x2f966  ldnull
0x2f967  stloc.s  4
0x2f969  ldloc.1
0x2f96a  brfalse.s loc_2F991
0x2f96c  ldloc.1
0x2f96d  ldstr    aExpandingMsuPa// "Expanding MSU package '"
0x2f972  ldloc.0
0x2f973  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsuPackage <>c__DisplayClass5_0::msuPkg
0x2f978  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2f97d  ldstr    asc_7F7FA// "'."
0x2f982  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f987  call     T0x2B000003
0x2f98c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2f991  ldarg.0
0x2f992  ldloc.3
0x2f993  call     instance string Microsoft.VisualStudio.Setup.Installer.MsuInstaller::ExpandPackage(string originalPath)
0x2f998  stloc.s  4
0x2f99a  leave.s  loc_2F9D7
0x2f99c  stloc.s  5
0x2f99e  ldstr    aCabFileCouldNo// "Cab file could not be expanded from loc"...
0x2f9a3  ldloc.3
0x2f9a4  ldstr    asc_7F7FA// "'."
0x2f9a9  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f9ae  stloc.2
0x2f9af  ldloc.1
0x2f9b0  ldloc.s  5
0x2f9b2  ldloc.2
0x2f9b3  call     T0x2B000003
0x2f9b8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f9bd  ldc.i4.4
0x2f9be  ldc.i4.0
0x2f9bf  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2f9c4  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2f9c9  dup
0x2f9ca  ldloc.2
0x2f9cb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2f9d0  stloc.s  6
0x2f9d2  leave    loc_2FAA6
0x2f9d7  ldloc.s  4
0x2f9d9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f9de  brfalse.s loc_2FA12
0x2f9e0  ldstr    aCabFileCouldNo// "Cab file could not be expanded from loc"...
0x2f9e5  ldloc.3
0x2f9e6  ldstr    asc_7F7FA// "'."
0x2f9eb  call     string [mscorlib]System.String::Concat(string, string, string)
0x2f9f0  stloc.2
0x2f9f1  ldloc.1
0x2f9f2  ldnull
0x2f9f3  ldloc.2
0x2f9f4  call     T0x2B000003
0x2f9f9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f9fe  ldc.i4.4
0x2f9ff  ldc.i4.0
0x2fa00  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2fa05  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2fa0a  dup
0x2fa0b  ldloc.2
0x2fa0c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2fa11  ret
0x2fa12  ldloc.0
0x2fa13  ldloc.s  4
0x2fa15  ldloc.3
0x2fa16  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x2fa1b  ldstr    aCab// ".cab"
0x2fa20  call     string [mscorlib]System.String::Concat(string, string)
0x2fa25  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2fa2a  stfld    string <>c__DisplayClass5_0::cabName
0x2fa2f  ldloc.0
0x2fa30  ldfld    string <>c__DisplayClass5_0::cabName
0x2fa35  call     bool [mscorlib]System.IO.File::Exists(string)
0x2fa3a  brtrue.s loc_2FA71
0x2fa3c  ldstr    aCabFileNotFoun// "Cab file not found after expanding the "...
0x2fa41  ldloc.3
0x2fa42  ldstr    asc_7F7FA// "'."
0x2fa47  call     string [mscorlib]System.String::Concat(string, string, string)
0x2fa4c  stloc.2
0x2fa4d  ldloc.1
0x2fa4e  ldnull
0x2fa4f  ldloc.2
0x2fa50  call     T0x2B000003
0x2fa55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2fa5a  ldc.i4.4
0x2fa5b  ldc.i4.0
0x2fa5c  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x2fa61  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2fa66  dup
0x2fa67  ldloc.2
0x2fa68  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2fa6d  stloc.s  6
0x2fa6f  leave.s  loc_2FAA6
0x2fa71  ldarg.0
0x2fa72  ldloc.0
0x2fa73  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsuPackage <>c__DisplayClass5_0::msuPkg
0x2fa78  ldloc.0
0x2fa79  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass5_0::<InstallCore>b__0()
0x2fa7f  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2fa84  ldarg.0
0x2fa85  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.MsuInstaller::retryCodes
0x2fa8a  ldc.i4.1
0x2fa8b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::ExecutePackageWithMessageBusRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2fa90  stloc.s  6
0x2fa92  leave.s  loc_2FAA6
0x2fa94  ldloc.s  4
0x2fa96  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2fa9b  brfalse.s loc_2FAA5
0x2fa9d  ldloc.s  4
0x2fa9f  ldc.i4.1
0x2faa0  call     void [mscorlib]System.IO.Directory::Delete(string, bool)
0x2faa5  endfinally
0x2faa6  ldloc.s  6
0x2faa8  ret
```
