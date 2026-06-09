# <RunServiceAsync>d__14::MoveNext

- ea: `0x1d30`
- end: `0x20e0`
- name: `<RunServiceAsync>d__14::MoveNext`
- size: `944`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0xd60`
- `0xf90`
- `0xfa0`
- `0xfc0`
- `0x1aa0`
- `0x1ac0`
- `0x1d30`

## string_xrefs

- `0x1f2f`: `RPC service created. Waiting for disconnect.`
- `0x205f`: `Failed to create new pipe, exiting listening loop.`
- `0x2079`: `Failed to create new pipe, exiting listening loop.`

## pseudocode

```c

```

## disassembly

```asm
0x1d30  ldarg.0
0x1d31  ldfld    int32 <RunServiceAsync>d__14::<>1__state
0x1d36  stloc.0
0x1d37  ldarg.0
0x1d38  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager <RunServiceAsync>d__14::<>4__this
0x1d3d  stloc.1
0x1d3e  ldloc.0
0x1d3f  ldc.i4.1
0x1d40  bgt.un   loc_20A1
0x1d45  nop
0x1d46  ldloc.0
0x1d47  brfalse.s loc_1D69
0x1d49  ldloc.0
0x1d4a  ldc.i4.1
0x1d4b  beq      loc_1F24
0x1d50  ldarg.0
0x1d51  ldloc.1
0x1d52  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0x1d57  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerWaitingForConnectionEventName
0x1d5c  ldnull
0x1d5d  ldc.i4.0
0x1d5e  ldc.i4.0
0x1d5f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x1d64  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1d69  nop
0x1d6a  ldloc.0
0x1d6b  brfalse.s loc_1DBE
0x1d6d  ldloc.1
0x1d6e  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x1d73  ldloc.1
0x1d74  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.ElevationServiceManager::cancellationToken
0x1d79  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x1d7e  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.IPipe::WaitForConnectionAsync(valuetype [mscorlib]System.Threading.CancellationToken token)
0x1d83  ldc.i4.0
0x1d84  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x1d89  stloc.3
0x1d8a  ldloca.s 3
0x1d8c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x1d91  stloc.2
0x1d92  ldloca.s 2
0x1d94  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x1d99  brtrue.s loc_1DDA
0x1d9b  ldarg.0
0x1d9c  ldc.i4.0
0x1d9d  dup
0x1d9e  stloc.0
0x1d9f  stfld    int32 <RunServiceAsync>d__14::<>1__state
0x1da4  ldarg.0
0x1da5  ldloc.2
0x1da6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1dab  ldarg.0
0x1dac  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <RunServiceAsync>d__14::<>t__builder
0x1db1  ldloca.s 2
0x1db3  ldarg.0
0x1db4  call     T0x2B00001B
0x1db9  leave    loc_20DF
0x1dbe  ldarg.0
0x1dbf  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1dc4  stloc.2
0x1dc5  ldarg.0
0x1dc6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1dcb  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x1dd1  ldarg.0
0x1dd2  ldc.i4.m1
0x1dd3  dup
0x1dd4  stloc.0
0x1dd5  stfld    int32 <RunServiceAsync>d__14::<>1__state
0x1dda  ldloca.s 2
0x1ddc  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x1de1  ldloc.1
0x1de2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x1de7  ldstr    aClientConnecte// "Client connected."
0x1dec  call     T0x2B000003
0x1df1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1df6  ldarg.0
0x1df7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1dfc  ldstr    aClientConnecte// "Client connected."
0x1e01  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x1e06  leave.s  loc_1E20
0x1e08  ldloc.0
0x1e09  ldc.i4.0
0x1e0a  bge.s    loc_1E1F
0x1e0c  ldarg.0
0x1e0d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1e12  brfalse.s loc_1E1F
0x1e14  ldarg.0
0x1e15  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1e1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e1f  endfinally
0x1e20  ldarg.0
0x1e21  ldnull
0x1e22  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1e27  ldloc.1
0x1e28  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.ElevationServiceManager::cancellationToken
0x1e2d  callvirt instance bool [mscorlib]System.Threading.CancellationTokenSource::get_IsCancellationRequested()
0x1e32  brfalse.s loc_1E39
0x1e34  leave    loc_20CC
0x1e39  ldloc.1
0x1e3a  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x1e3f  ldarg.0
0x1e40  ldflda   unsigned int32 <RunServiceAsync>d__14::<clientPid>5__2
0x1e45  callvirt instance bool Microsoft.VisualStudio.Setup.IPipe::TryGetClientPipeId([out] unsigned int32& processId)
0x1e4a  brtrue.s loc_1E89
0x1e4c  ldloc.1
0x1e4d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0x1e52  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerGetClientPidFailure
0x1e57  ldstr    aFailedToGetPid// "Failed to get PID for connecting client"...
0x1e5c  ldnull
0x1e5d  ldnull
0x1e5e  ldnull
0x1e5f  ldc.i4.0
0x1e60  ldnull
0x1e61  ldc.i4.0
0x1e62  ldnull
0x1e63  ldc.i4.0
0x1e64  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x1e69  ldloc.1
0x1e6a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x1e6f  ldstr    aFailedToGetThe// "Failed to get the process ID of the con"...
0x1e74  call     T0x2B000003
0x1e79  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1e7e  ldstr    aFailedToGetCli// "Failed to get client process ID."
0x1e83  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e88  throw
0x1e89  ldloc.1
0x1e8a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.IRpcConnectionValidator Microsoft.VisualStudio.Setup.ElevationServiceManager::clientValidator
0x1e8f  ldarg.0
0x1e90  ldfld    unsigned int32 <RunServiceAsync>d__14::<clientPid>5__2
0x1e95  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.IRpcConnectionValidator::IsValidRpcConnection(int32)
0x1e9a  brtrue.s loc_1EF8
0x1e9c  ldloc.1
0x1e9d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0x1ea2  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerInvalidClientFailure
0x1ea7  ldstr    aClientProcessI// "Client process is invalid."
0x1eac  ldnull
0x1ead  ldnull
0x1eae  ldnull
0x1eaf  ldc.i4.0
0x1eb0  ldnull
0x1eb1  ldc.i4.0
0x1eb2  ldnull
0x1eb3  ldc.i4.0
0x1eb4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x1eb9  ldloc.1
0x1eba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x1ebf  ldstr    aClientProcess0// "Client process {0} is not supported. Re"...
0x1ec4  ldc.i4.1
0x1ec5  newarr   [mscorlib]System.Object
0x1eca  dup
0x1ecb  ldc.i4.0
0x1ecc  ldarg.0
0x1ecd  ldfld    unsigned int32 <RunServiceAsync>d__14::<clientPid>5__2
0x1ed2  box      [mscorlib]System.UInt32
0x1ed7  stelem.ref
0x1ed8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1edd  ldloc.1
0x1ede  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x1ee3  callvirt instance void Microsoft.VisualStudio.Setup.IPipe::Disconnect()
0x1ee8  ldloc.1
0x1ee9  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x1eee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ef3  br       loc_2003
0x1ef8  ldloc.1
0x1ef9  ldfld    class Microsoft.VisualStudio.Setup.Services.IStreamJsonRpcFactory Microsoft.VisualStudio.Setup.ElevationServiceManager::rpcFactory
0x1efe  ldloc.1
0x1eff  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x1f04  callvirt instance class Microsoft.VisualStudio.Setup.Services.IRpcService Microsoft.VisualStudio.Setup.Services.IStreamJsonRpcFactory::CreateRpcService(class Microsoft.VisualStudio.Setup.IPipe pipe)
0x1f09  stloc.s  4
0x1f0b  ldarg.0
0x1f0c  ldloc.1
0x1f0d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0x1f12  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerClientConnectionEventName
0x1f17  ldnull
0x1f18  ldc.i4.0
0x1f19  ldc.i4.0
0x1f1a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x1f1f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1f24  nop
0x1f25  ldloc.0
0x1f26  ldc.i4.1
0x1f27  beq.s    loc_1F8B
0x1f29  ldloc.1
0x1f2a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x1f2f  ldstr    aRpcServiceCrea// "RPC service created. Waiting for discon"...
0x1f34  call     T0x2B000003
0x1f39  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1f3e  ldloc.s  4
0x1f40  ldloc.1
0x1f41  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.ElevationServiceManager::cancellationToken
0x1f46  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x1f4b  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Services.IRpcService::WaitForDisconnectAsync(valuetype [mscorlib]System.Threading.CancellationToken token)
0x1f50  ldc.i4.0
0x1f51  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x1f56  stloc.3
0x1f57  ldloca.s 3
0x1f59  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x1f5e  stloc.2
0x1f5f  ldloca.s 2
0x1f61  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x1f66  brtrue.s loc_1FA7
0x1f68  ldarg.0
0x1f69  ldc.i4.1
0x1f6a  dup
0x1f6b  stloc.0
0x1f6c  stfld    int32 <RunServiceAsync>d__14::<>1__state
0x1f71  ldarg.0
0x1f72  ldloc.2
0x1f73  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1f78  ldarg.0
0x1f79  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <RunServiceAsync>d__14::<>t__builder
0x1f7e  ldloca.s 2
0x1f80  ldarg.0
0x1f81  call     T0x2B00001B
0x1f86  leave    loc_20DF
0x1f8b  ldarg.0
0x1f8c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1f91  stloc.2
0x1f92  ldarg.0
0x1f93  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <RunServiceAsync>d__14::<>u__1
0x1f98  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x1f9e  ldarg.0
0x1f9f  ldc.i4.m1
0x1fa0  dup
0x1fa1  stloc.0
0x1fa2  stfld    int32 <RunServiceAsync>d__14::<>1__state
0x1fa7  ldloca.s 2
0x1fa9  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x1fae  ldarg.0
0x1faf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1fb4  ldstr    aClientDisconne// "Client disconnected."
0x1fb9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x1fbe  ldloc.1
0x1fbf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x1fc4  ldstr    aClient0Disconn// "Client {0} disconnected."
0x1fc9  ldc.i4.1
0x1fca  newarr   [mscorlib]System.Object
0x1fcf  dup
0x1fd0  ldc.i4.0
0x1fd1  ldarg.0
0x1fd2  ldfld    unsigned int32 <RunServiceAsync>d__14::<clientPid>5__2
0x1fd7  box      [mscorlib]System.UInt32
0x1fdc  stelem.ref
0x1fdd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1fe2  leave.s  loc_1FFC
0x1fe4  ldloc.0
0x1fe5  ldc.i4.0
0x1fe6  bge.s    loc_1FFB
0x1fe8  ldarg.0
0x1fe9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1fee  brfalse.s loc_1FFB
0x1ff0  ldarg.0
0x1ff1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x1ff6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ffb  endfinally
0x1ffc  ldarg.0
0x1ffd  ldnull
0x1ffe  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunServiceAsync>d__14::<waitOperation>5__3
0x2003  leave.s  loc_202F
0x2005  pop
0x2006  leave    loc_20CC
0x200b  stloc.s  5
0x200d  ldloc.1
0x200e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x2013  ldstr    aFailedToConnec// "Failed to connect with client. {0}"
0x2018  ldc.i4.1
0x2019  newarr   [mscorlib]System.Object
0x201e  dup
0x201f  ldc.i4.0
0x2020  ldloc.s  5
0x2022  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2027  stelem.ref
0x2028  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x202d  leave.s  loc_202F
0x202f  nop
0x2030  ldloc.1
0x2031  ldfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x2036  dup
0x2037  brtrue.s loc_203C
0x2039  pop
0x203a  br.s     loc_2041
0x203c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2041  leave.s  loc_2046
0x2043  pop
0x2044  leave.s  loc_2046
0x2046  nop
0x2047  ldloc.1
0x2048  ldloc.1
0x2049  call     instance class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::CreatePipe()
0x204e  stfld    class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.ElevationServiceManager::pipe
0x2053  leave.s  loc_20A1
0x2055  stloc.s  6
0x2057  ldloc.1
0x2058  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0x205d  ldloc.s  6
0x205f  ldstr    aFailedToCreate_3// "Failed to create new pipe, exiting list"...
0x2064  call     T0x2B000003
0x2069  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x206e  ldloc.1
0x206f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0x2074  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerPipeCreationFailure
  ... truncated ...
```
