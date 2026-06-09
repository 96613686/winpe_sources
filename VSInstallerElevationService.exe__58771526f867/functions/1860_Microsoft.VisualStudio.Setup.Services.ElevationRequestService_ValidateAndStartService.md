# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::ValidateAndStartService

- ea: `0x1860`
- end: `0x1a6b`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::ValidateAndStartService`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x16e0`

## callees

- `0x1730`
- `0x1840`
- `0x1860`

## string_xrefs

- `0x18d1`: `Failed to open '{0}' to validate signature.`
- `0x1967`: `Installer service signature validation failed. Result: {0}`
- `0x19e4`: `Failed to start installer service.`
- `0x19f4`: `Failed to start installer service.`
- `0x1a12`: `Successfully started installer service.`
- `0x1a22`: `Installer service started. PID: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1860  ldarg.0
0x1861  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.ElevationRequestService::fileSystem
0x1866  ldarg.0
0x1867  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x186c  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x1871  brtrue.s loc_18BC
0x1873  ldstr    a0DoesNotExist// "'{0}' does not exist."
0x1878  ldarg.0
0x1879  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x187e  call     string [mscorlib]System.String::Format(string, object)
0x1883  stloc.0
0x1884  ldarg.0
0x1885  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.ElevationRequestService::telemetry
0x188a  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestServiceValidateServiceFailure
0x188f  ldloc.0
0x1890  ldnull
0x1891  ldnull
0x1892  ldnull
0x1893  ldc.i4.0
0x1894  ldnull
0x1895  ldc.i4.0
0x1896  ldnull
0x1897  ldc.i4.0
0x1898  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x189d  ldarg.0
0x189e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x18a3  ldloc.0
0x18a4  call     T0x2B000003
0x18a9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x18ae  ldarg.1
0x18af  ldloc.0
0x18b0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x18b5  ldc.i4.0
0x18b6  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::.ctor(bool)
0x18bb  ret
0x18bc  ldarg.0
0x18bd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.ElevationRequestService::fileSystem
0x18c2  ldarg.0
0x18c3  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x18c8  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x18cd  stloc.1
0x18ce  ldloc.1
0x18cf  brtrue.s loc_1924
0x18d1  ldstr    aFailedToOpen0T// "Failed to open '{0}' to validate signat"...
0x18d6  ldarg.0
0x18d7  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x18dc  call     string [mscorlib]System.String::Format(string, object)
0x18e1  stloc.s  6
0x18e3  ldarg.0
0x18e4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.ElevationRequestService::telemetry
0x18e9  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestServiceValidateServiceFailure
0x18ee  ldloc.s  6
0x18f0  ldnull
0x18f1  ldnull
0x18f2  ldnull
0x18f3  ldc.i4.0
0x18f4  ldnull
0x18f5  ldc.i4.0
0x18f6  ldnull
0x18f7  ldc.i4.0
0x18f8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x18fd  ldarg.0
0x18fe  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x1903  ldloc.s  6
0x1905  call     T0x2B000003
0x190a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x190f  ldarg.1
0x1910  ldloc.s  6
0x1912  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x1917  ldc.i4.0
0x1918  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::.ctor(bool)
0x191d  stloc.s  7
0x191f  leave    loc_1A68
0x1924  ldarg.0
0x1925  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Services.ElevationRequestService::signatureVerifier
0x192a  ldloc.1
0x192b  ldarg.0
0x192c  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x1931  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::VerifyMicrosoftSignature(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager, class [mscorlib]System.IO.Stream, string)
0x1936  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x193b  stloc.2
0x193c  ldarg.0
0x193d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x1942  ldstr    a0SignatureResu// "'{0}' signature result: {1}"
0x1947  ldc.i4.2
0x1948  newarr   [mscorlib]System.Object
0x194d  dup
0x194e  ldc.i4.0
0x194f  ldarg.0
0x1950  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x1955  stelem.ref
0x1956  dup
0x1957  ldc.i4.1
0x1958  ldloc.2
0x1959  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x195e  stelem.ref
0x195f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1964  ldloc.2
0x1965  brfalse.s loc_19A8
0x1967  ldstr    aInstallerServi// "Installer service signature validation "...
0x196c  ldloc.2
0x196d  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x1972  call     string [mscorlib]System.String::Format(string, object)
0x1977  stloc.s  8
0x1979  ldarg.0
0x197a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.ElevationRequestService::telemetry
0x197f  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestServiceValidateServiceFailure
0x1984  ldloc.s  8
0x1986  ldnull
0x1987  ldnull
0x1988  ldnull
0x1989  ldc.i4.0
0x198a  ldnull
0x198b  ldc.i4.0
0x198c  ldnull
0x198d  ldc.i4.0
0x198e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x1993  ldarg.1
0x1994  ldloc.s  8
0x1996  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x199b  ldc.i4.0
0x199c  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::.ctor(bool)
0x19a1  stloc.s  7
0x19a3  leave    loc_1A68
0x19a8  call     string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::CreatePipeName()
0x19ad  stloc.3
0x19ae  ldarg.2
0x19af  ldloc.3
0x19b0  call     string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::GetCommandLineArgs(class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest request, string pipeName)
0x19b5  stloc.s  4
0x19b7  ldarg.0
0x19b8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.ElevationRequestService::processService
0x19bd  ldloca.s 5
0x19bf  ldarg.0
0x19c0  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x19c5  ldloc.s  4
0x19c7  callvirt instance string [mscorlib]System.Object::ToString()
0x19cc  ldc.i4.0
0x19cd  ldarg.0
0x19ce  ldfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x19d3  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x19d8  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::TryStartProcess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess&, string, string, bool, string)
0x19dd  brfalse.s loc_19E3
0x19df  ldloc.s  5
0x19e1  brtrue.s loc_1A0D
0x19e3  ldarg.1
0x19e4  ldstr    aFailedToStartI// "Failed to start installer service."
0x19e9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x19ee  ldarg.0
0x19ef  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x19f4  ldstr    aFailedToStartI// "Failed to start installer service."
0x19f9  call     T0x2B000003
0x19fe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1a03  ldc.i4.0
0x1a04  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::.ctor(bool)
0x1a09  stloc.s  7
0x1a0b  leave.s  loc_1A68
0x1a0d  ldloc.s  5
0x1a0f  stloc.s  9
0x1a11  ldarg.1
0x1a12  ldstr    aSuccessfullySt// "Successfully started installer service."
0x1a17  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x1a1c  ldarg.0
0x1a1d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x1a22  ldstr    aInstallerServi_0// "Installer service started. PID: {0}"
0x1a27  ldc.i4.1
0x1a28  newarr   [mscorlib]System.Object
0x1a2d  dup
0x1a2e  ldc.i4.0
0x1a2f  ldloc.s  5
0x1a31  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_Id()
0x1a36  box      [mscorlib]System.Int32
0x1a3b  stelem.ref
0x1a3c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1a41  ldc.i4.1
0x1a42  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::.ctor(bool)
0x1a47  dup
0x1a48  ldloc.3
0x1a49  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::set_PipeName(string)
0x1a4e  stloc.s  7
0x1a50  leave.s  loc_1A68
0x1a52  ldloc.s  9
0x1a54  brfalse.s loc_1A5D
0x1a56  ldloc.s  9
0x1a58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a5d  endfinally
0x1a5e  ldloc.1
0x1a5f  brfalse.s loc_1A67
0x1a61  ldloc.1
0x1a62  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a67  endfinally
0x1a68  ldloc.s  7
0x1a6a  ret
```
