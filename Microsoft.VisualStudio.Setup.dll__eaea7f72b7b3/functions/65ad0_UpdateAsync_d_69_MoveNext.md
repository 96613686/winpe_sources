# <UpdateAsync>d__69::MoveNext

- ea: `0x65ad0`
- end: `0x65d62`
- name: `<UpdateAsync>d__69::MoveNext`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x4930`
- `0x4be0`
- `0x4c50`
- `0x4e70`
- `0x5260`
- `0x52c0`
- `0x116a0`
- `0x63730`
- `0x65ad0`

## string_xrefs

- `0x65b05`: `channelManifestPair`
- `0x65b3c`: `ChannelUpdateAsync`

## pseudocode

```c

```

## disassembly

```asm
0x65ad0  ldarg.0
0x65ad1  ldfld    int32 <UpdateAsync>d__69::<>1__state
0x65ad6  stloc.0
0x65ad7  ldarg.0
0x65ad8  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <UpdateAsync>d__69::<>4__this
0x65add  stloc.1
0x65ade  ldloc.0
0x65adf  ldc.i4.1
0x65ae0  ble.un   loc_65B67
0x65ae5  ldloc.1
0x65ae6  call     instance bool Microsoft.VisualStudio.Setup.ChannelManagerBase::get_UpdateDisabled()
0x65aeb  brfalse.s loc_65AF4
0x65aed  ldnull
0x65aee  stloc.2
0x65aef  leave    loc_65D4D
0x65af4  ldarg.0
0x65af5  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <UpdateAsync>d__69::cancellationToken
0x65afa  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x65aff  ldarg.0
0x65b00  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65b05  ldstr    aChannelmanifes// "channelManifestPair"
0x65b0a  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x65b0f  ldloc.1
0x65b10  ldarg.0
0x65b11  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65b16  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x65b1b  ldarg.0
0x65b1c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65b21  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x65b26  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::ValidateUris(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest)
0x65b2b  ldloc.1
0x65b2c  callvirt instance void Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x65b31  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x65b36  dup
0x65b37  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x65b3c  ldstr    aChannelupdatea_0// "ChannelUpdateAsync"
0x65b41  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65b46  stloc.3
0x65b47  ldarg.0
0x65b48  ldloc.1
0x65b49  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ChannelManager::telemetry
0x65b4e  dup
0x65b4f  brtrue.s loc_65B55
0x65b51  pop
0x65b52  ldnull
0x65b53  br.s     loc_65B62
0x65b55  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CHANNELOPERATIONEVENT
0x65b5a  ldloc.3
0x65b5b  ldc.i4.0
0x65b5c  ldc.i4.0
0x65b5d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x65b62  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateAsync>d__69::<updateAsyncOperation>5__2
0x65b67  nop
0x65b68  ldloc.0
0x65b69  brfalse.s loc_65BCA
0x65b6b  ldloc.0
0x65b6c  ldc.i4.1
0x65b6d  beq      loc_65C94
0x65b72  ldloc.1
0x65b73  ldarg.0
0x65b74  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65b79  ldarg.0
0x65b7a  ldfld    bool <UpdateAsync>d__69::throwOnUpdateRequired
0x65b7f  ldarg.0
0x65b80  ldfld    bool <UpdateAsync>d__69::downloadOfflineInstaller
0x65b85  ldarg.0
0x65b86  ldfld    bool <UpdateAsync>d__69::alwaysCacheManifest
0x65b8b  ldarg.0
0x65b8c  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UpdateAsync>d__69::cancellationToken
0x65b91  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> Microsoft.VisualStudio.Setup.ChannelManager::UpdateChannelManifestAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, bool throwOnUpdateRequired, bool downloadOfflineInstaller, bool alwaysCacheManifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x65b96  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetAwaiter()
0x65b9b  stloc.s  5
0x65b9d  ldloca.s 5
0x65b9f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::get_IsCompleted()
0x65ba4  brtrue.s loc_65BE7
0x65ba6  ldarg.0
0x65ba7  ldc.i4.0
0x65ba8  dup
0x65ba9  stloc.0
0x65baa  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65baf  ldarg.0
0x65bb0  ldloc.s  5
0x65bb2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>u__1
0x65bb7  ldarg.0
0x65bb8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>t__builder
0x65bbd  ldloca.s 5
0x65bbf  ldarg.0
0x65bc0  call     T0x2B0002C9
0x65bc5  leave    loc_65D61
0x65bca  ldarg.0
0x65bcb  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>u__1
0x65bd0  stloc.s  5
0x65bd2  ldarg.0
0x65bd3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>u__1
0x65bd8  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>
0x65bde  ldarg.0
0x65bdf  ldc.i4.m1
0x65be0  dup
0x65be1  stloc.0
0x65be2  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65be7  ldloca.s 5
0x65be9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetResult()
0x65bee  stloc.s  4
0x65bf0  ldarg.0
0x65bf1  ldloc.s  4
0x65bf3  stfld    class Microsoft.VisualStudio.Setup.IChannelUpdateInformation <UpdateAsync>d__69::<updateInfo>5__3
0x65bf8  ldarg.0
0x65bf9  ldfld    class Microsoft.VisualStudio.Setup.IChannelUpdateInformation <UpdateAsync>d__69::<updateInfo>5__3
0x65bfe  brfalse.s loc_65C23
0x65c00  ldarg.0
0x65c01  ldarg.0
0x65c02  ldfld    class Microsoft.VisualStudio.Setup.IChannelUpdateInformation <UpdateAsync>d__69::<updateInfo>5__3
0x65c07  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.IChannelUpdateInformation::get_ChannelManifest()
0x65c0c  ldarg.0
0x65c0d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65c12  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x65c17  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest)
0x65c1c  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::<newChannelManifestPair>5__4
0x65c21  br.s     loc_65C4E
0x65c23  ldarg.0
0x65c24  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65c29  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x65c2e  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x65c33  stloc.s  6
0x65c35  ldarg.0
0x65c36  ldloc.1
0x65c37  ldloc.s  6
0x65c39  ldc.i4.0
0x65c3a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.ChannelManager::GetChannel(class [System]System.Uri channelUri, [opt] bool localChannelOnly)
0x65c3f  dup
0x65c40  brtrue.s loc_65C49
0x65c42  pop
0x65c43  ldarg.0
0x65c44  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::channelManifestPair
0x65c49  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::<newChannelManifestPair>5__4
0x65c4e  ldloc.1
0x65c4f  ldarg.0
0x65c50  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::<newChannelManifestPair>5__4
0x65c55  ldarg.0
0x65c56  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UpdateAsync>d__69::cancellationToken
0x65c5b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.ChannelManager::AddCatalogForChannelAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x65c60  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x65c65  stloc.s  7
0x65c67  ldloca.s 7
0x65c69  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x65c6e  brtrue.s loc_65CB1
0x65c70  ldarg.0
0x65c71  ldc.i4.1
0x65c72  dup
0x65c73  stloc.0
0x65c74  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65c79  ldarg.0
0x65c7a  ldloc.s  7
0x65c7c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <UpdateAsync>d__69::<>u__2
0x65c81  ldarg.0
0x65c82  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>t__builder
0x65c87  ldloca.s 7
0x65c89  ldarg.0
0x65c8a  call     T0x2B0002CA
0x65c8f  leave    loc_65D61
0x65c94  ldarg.0
0x65c95  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <UpdateAsync>d__69::<>u__2
0x65c9a  stloc.s  7
0x65c9c  ldarg.0
0x65c9d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <UpdateAsync>d__69::<>u__2
0x65ca2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x65ca8  ldarg.0
0x65ca9  ldc.i4.m1
0x65caa  dup
0x65cab  stloc.0
0x65cac  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65cb1  ldloca.s 7
0x65cb3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x65cb8  brtrue.s loc_65D01
0x65cba  ldloc.1
0x65cbb  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x65cc0  ldarg.0
0x65cc1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::<newChannelManifestPair>5__4
0x65cc6  ldc.i4.4
0x65cc7  callvirt instance void ChannelStatusTracker::SetStatus(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelPair, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelStatus status)
0x65ccc  ldarg.0
0x65ccd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateAsync>d__69::<updateAsyncOperation>5__2
0x65cd2  dup
0x65cd3  brtrue.s loc_65CD8
0x65cd5  pop
0x65cd6  br.s     loc_65CE2
0x65cd8  ldstr    aChannelManager_1// "Channel Manager Failure. Catalog downlo"...
0x65cdd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x65ce2  ldloc.1
0x65ce3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x65ce8  dup
0x65ce9  brtrue.s loc_65CEE
0x65ceb  pop
0x65cec  br.s     loc_65CFD
0x65cee  ldstr    aCatalogDownloa// "Catalog download failed."
0x65cf3  call     T0x2B000003
0x65cf8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x65cfd  ldnull
0x65cfe  stloc.2
0x65cff  leave.s  loc_65D4D
0x65d01  ldloc.1
0x65d02  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x65d07  ldarg.0
0x65d08  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateAsync>d__69::<newChannelManifestPair>5__4
0x65d0d  ldc.i4.3
0x65d0e  callvirt instance void ChannelStatusTracker::SetStatus(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelPair, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelStatus status)
0x65d13  ldarg.0
0x65d14  ldfld    class Microsoft.VisualStudio.Setup.IChannelUpdateInformation <UpdateAsync>d__69::<updateInfo>5__3
0x65d19  stloc.2
0x65d1a  leave.s  loc_65D4D
0x65d1c  ldloc.0
0x65d1d  ldc.i4.0
0x65d1e  bge.s    loc_65D33
0x65d20  ldarg.0
0x65d21  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateAsync>d__69::<updateAsyncOperation>5__2
0x65d26  brfalse.s loc_65D33
0x65d28  ldarg.0
0x65d29  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateAsync>d__69::<updateAsyncOperation>5__2
0x65d2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65d33  endfinally
0x65d34  stloc.s  8
0x65d36  ldarg.0
0x65d37  ldc.i4.s 0xFE
0x65d39  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65d3e  ldarg.0
0x65d3f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>t__builder
0x65d44  ldloc.s  8
0x65d46  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::SetException(class [mscorlib]System.Exception)
0x65d4b  leave.s  loc_65D61
0x65d4d  ldarg.0
0x65d4e  ldc.i4.s 0xFE
0x65d50  stfld    int32 <UpdateAsync>d__69::<>1__state
0x65d55  ldarg.0
0x65d56  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateAsync>d__69::<>t__builder
0x65d5b  ldloc.2
0x65d5c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::SetResult(var<u1>)
0x65d61  ret
```
