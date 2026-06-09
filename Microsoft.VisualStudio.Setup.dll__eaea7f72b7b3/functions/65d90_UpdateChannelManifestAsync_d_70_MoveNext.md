# <UpdateChannelManifestAsync>d__70::MoveNext

- ea: `0x65d90`
- end: `0x6643f`
- name: `<UpdateChannelManifestAsync>d__70::MoveNext`
- size: `1711`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, installer_update`

## callees

- `0x3ef0`
- `0x4670`
- `0x4e70`
- `0x5090`
- `0x5130`
- `0x5180`
- `0x5260`
- `0x5280`
- `0x52c0`
- `0x5460`
- `0x54d0`
- `0x5670`
- `0x11430`
- `0x27980`
- `0x55230`
- `0x55290`
- `0x552a0`
- `0x59440`
- `0x59470`
- `0x63310`
- `0x63330`
- `0x63350`
- `0x63730`
- `0x65d90`

## string_xrefs

- `0x65dc5`: `channelManifestPair`
- `0x65e03`: `ChannelUpdateManifestAsync`
- `0x65faa`: `Could not update channel "`
- `0x66196`: `Did not pre-download offline bootstrapper. Will try again when update started.`
- `0x6628f`: `Channel Manager Failure. Unable to update channel manifest`
- `0x662a5`: `Unable to update channel manifest: "`
- `0x662e6`: `Updated channel manifest: "{0}" to version {1}.`
- `0x6634d`: `Channel manifest for {0} is already up to date.`

## pseudocode

```c

```

## disassembly

```asm
0x65d90  ldarg.0
0x65d91  ldfld    int32 <UpdateChannelManifestAsync>d__70::<>1__state
0x65d96  stloc.0
0x65d97  ldarg.0
0x65d98  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <UpdateChannelManifestAsync>d__70::<>4__this
0x65d9d  stloc.1
0x65d9e  ldloc.0
0x65d9f  ldc.i4.1
0x65da0  ble.un   loc_65E30
0x65da5  ldloc.1
0x65da6  call     instance bool Microsoft.VisualStudio.Setup.ChannelManagerBase::get_UpdateDisabled()
0x65dab  brfalse.s loc_65DB4
0x65dad  ldnull
0x65dae  stloc.2
0x65daf  leave    loc_6642A
0x65db4  ldarg.0
0x65db5  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <UpdateChannelManifestAsync>d__70::cancellationToken
0x65dba  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x65dbf  ldarg.0
0x65dc0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65dc5  ldstr    aChannelmanifes// "channelManifestPair"
0x65dca  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x65dcf  ldloc.1
0x65dd0  ldarg.0
0x65dd1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65dd6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x65ddb  ldarg.0
0x65ddc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65de1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x65de6  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::ValidateUris(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest)
0x65deb  ldloc.1
0x65dec  callvirt instance void Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x65df1  ldloc.1
0x65df2  call     instance class Microsoft.VisualStudio.Setup.IChannelDownloader Microsoft.VisualStudio.Setup.ChannelManagerBase::GetChannelDownloader()
0x65df7  stloc.3
0x65df8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x65dfd  dup
0x65dfe  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x65e03  ldstr    aChannelupdatem// "ChannelUpdateManifestAsync"
0x65e08  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65e0d  stloc.s  4
0x65e0f  ldarg.0
0x65e10  ldloc.1
0x65e11  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ChannelManager::telemetry
0x65e16  dup
0x65e17  brtrue.s loc_65E1D
0x65e19  pop
0x65e1a  ldnull
0x65e1b  br.s     loc_65E2B
0x65e1d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CHANNELOPERATIONEVENT
0x65e22  ldloc.s  4
0x65e24  ldc.i4.0
0x65e25  ldc.i4.0
0x65e26  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x65e2b  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x65e30  nop
0x65e31  ldloc.0
0x65e32  brfalse.s loc_65E5E
0x65e34  ldloc.0
0x65e35  ldc.i4.1
0x65e36  beq      loc_66160
0x65e3b  ldarg.0
0x65e3c  ldflda   valuetype ManifestDownloadSummary <UpdateChannelManifestAsync>d__70::<downloadSummary>5__3
0x65e41  initobj  ManifestDownloadSummary
0x65e47  ldarg.0
0x65e48  ldloc.1
0x65e49  ldfld    class Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.ChannelManager::channelRepository
0x65e4e  ldarg.0
0x65e4f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65e54  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> Microsoft.VisualStudio.Setup.Cache.IChannelRepository::GetLastUpdateDate(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair)
0x65e59  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> <UpdateChannelManifestAsync>d__70::<lastUpdateDate>5__4
0x65e5e  nop
0x65e5f  ldloc.0
0x65e60  brfalse.s loc_65ED9
0x65e62  ldc.i4.0
0x65e63  stloc.s  6
0x65e65  ldloc.1
0x65e66  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x65e6b  ldarg.0
0x65e6c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65e71  ldc.i4.2
0x65e72  callvirt instance void ChannelStatusTracker::SetStatus(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelPair, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelStatus status)
0x65e77  ldloc.3
0x65e78  ldarg.0
0x65e79  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65e7e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x65e83  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x65e88  ldloc.1
0x65e89  call     instance string Microsoft.VisualStudio.Setup.ChannelManagerBase::get_TemporaryCacheDirectory()
0x65e8e  ldarg.0
0x65e8f  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UpdateChannelManifestAsync>d__70::cancellationToken
0x65e94  ldarg.0
0x65e95  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x65e9a  ldarg.0
0x65e9b  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> <UpdateChannelManifestAsync>d__70::<lastUpdateDate>5__4
0x65ea0  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary> Microsoft.VisualStudio.Setup.IChannelDownloader::GetLatestChannelManifestAsync(class [System]System.Uri channelUri, string temporaryCacheDirectory, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation updateAsyncOperation, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> lastModifiedDate)
0x65ea5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype ManifestDownloadSummary>::GetAwaiter()
0x65eaa  stloc.s  8
0x65eac  ldloca.s 8
0x65eae  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::get_IsCompleted()
0x65eb3  brtrue.s loc_65EF6
0x65eb5  ldarg.0
0x65eb6  ldc.i4.0
0x65eb7  dup
0x65eb8  stloc.0
0x65eb9  stfld    int32 <UpdateChannelManifestAsync>d__70::<>1__state
0x65ebe  ldarg.0
0x65ebf  ldloc.s  8
0x65ec1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <UpdateChannelManifestAsync>d__70::<>u__1
0x65ec6  ldarg.0
0x65ec7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <UpdateChannelManifestAsync>d__70::<>t__builder
0x65ecc  ldloca.s 8
0x65ece  ldarg.0
0x65ecf  call     T0x2B0002CB
0x65ed4  leave    loc_6643E
0x65ed9  ldarg.0
0x65eda  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <UpdateChannelManifestAsync>d__70::<>u__1
0x65edf  stloc.s  8
0x65ee1  ldarg.0
0x65ee2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary> <UpdateChannelManifestAsync>d__70::<>u__1
0x65ee7  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>
0x65eed  ldarg.0
0x65eee  ldc.i4.m1
0x65eef  dup
0x65ef0  stloc.0
0x65ef1  stfld    int32 <UpdateChannelManifestAsync>d__70::<>1__state
0x65ef6  ldloca.s 8
0x65ef8  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype ManifestDownloadSummary>::GetResult()
0x65efd  stloc.s  7
0x65eff  ldarg.0
0x65f00  ldloc.s  7
0x65f02  stfld    valuetype ManifestDownloadSummary <UpdateChannelManifestAsync>d__70::<downloadSummary>5__3
0x65f07  ldc.i4.1
0x65f08  stloc.s  6
0x65f0a  ldarg.0
0x65f0b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x65f10  dup
0x65f11  brtrue.s loc_65F16
0x65f13  pop
0x65f14  br.s     loc_65F2C
0x65f16  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x65f1b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FINISHEDMANIFESTDOWNLOAD
0x65f20  ldloc.s  6
0x65f22  box      [mscorlib]System.Boolean
0x65f27  call     void Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> dictionary, string key, object value)
0x65f2c  ldarg.0
0x65f2d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x65f32  dup
0x65f33  brtrue.s loc_65F38
0x65f35  pop
0x65f36  br.s     loc_65F5A
0x65f38  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x65f3d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::WASMANIFESTMODIFIED
0x65f42  ldarg.0
0x65f43  ldflda   valuetype ManifestDownloadSummary <UpdateChannelManifestAsync>d__70::<downloadSummary>5__3
0x65f48  call     instance bool ManifestDownloadSummary::get_NotModified()
0x65f4d  ldc.i4.0
0x65f4e  ceq
0x65f50  box      [mscorlib]System.Boolean
0x65f55  call     void Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> dictionary, string key, object value)
0x65f5a  leave    loc_66009
0x65f5f  isinst   [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException
0x65f64  dup
0x65f65  brtrue.s loc_65F6B
0x65f67  pop
0x65f68  ldc.i4.0
0x65f69  br.s     loc_65F87
0x65f6b  stloc.s  9
0x65f6d  ldloc.1
0x65f6e  ldloc.s  9
0x65f70  ldloca.s 0xA
0x65f72  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsDownloadFailureExceptionInvalidSignatureException(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException ex, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException& invalidSignatureException)
0x65f77  brfalse.s loc_65F83
0x65f79  ldloc.1
0x65f7a  ldloc.s  0xA
0x65f7c  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsVerificationResultInvalidTestCertificate(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException ex)
0x65f81  br.s     loc_65F84
0x65f83  ldc.i4.0
0x65f84  ldc.i4.0
0x65f85  cgt.un
0x65f87  endfilter
0x65f89  pop
0x65f8a  ldloc.1
0x65f8b  ldloc.s  9
0x65f8d  ldloc.s  0xA
0x65f8f  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::HandleDownloadFailureException(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadFailureException ex, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException invalidSignatureException)
0x65f94  leave.s  loc_66009
0x65f96  stloc.s  0xB
0x65f98  ldloc.1
0x65f99  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x65f9e  ldarg.0
0x65f9f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65fa4  ldc.i4.4
0x65fa5  callvirt instance void ChannelStatusTracker::SetStatus(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelPair, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelStatus status)
0x65faa  ldstr    aCouldNotUpdate// "Could not update channel \""
0x65faf  ldarg.0
0x65fb0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x65fb5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x65fba  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x65fbf  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x65fc4  ldstr    asc_8B518// "\""
0x65fc9  call     string [mscorlib]System.String::Concat(string, string, string)
0x65fce  stloc.s  0xC
0x65fd0  ldloc.1
0x65fd1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x65fd6  dup
0x65fd7  brtrue.s loc_65FDC
0x65fd9  pop
0x65fda  br.s     loc_65FEA
0x65fdc  ldloc.s  0xB
0x65fde  ldloc.s  0xC
0x65fe0  call     T0x2B000003
0x65fe5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x65fea  ldarg.0
0x65feb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x65ff0  dup
0x65ff1  brtrue.s loc_65FF6
0x65ff3  pop
0x65ff4  br.s     loc_66007
0x65ff6  ldloc.s  0xC
0x65ff8  ldloc.s  0xB
0x65ffa  ldloc.s  0xB
0x65ffc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x66001  ldc.i4.1
0x66002  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x66007  rethrow
0x66009  ldarg.0
0x6600a  ldarg.0
0x6600b  ldflda   valuetype ManifestDownloadSummary <UpdateChannelManifestAsync>d__70::<downloadSummary>5__3
0x66010  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest ManifestDownloadSummary::get_Manifest()
0x66015  dup
0x66016  brtrue.s loc_66024
0x66018  pop
0x66019  ldarg.0
0x6601a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x6601f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x66024  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <UpdateChannelManifestAsync>d__70::<latestChannelManifest>5__5
0x66029  ldarg.0
0x6602a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x6602f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x66034  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x66039  stloc.s  5
0x6603b  ldarg.0
0x6603c  ldarg.0
0x6603d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <UpdateChannelManifestAsync>d__70::<latestChannelManifest>5__5
0x66042  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x66047  stfld    class [mscorlib]System.Version <UpdateChannelManifestAsync>d__70::<downloadedVersion>5__6
0x6604c  ldloc.s  5
0x6604e  ldarg.0
0x6604f  ldfld    class [mscorlib]System.Version <UpdateChannelManifestAsync>d__70::<downloadedVersion>5__6
0x66054  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x66059  brtrue.s loc_6607B
0x6605b  ldarg.0
0x6605c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <UpdateChannelManifestAsync>d__70::<latestChannelManifest>5__5
0x66061  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_IsRetired()
0x66066  ldarg.0
0x66067  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x6606c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x66071  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_IsRetired()
0x66076  beq      loc_66341
0x6607b  ldarg.0
0x6607c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x66081  dup
0x66082  brtrue.s loc_66087
0x66084  pop
0x66085  br.s     loc_66098
0x66087  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x6608c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::OLDCHANNELMANIFESTVERSION
0x66091  ldloc.s  5
0x66093  call     void Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> dictionary, string key, object value)
0x66098  ldarg.0
0x66099  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <UpdateChannelManifestAsync>d__70::<updateAsyncOperation>5__2
0x6609e  dup
0x6609f  brtrue.s loc_660A4
0x660a1  pop
0x660a2  br.s     loc_660B9
0x660a4  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x660a9  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::NEWCHANNELMANIFESTVERSION
0x660ae  ldarg.0
0x660af  ldfld    class [mscorlib]System.Version <UpdateChannelManifestAsync>d__70::<downloadedVersion>5__6
0x660b4  call     void Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> dictionary, string key, object value)
0x660b9  ldarg.0
0x660ba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <UpdateChannelManifestAsync>d__70::<latestChannelManifest>5__5
0x660bf  ldarg.0
0x660c0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <UpdateChannelManifestAsync>d__70::channelManifestPair
0x660c5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x660ca  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x660cf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::set_UpdateUri(class [System]System.Uri)
0x660d4  ldarg.0
0x660d5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <UpdateChannelManifestAsync>d__70::<latestChannelManifest>5__5
0x660da  ldc.i4.1
0x660db  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::set_CanUpdate(bool)
0x660e0  ldnull
0x660e1  stloc.s  0xD
0x660e3  ldarg.0
0x660e4  ldfld    bool <UpdateChannelManifestAsync>d__70::downloadOfflineInstaller
0x660e9  brfalse  loc_661A5
0x660ee  ldloc.1
0x660ef  call     instance class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.ChannelManagerBase::get_Services()
0x660f4  ldc.i4.0
  ... truncated ...
```
