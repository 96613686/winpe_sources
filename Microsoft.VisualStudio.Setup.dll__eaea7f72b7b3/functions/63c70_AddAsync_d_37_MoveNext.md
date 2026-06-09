# <AddAsync>d__37::MoveNext

- ea: `0x63c70`
- end: `0x6446a`
- name: `<AddAsync>d__37::MoveNext`
- size: `2042`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x3ef0`
- `0x4670`
- `0x4930`
- `0x4e90`
- `0x5090`
- `0x5130`
- `0x52c0`
- `0x5460`
- `0x54d0`
- `0xe2e0`
- `0xe2f0`
- `0xe380`
- `0x11430`
- `0x199a0`
- `0x27980`
- `0x55230`
- `0x63310`
- `0x63760`
- `0x63c70`

## string_xrefs

- `0x63e4c`: `UnableToDownloadChannelManifest_Args1`
- `0x641c0`: `UnableToDownloadChannelManifest_Args1`
- `0x643d8`: `UnableToDownloadChannelManifest_Args1`
- `0x63f4d`: `Channel manifest cannot be downloaded for major version check.`
- `0x64311`: `The channel manifest is already in the cache.`

## pseudocode

```c

```

## disassembly

```asm
0x63c70  ldarg.0
0x63c71  ldfld    int32 <AddAsync>d__37::<>1__state
0x63c76  stloc.0
0x63c77  ldarg.0
0x63c78  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <AddAsync>d__37::<>4__this
0x63c7d  stloc.1
0x63c7e  ldloc.0
0x63c7f  ldc.i4.2
0x63c80  ble.un.s loc_63CE7
0x63c82  ldloc.1
0x63c83  ldarg.0
0x63c84  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63c89  ldarg.0
0x63c8a  ldfld    class [System]System.Uri <AddAsync>d__37::installChannelUri
0x63c8f  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::ValidateUris(class [System]System.Uri channelUri, class [System]System.Uri installChannelUri)
0x63c94  ldarg.0
0x63c95  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <AddAsync>d__37::cancellationToken
0x63c9a  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x63c9f  ldloc.1
0x63ca0  callvirt instance void Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x63ca5  ldarg.0
0x63ca6  ldloc.1
0x63ca7  call     instance class Microsoft.VisualStudio.Setup.IChannelDownloader Microsoft.VisualStudio.Setup.ChannelManagerBase::GetChannelDownloader()
0x63cac  stfld    class Microsoft.VisualStudio.Setup.IChannelDownloader <AddAsync>d__37::<channelDownloader>5__2
0x63cb1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x63cb6  dup
0x63cb7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x63cbc  ldstr    aChanneladdasyn// "ChannelAddAsync"
0x63cc1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63cc6  stloc.3
0x63cc7  ldarg.0
0x63cc8  ldloc.1
0x63cc9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ChannelManager::telemetry
0x63cce  dup
0x63ccf  brtrue.s loc_63CD5
0x63cd1  pop
0x63cd2  ldnull
0x63cd3  br.s     loc_63CE2
0x63cd5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CHANNELOPERATIONEVENT
0x63cda  ldloc.3
0x63cdb  ldc.i4.0
0x63cdc  ldc.i4.0
0x63cdd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x63ce2  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__37::<addAsyncOperation>5__3
0x63ce7  nop
0x63ce8  ldloc.0
0x63ce9  ldc.i4.2
0x63cea  pop
0x63ceb  pop
0x63cec  nop
0x63ced  ldloc.0
0x63cee  switch   loc_63D70, loc_63EAA, loc_640E4
0x63cff  ldarg.0
0x63d00  ldnull
0x63d01  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifest>5__4
0x63d06  ldarg.0
0x63d07  ldloc.1
0x63d08  ldarg.0
0x63d09  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63d0e  ldc.i4.1
0x63d0f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.ChannelManager::GetChannel(class [System]System.Uri channelUri, [opt] bool localChannelOnly)
0x63d14  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddAsync>d__37::<existingChannelItem>5__5
0x63d19  ldarg.0
0x63d1a  ldc.i4.0
0x63d1b  stfld    bool <AddAsync>d__37::<removeExistingCatalog>5__6
0x63d20  ldarg.0
0x63d21  ldarg.0
0x63d22  ldfld    class [System]System.Uri <AddAsync>d__37::installCatalogUri
0x63d27  ldnull
0x63d28  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x63d2d  brtrue.s loc_63D3D
0x63d2f  ldarg.0
0x63d30  ldfld    class [System]System.Uri <AddAsync>d__37::installChannelUri
0x63d35  ldnull
0x63d36  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x63d3b  br.s     loc_63D3E
0x63d3d  ldc.i4.1
0x63d3e  stfld    bool <AddAsync>d__37::<useInstallChannelUri>5__7
0x63d43  ldarg.0
0x63d44  ldarg.0
0x63d45  ldfld    bool <AddAsync>d__37::<useInstallChannelUri>5__7
0x63d4a  brtrue.s loc_63D54
0x63d4c  ldarg.0
0x63d4d  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63d52  br.s     loc_63D5A
0x63d54  ldarg.0
0x63d55  ldfld    class [System]System.Uri <AddAsync>d__37::installChannelUri
0x63d5a  stfld    class [System]System.Uri <AddAsync>d__37::<channelUriToUse>5__8
0x63d5f  ldarg.0
0x63d60  ldfld    class [System]System.Uri <AddAsync>d__37::<channelUriToUse>5__8
0x63d65  ldnull
0x63d66  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x63d6b  brfalse  loc_640CC
0x63d70  nop
0x63d71  ldloc.0
0x63d72  brfalse.s loc_63DD0
0x63d74  ldarg.0
0x63d75  ldfld    class Microsoft.VisualStudio.Setup.IChannelDownloader <AddAsync>d__37::<channelDownloader>5__2
0x63d7a  ldarg.0
0x63d7b  ldfld    class [System]System.Uri <AddAsync>d__37::<channelUriToUse>5__8
0x63d80  ldloc.1
0x63d81  call     instance string Microsoft.VisualStudio.Setup.ChannelManagerBase::get_TemporaryCacheDirectory()
0x63d86  ldarg.0
0x63d87  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddAsync>d__37::cancellationToken
0x63d8c  ldnull
0x63d8d  ldloca.s 7
0x63d8f  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x63d95  ldloc.s  7
0x63d97  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary> Microsoft.VisualStudio.Setup.IChannelDownloader::GetLatestChannelManifestAsync(class [System]System.Uri channelUri, string temporaryCacheDirectory, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation updateAsyncOperation, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> lastModifiedDate)
0x63d9c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary>::GetAwaiter()
0x63da1  stloc.s  6
0x63da3  ldloca.s 6
0x63da5  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::get_IsCompleted()
0x63daa  brtrue.s loc_63DED
0x63dac  ldarg.0
0x63dad  ldc.i4.0
0x63dae  dup
0x63daf  stloc.0
0x63db0  stfld    int32 <AddAsync>d__37::<>1__state
0x63db5  ldarg.0
0x63db6  ldloc.s  6
0x63db8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63dbd  ldarg.0
0x63dbe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <AddAsync>d__37::<>t__builder
0x63dc3  ldloca.s 6
0x63dc5  ldarg.0
0x63dc6  call     T0x2B0002B6
0x63dcb  leave    loc_64469
0x63dd0  ldarg.0
0x63dd1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63dd6  stloc.s  6
0x63dd8  ldarg.0
0x63dd9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63dde  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>
0x63de4  ldarg.0
0x63de5  ldc.i4.m1
0x63de6  dup
0x63de7  stloc.0
0x63de8  stfld    int32 <AddAsync>d__37::<>1__state
0x63ded  ldloca.s 6
0x63def  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::GetResult()
0x63df4  stloc.s  5
0x63df6  ldarg.0
0x63df7  ldloca.s 5
0x63df9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest ManifestDownloadSummary::get_Manifest()
0x63dfe  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifest>5__4
0x63e03  ldloc.1
0x63e04  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x63e09  ldarg.0
0x63e0a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifest>5__4
0x63e0f  ldarg.0
0x63e10  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63e15  ldc.i4.3
0x63e16  callvirt instance void ChannelStatusTracker::SetStatus(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channel, class [System]System.Uri channelUri, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelStatus status)
0x63e1b  leave.s  loc_63E66
0x63e1d  isinst   [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException
0x63e22  dup
0x63e23  brtrue.s loc_63E29
0x63e25  pop
0x63e26  ldc.i4.0
0x63e27  br.s     loc_63E38
0x63e29  stloc.s  8
0x63e2b  ldloc.1
0x63e2c  ldloc.s  8
0x63e2e  ldloca.s 9
0x63e30  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsDownloadFailureExceptionInvalidSignatureException(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException ex, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException& invalidSignatureException)
0x63e35  ldc.i4.0
0x63e36  cgt.un
0x63e38  endfilter
0x63e3a  pop
0x63e3b  ldloc.1
0x63e3c  ldloc.s  8
0x63e3e  ldloc.s  9
0x63e40  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::HandleDownloadFailureException(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException ex, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException invalidSignatureException)
0x63e45  leave.s  loc_63E66
0x63e47  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x63e4c  ldstr    aUnabletodownlo// "UnableToDownloadChannelManifest_Args1"
0x63e51  ldc.i4.1
0x63e52  newarr   [mscorlib]System.Object
0x63e57  dup
0x63e58  ldc.i4.0
0x63e59  ldarg.0
0x63e5a  ldfld    class [System]System.Uri <AddAsync>d__37::<channelUriToUse>5__8
0x63e5f  stelem.ref
0x63e60  newobj   instance void Microsoft.VisualStudio.Setup.ChannelManifestDownloadException::.ctor(class [mscorlib]System.Exception innerException, class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x63e65  throw
0x63e66  ldarg.0
0x63e67  ldfld    bool <AddAsync>d__37::<useInstallChannelUri>5__7
0x63e6c  brfalse  loc_63FB1
0x63e71  ldarg.0
0x63e72  ldarg.0
0x63e73  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifest>5__4
0x63e78  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x63e7d  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x63e82  stfld    int32 <AddAsync>d__37::<actualMajorVersion>5__10
0x63e87  ldarg.0
0x63e88  ldarg.0
0x63e89  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddAsync>d__37::<existingChannelItem>5__5
0x63e8e  dup
0x63e8f  brtrue.s loc_63E95
0x63e91  pop
0x63e92  ldnull
0x63e93  br.s     loc_63E9A
0x63e95  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x63e9a  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifestToCompare>5__11
0x63e9f  ldarg.0
0x63ea0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifestToCompare>5__11
0x63ea5  brtrue   loc_63F5E
0x63eaa  nop
0x63eab  ldloc.0
0x63eac  ldc.i4.1
0x63ead  beq.s    loc_63F0B
0x63eaf  ldarg.0
0x63eb0  ldfld    class Microsoft.VisualStudio.Setup.IChannelDownloader <AddAsync>d__37::<channelDownloader>5__2
0x63eb5  ldarg.0
0x63eb6  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63ebb  ldloc.1
0x63ebc  call     instance string Microsoft.VisualStudio.Setup.ChannelManagerBase::get_TemporaryCacheDirectory()
0x63ec1  ldarg.0
0x63ec2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddAsync>d__37::cancellationToken
0x63ec7  ldnull
0x63ec8  ldloca.s 7
0x63eca  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x63ed0  ldloc.s  7
0x63ed2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary> Microsoft.VisualStudio.Setup.IChannelDownloader::GetLatestChannelManifestAsync(class [System]System.Uri channelUri, string temporaryCacheDirectory, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation updateAsyncOperation, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> lastModifiedDate)
0x63ed7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary>::GetAwaiter()
0x63edc  stloc.s  6
0x63ede  ldloca.s 6
0x63ee0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::get_IsCompleted()
0x63ee5  brtrue.s loc_63F28
0x63ee7  ldarg.0
0x63ee8  ldc.i4.1
0x63ee9  dup
0x63eea  stloc.0
0x63eeb  stfld    int32 <AddAsync>d__37::<>1__state
0x63ef0  ldarg.0
0x63ef1  ldloc.s  6
0x63ef3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63ef8  ldarg.0
0x63ef9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <AddAsync>d__37::<>t__builder
0x63efe  ldloca.s 6
0x63f00  ldarg.0
0x63f01  call     T0x2B0002B6
0x63f06  leave    loc_64469
0x63f0b  ldarg.0
0x63f0c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63f11  stloc.s  6
0x63f13  ldarg.0
0x63f14  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <AddAsync>d__37::<>u__1
0x63f19  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>
0x63f1f  ldarg.0
0x63f20  ldc.i4.m1
0x63f21  dup
0x63f22  stloc.0
0x63f23  stfld    int32 <AddAsync>d__37::<>1__state
0x63f28  ldloca.s 6
0x63f2a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::GetResult()
0x63f2f  stloc.s  0xA
0x63f31  ldarg.0
0x63f32  ldloca.s 0xA
0x63f34  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest ManifestDownloadSummary::get_Manifest()
0x63f39  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifestToCompare>5__11
0x63f3e  leave.s  loc_63F5E
0x63f40  pop
0x63f41  ldloc.1
0x63f42  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x63f47  dup
0x63f48  brtrue.s loc_63F4D
0x63f4a  pop
0x63f4b  br.s     loc_63F5C
0x63f4d  ldstr    aChannelManifes_2// "Channel manifest cannot be downloaded f"...
0x63f52  call     T0x2B000003
0x63f57  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x63f5c  leave.s  loc_63F5E
0x63f5e  ldarg.0
0x63f5f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifestToCompare>5__11
0x63f64  brfalse.s loc_63FAA
0x63f66  ldarg.0
0x63f67  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <AddAsync>d__37::<channelManifestToCompare>5__11
0x63f6c  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x63f71  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x63f76  stloc.s  0xB
0x63f78  ldarg.0
0x63f79  ldfld    int32 <AddAsync>d__37::<actualMajorVersion>5__10
0x63f7e  ldloc.s  0xB
0x63f80  beq.s    loc_63FAA
0x63f82  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x63f87  ldstr    aChannelmajorve// "ChannelMajorVersionMismatch"
0x63f8c  ldc.i4.2
0x63f8d  newarr   [mscorlib]System.Object
0x63f92  dup
0x63f93  ldc.i4.0
0x63f94  ldarg.0
0x63f95  ldfld    class [System]System.Uri <AddAsync>d__37::installChannelUri
0x63f9a  stelem.ref
0x63f9b  dup
0x63f9c  ldc.i4.1
0x63f9d  ldarg.0
0x63f9e  ldfld    class [System]System.Uri <AddAsync>d__37::channelUri
0x63fa3  stelem.ref
  ... truncated ...
```
