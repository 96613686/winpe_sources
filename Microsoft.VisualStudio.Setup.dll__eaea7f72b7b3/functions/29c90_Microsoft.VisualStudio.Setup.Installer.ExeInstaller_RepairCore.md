# Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RepairCore

- ea: `0x29c90`
- end: `0x29d54`
- name: `Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RepairCore`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x29c90`
- `0x2b940`
- `0x2bee0`
- `0x2c3f0`
- `0x6c470`

## string_xrefs

- `0x29d29`: `InvalidInputPaths`
- `0x29cfe`: `PackageNoRepair`
- `0x29d0f`: `PackageNoRepair`

## pseudocode

```c

```

## disassembly

```asm
0x29c90  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x29c95  stloc.0
0x29c96  ldloc.0
0x29c97  ldarg.0
0x29c98  stfld    class Microsoft.VisualStudio.Setup.Installer.ExeInstaller <>c__DisplayClass12_0::<>4__this
0x29c9d  ldloc.0
0x29c9e  ldarg.2
0x29c9f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass12_0::pkg
0x29ca4  ldloc.0
0x29ca5  ldarg.3
0x29ca6  stfld    string <>c__DisplayClass12_0::localPath
0x29cab  ldloc.0
0x29cac  ldnull
0x29cad  stfld    string <>c__DisplayClass12_0::logFileName
0x29cb2  ldloc.0
0x29cb3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass12_0::pkg
0x29cb8  brfalse.s loc_29CCD
0x29cba  ldloc.0
0x29cbb  ldarg.0
0x29cbc  ldloc.0
0x29cbd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass12_0::pkg
0x29cc2  ldnull
0x29cc3  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetLogFileName([opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string installerFile)
0x29cc8  stfld    string <>c__DisplayClass12_0::logFileName
0x29ccd  ldloc.0
0x29cce  ldarg.0
0x29ccf  ldloc.0
0x29cd0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage <>c__DisplayClass12_0::pkg
0x29cd5  call     T0x2B000164
0x29cda  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExePackage <>c__DisplayClass12_0::exePkg
0x29cdf  ldloc.0
0x29ce0  ldloc.0
0x29ce1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExePackage <>c__DisplayClass12_0::exePkg
0x29ce6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExePackage::get_RepairParams()
0x29ceb  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter <>c__DisplayClass12_0::repairParams
0x29cf0  ldloc.0
0x29cf1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter <>c__DisplayClass12_0::repairParams
0x29cf6  brtrue.s loc_29D1A
0x29cf8  ldarg.0
0x29cf9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x29cfe  ldstr    aPackagenorepai// "PackageNoRepair"
0x29d03  call     T0x2B000003
0x29d08  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x29d0d  ldc.i4.1
0x29d0e  ldc.i4.0
0x29d0f  ldstr    aPackagenorepai// "PackageNoRepair"
0x29d14  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x29d19  ret
0x29d1a  ldloc.0
0x29d1b  ldfld    string <>c__DisplayClass12_0::localPath
0x29d20  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x29d25  brtrue.s loc_29D34
0x29d27  ldc.i4.4
0x29d28  ldc.i4.0
0x29d29  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x29d2e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x29d33  ret
0x29d34  ldarg.0
0x29d35  ldloc.0
0x29d36  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExePackage <>c__DisplayClass12_0::exePkg
0x29d3b  ldloc.0
0x29d3c  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass12_0::<RepairCore>b__0()
0x29d42  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x29d47  ldarg.0
0x29d48  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x29d4d  ldc.i4.2
0x29d4e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::ExecutePackageWithMessageBusRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x29d53  ret
```
