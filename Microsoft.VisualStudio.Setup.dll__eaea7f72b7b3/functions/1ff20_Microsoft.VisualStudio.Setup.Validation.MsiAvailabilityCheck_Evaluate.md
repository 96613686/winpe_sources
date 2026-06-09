# Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::Evaluate

- ea: `0x1ff20`
- end: `0x200d7`
- name: `Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::Evaluate`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10a20`
- `0x199a0`
- `0x1ff20`
- `0x200e0`
- `0x20850`
- `0x21b80`
- `0x21c50`
- `0x21ce0`
- `0x2f290`
- `0x35350`

## string_xrefs

- `0x20079`: `Precheck_TestingMsiInstallationCheck`
- `0x1ff4c`: `Microsoft.VisualStudio.Setup.TestMsi.msi`
- `0x1ff72`: `Test MSI {0} does not exist.`
- `0x1fff9`: `Test MSI failed signature validation`
- `0x20017`: `Test MSI {0} failed validation. We cannot detect if the Windows Installer service is running.`
- `0x20052`: `TestMSI`
- `0x20068`: ` REBOOT = ReallySuppress ARPSYSTEMCOMPONENT=1 ALLUSERS=1 MSIFASTINSTALL=7`
- `0x200ad`: `Precheck: Failure in checking Windows Installer availability via installing test MSI: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1ff20  ldarg.0
0x1ff21  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::fileSystem
0x1ff26  ldc.i4.4
0x1ff27  newarr   [mscorlib]System.String
0x1ff2c  dup
0x1ff2d  ldc.i4.0
0x1ff2e  ldarg.0
0x1ff2f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::fileSystem
0x1ff34  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x1ff39  stelem.ref
0x1ff3a  dup
0x1ff3b  ldc.i4.1
0x1ff3c  ldsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x1ff41  stelem.ref
0x1ff42  dup
0x1ff43  ldc.i4.2
0x1ff44  ldsfld   string Microsoft.VisualStudio.Setup.Validation.Constants::PrecheckToolsFolder
0x1ff49  stelem.ref
0x1ff4a  dup
0x1ff4b  ldc.i4.3
0x1ff4c  ldstr    aMicrosoftVisua_24// "Microsoft.VisualStudio.Setup.TestMsi.ms"...
0x1ff51  stelem.ref
0x1ff52  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CombinePath(string[])
0x1ff57  stloc.0
0x1ff58  ldarg.0
0x1ff59  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::fileSystem
0x1ff5e  ldloc.0
0x1ff5f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x1ff64  brtrue.s loc_1FF88
0x1ff66  ldarg.0
0x1ff67  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::logger
0x1ff6c  dup
0x1ff6d  brtrue.s loc_1FF72
0x1ff6f  pop
0x1ff70  br.s     loc_1FF86
0x1ff72  ldstr    aTestMsi0DoesNo// "Test MSI {0} does not exist."
0x1ff77  ldc.i4.1
0x1ff78  newarr   [mscorlib]System.Object
0x1ff7d  dup
0x1ff7e  ldc.i4.0
0x1ff7f  ldloc.0
0x1ff80  stelem.ref
0x1ff81  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1ff86  ldnull
0x1ff87  ret
0x1ff88  ldarg.0
0x1ff89  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::precheckParameters
0x1ff8e  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_BootstrapperAction()
0x1ff93  ldc.i4.3
0x1ff94  beq.s    loc_1FF9E
0x1ff96  ldarg.0
0x1ff97  call     instance bool Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::HasPackageTriggeringPrecheck()
0x1ff9c  brtrue.s loc_1FFA0
0x1ff9e  ldnull
0x1ff9f  ret
0x1ffa0  ldsfld   class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler <>c::<>9__16_0
0x1ffa5  dup
0x1ffa6  brtrue.s loc_1FFBF
0x1ffa8  pop
0x1ffa9  ldsfld   class <>c <>c::<>9
0x1ffae  ldftn    instance valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageResult <>c::<Evaluate>b__16_0(valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.InstallMessage _, class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.Record _, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageButtons _, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageIcon _, valuetype Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.MessageDefaultButton _)
0x1ffb4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler::.ctor(object object, native int method)
0x1ffb9  dup
0x1ffba  stsfld   class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler <>c::<>9__16_0
0x1ffbf  ldc.i4.0
0x1ffc0  ldc.i4.0
0x1ffc1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.MsiUserInterfaceHandler::.ctor(class Microsoft.VisualStudio.Setup.Installer.WindowsInstaller.ExternalUIRecordHandler handler, [opt] bool force, [opt] bool msiZapDisabled)
0x1ffc6  stloc.1
0x1ffc7  ldarg.0
0x1ffc8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::fileSystem
0x1ffcd  ldloc.0
0x1ffce  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x1ffd3  stloc.2
0x1ffd4  ldarg.0
0x1ffd5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::signatureManager
0x1ffda  ldloc.2
0x1ffdb  ldloc.0
0x1ffdc  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Extensions::VerifyMicrosoftSignature(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager signatureManager, class [mscorlib]System.IO.Stream file, [opt] string path)
0x1ffe1  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x1ffe6  brfalse.s loc_20032
0x1ffe8  ldarg.0
0x1ffe9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::telemetry
0x1ffee  dup
0x1ffef  brtrue.s loc_1FFF4
0x1fff1  pop
0x1fff2  br.s     loc_2000B
0x1fff4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::TESTMSIERROREVENT
0x1fff9  ldstr    aTestMsiFailedS// "Test MSI failed signature validation"
0x1fffe  ldnull
0x1ffff  ldnull
0x20000  ldnull
0x20001  ldc.i4.0
0x20002  ldnull
0x20003  ldc.i4.0
0x20004  ldnull
0x20005  ldc.i4.0
0x20006  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2000b  ldarg.0
0x2000c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::logger
0x20011  dup
0x20012  brtrue.s loc_20017
0x20014  pop
0x20015  br.s     loc_2002B
0x20017  ldstr    aTestMsi0Failed// "Test MSI {0} failed validation. We cann"...
0x2001c  ldc.i4.1
0x2001d  newarr   [mscorlib]System.Object
0x20022  dup
0x20023  ldc.i4.0
0x20024  ldloc.0
0x20025  stelem.ref
0x20026  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2002b  ldnull
0x2002c  stloc.3
0x2002d  leave    loc_200D5
0x20032  leave.s  loc_2003E
0x20034  ldloc.2
0x20035  brfalse.s loc_2003D
0x20037  ldloc.2
0x20038  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2003d  endfinally
0x2003e  ldarg.0
0x2003f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::logger
0x20044  brfalse.s loc_20061
0x20046  ldarg.0
0x20047  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::windowsInstallerService
0x2004c  ldarg.0
0x2004d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::logger
0x20052  ldstr    aTestmsi// "TestMSI"
0x20057  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::GenerateLogFileName(string)
0x2005c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::EnableLog(string)
0x20061  ldarg.0
0x20062  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::windowsInstallerService
0x20067  ldloc.0
0x20068  ldstr    aRebootReallysu// " REBOOT = ReallySuppress ARPSYSTEMCOMPO"...
0x2006d  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::InstallProduct(string, string)
0x20072  brfalse.s loc_2009D
0x20074  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x20079  ldstr    aPrecheckTestin// "Precheck_TestingMsiInstallationCheck"
0x2007e  call     T0x2B000003
0x20083  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x20088  dup
0x20089  ldc.i4.0
0x2008a  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x2008f  dup
0x20090  ldc.i4   0x1F4C
0x20095  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x2009a  stloc.3
0x2009b  leave.s  loc_200D5
0x2009d  leave.s  loc_200D3
0x2009f  stloc.s  4
0x200a1  ldarg.0
0x200a2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MsiAvailabilityCheck::logger
0x200a7  dup
0x200a8  brtrue.s loc_200AD
0x200aa  pop
0x200ab  br.s     loc_200C7
0x200ad  ldstr    aPrecheckFailur_1// "Precheck: Failure in checking Windows I"...
0x200b2  ldc.i4.1
0x200b3  newarr   [mscorlib]System.Object
0x200b8  dup
0x200b9  ldc.i4.0
0x200ba  ldloc.s  4
0x200bc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x200c1  stelem.ref
0x200c2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x200c7  leave.s  loc_200D3
0x200c9  ldloc.1
0x200ca  brfalse.s loc_200D2
0x200cc  ldloc.1
0x200cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x200d2  endfinally
0x200d3  ldnull
0x200d4  ret
0x200d5  ldloc.3
0x200d6  ret
```
