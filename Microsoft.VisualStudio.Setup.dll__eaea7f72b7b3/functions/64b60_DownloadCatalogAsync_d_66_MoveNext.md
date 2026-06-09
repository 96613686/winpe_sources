# <DownloadCatalogAsync>d__66::MoveNext

- ea: `0x64b60`
- end: `0x64def`
- name: `<DownloadCatalogAsync>d__66::MoveNext`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4e20`
- `0xee90`
- `0xef30`
- `0xef80`
- `0x10dc0`
- `0x64b60`

## string_xrefs

- `0x64c55`: `Downloading installable manifest from "{0}" and using the channel URI "{1}".`
- `0x64d2e`: `Downloading installable manifest from "{0}" and using the channel URI "{1}".`

## pseudocode

```c

```

## disassembly

```asm
0x64b60  ldarg.0
0x64b61  ldfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64b66  stloc.0
0x64b67  ldarg.0
0x64b68  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <DownloadCatalogAsync>d__66::<>4__this
0x64b6d  stloc.1
0x64b6e  ldloc.0
0x64b6f  brfalse  loc_64C45
0x64b74  ldloc.0
0x64b75  ldc.i4.1
0x64b76  beq      loc_64D96
0x64b7b  ldarg.0
0x64b7c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64b81  brfalse  loc_64DBD
0x64b86  ldarg.0
0x64b87  ldarg.0
0x64b88  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64b8d  ldc.i4.1
0x64b8e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::GetChannel(bool)
0x64b93  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IManifestItem> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel::get_ProductManifest()
0x64b98  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IManifestItem>::get_Item()
0x64b9d  call     class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetPayloadUri(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelItemWithPayloads)
0x64ba2  stfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<catalogUri>5__2
0x64ba7  ldarg.0
0x64ba8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64bad  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_CanUpdate()
0x64bb2  brfalse  loc_64D22
0x64bb7  ldarg.0
0x64bb8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64bbd  call     bool Microsoft.VisualStudio.Setup.Extensions::IsLayoutChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest)
0x64bc2  brfalse.s loc_64BF6
0x64bc4  ldarg.0
0x64bc5  ldarg.0
0x64bc6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64bcb  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x64bd0  ldarg.0
0x64bd1  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<catalogUri>5__2
0x64bd6  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x64bdb  ldloc.1
0x64bdc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x64be1  ldloc.1
0x64be2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ChannelManager::fileSystem
0x64be7  call     class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetLayoutArtifactPath(class [System]System.Uri, class [System]System.Uri, string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem)
0x64bec  stfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<catalogUri>5__2
0x64bf1  br       loc_64D22
0x64bf6  ldarg.0
0x64bf7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64bfc  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x64c01  brfalse  loc_64D22
0x64c06  ldarg.0
0x64c07  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64c0c  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x64c11  stloc.3
0x64c12  ldarg.0
0x64c13  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64c18  call     bool Microsoft.VisualStudio.Setup.Extensions::IsWebLayoutChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest)
0x64c1d  brfalse  loc_64D22
0x64c22  ldloc.3
0x64c23  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Extensions::GetLayoutUrlFromChannelUrl(class [System]System.Uri)
0x64c28  stloc.s  4
0x64c2a  ldarg.0
0x64c2b  ldloc.s  4
0x64c2d  ldc.i4.1
0x64c2e  newarr   [mscorlib]System.String
0x64c33  dup
0x64c34  ldc.i4.0
0x64c35  ldsfld   string Microsoft.VisualStudio.Setup.LayoutConstants::CatalogFileName
0x64c3a  stelem.ref
0x64c3b  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Extensions::Combine(class [System]System.Uri uri, string[] additionalParts)
0x64c40  stfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<layoutCatalogUri>5__3
0x64c45  nop
0x64c46  ldloc.0
0x64c47  brfalse.s loc_64CC0
0x64c49  ldloc.1
0x64c4a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x64c4f  dup
0x64c50  brtrue.s loc_64C55
0x64c52  pop
0x64c53  br.s     loc_64C7A
0x64c55  ldstr    aDownloadingIns// "Downloading installable manifest from "...
0x64c5a  ldarg.0
0x64c5b  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<layoutCatalogUri>5__3
0x64c60  ldarg.0
0x64c61  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64c66  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x64c6b  call     string [mscorlib]System.String::Format(string, object, object)
0x64c70  call     T0x2B000003
0x64c75  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x64c7a  ldloc.1
0x64c7b  ldarg.0
0x64c7c  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<layoutCatalogUri>5__3
0x64c81  ldarg.0
0x64c82  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadCatalogAsync>d__66::cancellationToken
0x64c87  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadJsonFileAsync(class [System]System.Uri uri, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x64c8c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x64c91  stloc.s  5
0x64c93  ldloca.s 5
0x64c95  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x64c9a  brtrue.s loc_64CDD
0x64c9c  ldarg.0
0x64c9d  ldc.i4.0
0x64c9e  dup
0x64c9f  stloc.0
0x64ca0  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64ca5  ldarg.0
0x64ca6  ldloc.s  5
0x64ca8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64cad  ldarg.0
0x64cae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadCatalogAsync>d__66::<>t__builder
0x64cb3  ldloca.s 5
0x64cb5  ldarg.0
0x64cb6  call     T0x2B0002BB
0x64cbb  leave    loc_64DEE
0x64cc0  ldarg.0
0x64cc1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64cc6  stloc.s  5
0x64cc8  ldarg.0
0x64cc9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64cce  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x64cd4  ldarg.0
0x64cd5  ldc.i4.m1
0x64cd6  dup
0x64cd7  stloc.0
0x64cd8  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64cdd  ldloca.s 5
0x64cdf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x64ce4  stloc.2
0x64ce5  leave    loc_64DDA
0x64cea  stloc.s  6
0x64cec  ldloc.1
0x64ced  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x64cf2  dup
0x64cf3  brtrue.s loc_64CF8
0x64cf5  pop
0x64cf6  br.s     loc_64D19
0x64cf8  ldstr    aDownloadOf0IsF// "Download of {0} is failed. {1}"
0x64cfd  ldarg.0
0x64cfe  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<layoutCatalogUri>5__3
0x64d03  ldloc.s  6
0x64d05  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64d0a  call     string [mscorlib]System.String::Format(string, object, object)
0x64d0f  call     T0x2B000003
0x64d14  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x64d19  leave.s  loc_64D1B
0x64d1b  ldarg.0
0x64d1c  ldnull
0x64d1d  stfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<layoutCatalogUri>5__3
0x64d22  ldloc.1
0x64d23  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x64d28  dup
0x64d29  brtrue.s loc_64D2E
0x64d2b  pop
0x64d2c  br.s     loc_64D53
0x64d2e  ldstr    aDownloadingIns// "Downloading installable manifest from "...
0x64d33  ldarg.0
0x64d34  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<catalogUri>5__2
0x64d39  ldarg.0
0x64d3a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCatalogAsync>d__66::channelManifest
0x64d3f  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x64d44  call     string [mscorlib]System.String::Format(string, object, object)
0x64d49  call     T0x2B000003
0x64d4e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x64d53  ldloc.1
0x64d54  ldarg.0
0x64d55  ldfld    class [System]System.Uri <DownloadCatalogAsync>d__66::<catalogUri>5__2
0x64d5a  ldarg.0
0x64d5b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadCatalogAsync>d__66::cancellationToken
0x64d60  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadJsonFileAsync(class [System]System.Uri uri, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x64d65  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x64d6a  stloc.s  5
0x64d6c  ldloca.s 5
0x64d6e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x64d73  brtrue.s loc_64DB3
0x64d75  ldarg.0
0x64d76  ldc.i4.1
0x64d77  dup
0x64d78  stloc.0
0x64d79  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64d7e  ldarg.0
0x64d7f  ldloc.s  5
0x64d81  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64d86  ldarg.0
0x64d87  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadCatalogAsync>d__66::<>t__builder
0x64d8c  ldloca.s 5
0x64d8e  ldarg.0
0x64d8f  call     T0x2B0002BB
0x64d94  leave.s  loc_64DEE
0x64d96  ldarg.0
0x64d97  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64d9c  stloc.s  5
0x64d9e  ldarg.0
0x64d9f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadCatalogAsync>d__66::<>u__1
0x64da4  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x64daa  ldarg.0
0x64dab  ldc.i4.m1
0x64dac  dup
0x64dad  stloc.0
0x64dae  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64db3  ldloca.s 5
0x64db5  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x64dba  stloc.2
0x64dbb  leave.s  loc_64DDA
0x64dbd  ldnull
0x64dbe  stloc.2
0x64dbf  leave.s  loc_64DDA
0x64dc1  stloc.s  7
0x64dc3  ldarg.0
0x64dc4  ldc.i4.s 0xFE
0x64dc6  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64dcb  ldarg.0
0x64dcc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadCatalogAsync>d__66::<>t__builder
0x64dd1  ldloc.s  7
0x64dd3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x64dd8  leave.s  loc_64DEE
0x64dda  ldarg.0
0x64ddb  ldc.i4.s 0xFE
0x64ddd  stfld    int32 <DownloadCatalogAsync>d__66::<>1__state
0x64de2  ldarg.0
0x64de3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadCatalogAsync>d__66::<>t__builder
0x64de8  ldloc.2
0x64de9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x64dee  ret
```
