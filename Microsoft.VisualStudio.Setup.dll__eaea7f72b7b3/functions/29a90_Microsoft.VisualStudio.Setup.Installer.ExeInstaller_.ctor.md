# Microsoft.VisualStudio.Setup.Installer.ExeInstaller::.ctor

- ea: `0x29a90`
- end: `0x29b28`
- name: `Microsoft.VisualStudio.Setup.Installer.ExeInstaller::.ctor`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d500`
- `0x60110`

## callees

- `0x2ad20`
- `0x2b840`
- `0x2d760`

## string_xrefs

- `0x29ac8`: `MidInstall_Busy`
- `0x29aef`: `MidInstall_Busy`
- `0x29b16`: `MidInstall_Busy`

## pseudocode

```c

```

## disassembly

```asm
0x29a90  ldarg.0
0x29a91  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultComparer::ReturnCodeAndMessageIdHResultCompatible
0x29a96  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x29a9b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x29aa0  ldarg.0
0x29aa1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ExeInstallerReturnCodes::.ctor()
0x29aa6  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection Microsoft.VisualStudio.Setup.Installer.ExeInstaller::<ReturnCodes>k__BackingField
0x29aab  ldarg.0
0x29aac  ldarg.1
0x29aad  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::.ctor(class [mscorlib]System.IServiceProvider services)
0x29ab2  ldarg.0
0x29ab3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x29ab8  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor()
0x29abd  dup
0x29abe  ldc.i4   0x652
0x29ac3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_ReturnCode(int32)
0x29ac8  ldstr    aMidinstallBusy// "MidInstall_Busy"
0x29acd  ldc.i4.0
0x29ace  ldc.i4.0
0x29acf  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallRetry::.ctor(string resourceId, [opt] int32 retryCount, [opt] int32 userRetryCount)
0x29ad4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::Add(var<u1>, !!T0)
0x29ad9  ldarg.0
0x29ada  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x29adf  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor()
0x29ae4  dup
0x29ae5  ldc.i4   0x80040712
0x29aea  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_ReturnCode(int32)
0x29aef  ldstr    aMidinstallBusy// "MidInstall_Busy"
0x29af4  ldc.i4.0
0x29af5  ldc.i4.0
0x29af6  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallRetry::.ctor(string resourceId, [opt] int32 retryCount, [opt] int32 userRetryCount)
0x29afb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::Add(var<u1>, !!T0)
0x29b00  ldarg.0
0x29b01  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x29b06  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor()
0x29b0b  dup
0x29b0c  ldc.i4   0x80040707
0x29b11  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_ReturnCode(int32)
0x29b16  ldstr    aMidinstallBusy// "MidInstall_Busy"
0x29b1b  ldc.i4.0
0x29b1c  ldc.i4.0
0x29b1d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallRetry::.ctor(string resourceId, [opt] int32 retryCount, [opt] int32 userRetryCount)
0x29b22  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::Add(var<u1>, !!T0)
0x29b27  ret
```
