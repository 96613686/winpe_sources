# <RunImplAsync>d__15::MoveNext

- ea: `0x3c10`
- end: `0x408b`
- name: `<RunImplAsync>d__15::MoveNext`
- size: `1147`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: ``

## callees

- `0xdf0`
- `0x1070`
- `0x1850`
- `0x18d0`
- `0x18f0`
- `0x1900`
- `0x1910`
- `0x1a60`
- `0x1ae0`
- `0x1b10`
- `0x1b70`
- `0x1c30`
- `0x1c70`
- `0x1cd0`
- `0x25a0`
- `0x25c0`
- `0x25d0`
- `0x2640`
- `0x2660`
- `0x2680`
- `0x2950`
- `0x3c10`

## string_xrefs

- `0x3f4f`: `AnotherProcessAlreadyRunning - Another background process is already running`

## pseudocode

```c

```

## disassembly

```asm
0x3c10  ldarg.0
0x3c11  ldfld    int32 <RunImplAsync>d__15::<>1__state
0x3c16  stloc.0
0x3c17  ldarg.0
0x3c18  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloader <RunImplAsync>d__15::<>4__this
0x3c1d  stloc.1
0x3c1e  ldloc.0
0x3c1f  ldc.i4.2
0x3c20  ble.un.s loc_3C29
0x3c22  ldarg.0
0x3c23  ldc.i4.2
0x3c24  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__15::<result>5__2
0x3c29  nop
0x3c2a  ldloc.0
0x3c2b  switch   loc_3C7C, loc_3CE0, loc_3DE1
0x3c3c  ldloc.1
0x3c3d  ldarg.0
0x3c3e  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__15::cancellationToken
0x3c43  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3c48  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x3c4d  stloc.s  4
0x3c4f  ldloca.s 4
0x3c51  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x3c56  brtrue.s loc_3C99
0x3c58  ldarg.0
0x3c59  ldc.i4.0
0x3c5a  dup
0x3c5b  stloc.0
0x3c5c  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3c61  ldarg.0
0x3c62  ldloc.s  4
0x3c64  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3c69  ldarg.0
0x3c6a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__15::<>t__builder
0x3c6f  ldloca.s 4
0x3c71  ldarg.0
0x3c72  call     T0x2B000047
0x3c77  leave    loc_408A
0x3c7c  ldarg.0
0x3c7d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3c82  stloc.s  4
0x3c84  ldarg.0
0x3c85  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3c8a  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x3c90  ldarg.0
0x3c91  ldc.i4.m1
0x3c92  dup
0x3c93  stloc.0
0x3c94  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3c99  ldloca.s 4
0x3c9b  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x3ca0  ldloc.1
0x3ca1  ldarg.0
0x3ca2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__15::cancellationToken
0x3ca7  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CleanupLogsAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3cac  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x3cb1  stloc.s  4
0x3cb3  ldloca.s 4
0x3cb5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x3cba  brtrue.s loc_3CFD
0x3cbc  ldarg.0
0x3cbd  ldc.i4.1
0x3cbe  dup
0x3cbf  stloc.0
0x3cc0  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3cc5  ldarg.0
0x3cc6  ldloc.s  4
0x3cc8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3ccd  ldarg.0
0x3cce  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__15::<>t__builder
0x3cd3  ldloca.s 4
0x3cd5  ldarg.0
0x3cd6  call     T0x2B000047
0x3cdb  leave    loc_408A
0x3ce0  ldarg.0
0x3ce1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3ce6  stloc.s  4
0x3ce8  ldarg.0
0x3ce9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__15::<>u__1
0x3cee  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x3cf4  ldarg.0
0x3cf5  ldc.i4.m1
0x3cf6  dup
0x3cf7  stloc.0
0x3cf8  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3cfd  ldloca.s 4
0x3cff  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x3d04  ldloc.1
0x3d05  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FeatureEnabled()
0x3d0a  brtrue.s loc_3D2E
0x3d0c  ldloc.1
0x3d0d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x3d12  dup
0x3d13  brtrue.s loc_3D18
0x3d15  pop
0x3d16  br.s     loc_3D27
0x3d18  ldstr    aBackgroundDown_0// "Background download feature is disabled"...
0x3d1d  call     T0x2B00000A
0x3d22  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3d27  ldc.i4.0
0x3d28  stloc.2
0x3d29  leave    loc_4076
0x3d2e  ldloc.1
0x3d2f  ldfld    class Microsoft.VisualStudio.Setup.IWMIValidator Microsoft.VisualStudio.Setup.BackgroundDownloader::wmiValidator
0x3d34  callvirt instance valuetype Microsoft.VisualStudio.Setup.WMIValidatorResult Microsoft.VisualStudio.Setup.IWMIValidator::GetWMIValidatorResult()
0x3d39  stloc.3
0x3d3a  ldarg.0
0x3d3b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3d40  dup
0x3d41  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADACTIVITYID
0x3d46  ldloc.1
0x3d47  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x3d4c  callvirt instance string Microsoft.VisualStudio.Setup.CommandLine::get_ActivityId()
0x3d51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3d56  dup
0x3d57  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISCHILD
0x3d5c  ldloc.1
0x3d5d  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x3d62  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsChildProcess()
0x3d67  box      [mscorlib]System.Boolean
0x3d6c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3d71  dup
0x3d72  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADNOCANCEL
0x3d77  ldloc.1
0x3d78  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x3d7d  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_CanCancel()
0x3d82  ldc.i4.0
0x3d83  ceq
0x3d85  box      [mscorlib]System.Boolean
0x3d8a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3d8f  dup
0x3d90  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::HASFUNCTIONALWMIPROVIDERPROPERTY
0x3d95  ldloc.3
0x3d96  box      Microsoft.VisualStudio.Setup.WMIValidatorResult
0x3d9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3da0  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__15::<telemetryProperties>5__3
0x3da5  ldloc.1
0x3da6  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x3dab  dup
0x3dac  brtrue.s loc_3DB1
0x3dae  pop
0x3daf  br.s     loc_3DBC
0x3db1  ldarg.0
0x3db2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__15::<telemetryProperties>5__3
0x3db7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::SetSharedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x3dbc  ldarg.0
0x3dbd  ldloc.1
0x3dbe  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x3dc3  dup
0x3dc4  brtrue.s loc_3DCA
0x3dc6  pop
0x3dc7  ldnull
0x3dc8  br.s     loc_3DDC
0x3dca  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEVENT
0x3dcf  ldarg.0
0x3dd0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__15::<telemetryProperties>5__3
0x3dd5  ldc.i4.0
0x3dd6  ldc.i4.0
0x3dd7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x3ddc  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__15::<telemetryOperation>5__4
0x3de1  nop
0x3de2  ldloc.0
0x3de3  ldc.i4.2
0x3de4  beq.s    loc_3DFC
0x3de6  ldarg.0
0x3de7  ldloc.1
0x3de8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x3ded  ldstr    aBackgroundDown_1// "Background Download"
0x3df2  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0x3df7  stfld    class Microsoft.VisualStudio.Setup.OperationLogger <RunImplAsync>d__15::<>7__wrap4
0x3dfc  nop
0x3dfd  ldloc.0
0x3dfe  ldc.i4.2
0x3dff  pop
0x3e00  pop
0x3e01  nop
0x3e02  ldloc.0
0x3e03  ldc.i4.2
0x3e04  beq.s    loc_3E75
0x3e06  ldloc.1
0x3e07  ldfld    class Microsoft.VisualStudio.Setup.IWork Microsoft.VisualStudio.Setup.BackgroundDownloader::work
0x3e0c  ldloc.1
0x3e0d  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x3e12  callvirt instance void Microsoft.VisualStudio.Setup.IWork::GrabSingletonLock(class [mscorlib]System.IServiceProvider services)
0x3e17  ldloc.1
0x3e18  ldfld    class Microsoft.VisualStudio.Setup.IWork Microsoft.VisualStudio.Setup.BackgroundDownloader::work
0x3e1d  ldloc.1
0x3e1e  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x3e23  ldarg.0
0x3e24  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__15::<telemetryOperation>5__4
0x3e29  callvirt instance void Microsoft.VisualStudio.Setup.IWork::RunPrecheck(class [mscorlib]System.IServiceProvider services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation)
0x3e2e  ldloc.1
0x3e2f  ldloc.1
0x3e30  ldfld    class Microsoft.VisualStudio.Setup.IWork Microsoft.VisualStudio.Setup.BackgroundDownloader::work
0x3e35  ldnull
0x3e36  ldarg.0
0x3e37  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__15::cancellationToken
0x3e3c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CheckForUpdatesAsync(class Microsoft.VisualStudio.Setup.IWork primaryChild, string instanceId, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3e41  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::GetAwaiter()
0x3e46  stloc.s  7
0x3e48  ldloca.s 7
0x3e4a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::get_IsCompleted()
0x3e4f  brtrue.s loc_3E92
0x3e51  ldarg.0
0x3e52  ldc.i4.2
0x3e53  dup
0x3e54  stloc.0
0x3e55  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3e5a  ldarg.0
0x3e5b  ldloc.s  7
0x3e5d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__15::<>u__2
0x3e62  ldarg.0
0x3e63  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__15::<>t__builder
0x3e68  ldloca.s 7
0x3e6a  ldarg.0
0x3e6b  call     T0x2B000048
0x3e70  leave    loc_408A
0x3e75  ldarg.0
0x3e76  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__15::<>u__2
0x3e7b  stloc.s  7
0x3e7d  ldarg.0
0x3e7e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__15::<>u__2
0x3e83  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>
0x3e89  ldarg.0
0x3e8a  ldc.i4.m1
0x3e8b  dup
0x3e8c  stloc.0
0x3e8d  stfld    int32 <RunImplAsync>d__15::<>1__state
0x3e92  ldloca.s 7
0x3e94  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::GetResult()
0x3e99  stloc.s  5
0x3e9b  ldarg.0
0x3e9c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__15::<telemetryProperties>5__3
0x3ea1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADHASUPDATE
0x3ea6  ldloc.s  5
0x3ea8  callvirt instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EngineUpdateRequired()
0x3ead  box      [mscorlib]System.Boolean
0x3eb2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3eb7  ldloc.s  5
0x3eb9  callvirt instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EngineUpdateRequired()
0x3ebe  brtrue.s loc_3ECE
0x3ec0  ldloc.1
0x3ec1  ldarg.0
0x3ec2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__15::cancellationToken
0x3ec7  callvirt instance int32 Microsoft.VisualStudio.Setup.BackgroundDownloader::DoBackgroundDownloads(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3ecc  br.s     loc_3EE8
0x3ece  ldloc.1
0x3ecf  ldloc.s  5
0x3ed1  callvirt instance string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcUrl()
0x3ed6  ldloc.s  5
0x3ed8  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcVersion()
0x3edd  ldarg.0
0x3ede  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__15::cancellationToken
0x3ee3  callvirt instance int32 Microsoft.VisualStudio.Setup.BackgroundDownloader::LaunchChildAndWait(string engineUrl, class [mscorlib]System.Version opcVersion, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3ee8  stloc.s  6
0x3eea  ldloc.s  6
0x3eec  brtrue.s loc_3EF7
0x3eee  ldarg.0
0x3eef  ldc.i4.0
0x3ef0  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__15::<result>5__2
0x3ef5  br.s     loc_3F10
0x3ef7  ldloc.s  6
0x3ef9  ldc.i4   0x8013153B
0x3efe  bne.un.s loc_3F09
0x3f00  ldarg.0
0x3f01  ldc.i4.2
0x3f02  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__15::<result>5__2
0x3f07  br.s     loc_3F10
0x3f09  ldarg.0
0x3f0a  ldc.i4.1
0x3f0b  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__15::<result>5__2
0x3f10  ldloc.s  6
0x3f12  stloc.2
0x3f13  leave    loc_4076
0x3f18  stloc.s  8
0x3f1a  ldloc.1
0x3f1b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x3f20  dup
0x3f21  brtrue.s loc_3F26
0x3f23  pop
0x3f24  br.s     loc_3F43
0x3f26  ldloc.s  8
0x3f28  ldstr    aFailedToStartB// "Failed to start background downloader: "
0x3f2d  ldloc.s  8
0x3f2f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3f34  call     string [mscorlib]System.String::Concat(string, string)
0x3f39  call     T0x2B00000A
0x3f3e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x3f43  ldarg.0
0x3f44  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__15::<telemetryOperation>5__4
0x3f49  dup
0x3f4a  brtrue.s loc_3F4F
0x3f4c  pop
0x3f4d  br.s     loc_3F59
0x3f4f  ldstr    aAnotherprocess// "AnotherProcessAlreadyRunning - Another "...
0x3f54  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x3f59  ldarg.0
0x3f5a  ldc.i4.2
0x3f5b  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__15::<result>5__2
0x3f60  rethrow
  ... truncated ...
```
