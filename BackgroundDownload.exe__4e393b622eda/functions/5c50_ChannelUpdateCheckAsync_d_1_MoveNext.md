# <ChannelUpdateCheckAsync>d__1::MoveNext

- ea: `0x5c50`
- end: `0x5f55`
- name: `<ChannelUpdateCheckAsync>d__1::MoveNext`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x5bd0`
- `0x5c50`

## pseudocode

```c

```

## disassembly

```asm
0x5c50  ldarg.0
0x5c51  ldfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5c56  stloc.0
0x5c57  ldloc.0
0x5c58  switch   loc_5CD1, loc_5E00, loc_5E83, loc_5EF3
0x5c6d  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x5c72  stloc.1
0x5c73  ldloc.1
0x5c74  ldarg.0
0x5c75  ldfld    string <ChannelUpdateCheckAsync>d__1::instanceId
0x5c7a  stfld    string <>c__DisplayClass1_0::instanceId
0x5c7f  ldloc.1
0x5c80  ldfld    string <>c__DisplayClass1_0::instanceId
0x5c85  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5c8a  brfalse.s loc_5CFB
0x5c8c  ldarg.0
0x5c8d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5c92  ldarg.0
0x5c93  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ChannelUpdateCheckAsync>d__1::cancellationToken
0x5c98  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::UpdateAllAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x5c9d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x5ca2  stloc.s  4
0x5ca4  ldloca.s 4
0x5ca6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x5cab  brtrue.s loc_5CEE
0x5cad  ldarg.0
0x5cae  ldc.i4.0
0x5caf  dup
0x5cb0  stloc.0
0x5cb1  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5cb6  ldarg.0
0x5cb7  ldloc.s  4
0x5cb9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5cbe  ldarg.0
0x5cbf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5cc4  ldloca.s 4
0x5cc6  ldarg.0
0x5cc7  call     T0x2B00006B
0x5ccc  leave    loc_5F54
0x5cd1  ldarg.0
0x5cd2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5cd7  stloc.s  4
0x5cd9  ldarg.0
0x5cda  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5cdf  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x5ce5  ldarg.0
0x5ce6  ldc.i4.m1
0x5ce7  dup
0x5ce8  stloc.0
0x5ce9  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5cee  ldloca.s 4
0x5cf0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x5cf5  pop
0x5cf6  leave    loc_5F3A
0x5cfb  ldarg.0
0x5cfc  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <ChannelUpdateCheckAsync>d__1::instances
0x5d01  ldloc.1
0x5d02  ldftn    instance bool <>c__DisplayClass1_0::<ChannelUpdateCheckAsync>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance i)
0x5d08  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool>::.ctor(object, native int)
0x5d0d  call     T0x2B00006C
0x5d12  dup
0x5d13  brtrue.s loc_5D31
0x5d15  pop
0x5d16  ldstr    aTheInstance// "The instance "
0x5d1b  ldloc.1
0x5d1c  ldfld    string <>c__DisplayClass1_0::instanceId
0x5d21  ldstr    aDoesnTExistOnT// " doesn't exist on this system."
0x5d26  call     string [mscorlib]System.String::Concat(string, string, string)
0x5d2b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5d30  throw
0x5d31  stloc.2
0x5d32  ldarg.0
0x5d33  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5d38  ldloc.2
0x5d39  ldc.i4.0
0x5d3a  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::GetChannelForInstance(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool)
0x5d3f  stloc.3
0x5d40  ldloc.3
0x5d41  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x5d46  brfalse.s loc_5D8A
0x5d48  ldloc.3
0x5d49  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x5d4e  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x5d53  dup
0x5d54  brtrue.s loc_5D69
0x5d56  pop
0x5d57  ldloc.3
0x5d58  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x5d5d  dup
0x5d5e  brtrue.s loc_5D64
0x5d60  pop
0x5d61  ldnull
0x5d62  br.s     loc_5D69
0x5d64  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x5d69  stloc.s  5
0x5d6b  ldloc.s  5
0x5d6d  brfalse.s loc_5D8A
0x5d6f  ldarg.0
0x5d70  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5d75  ldloc.s  5
0x5d77  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::RemoveInstallChannel(class [System]System.Uri)
0x5d7c  ldarg.0
0x5d7d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5d82  ldloc.2
0x5d83  ldc.i4.0
0x5d84  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::GetChannelForInstance(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool)
0x5d89  stloc.3
0x5d8a  ldarg.0
0x5d8b  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions::.ctor()
0x5d90  dup
0x5d91  ldc.i4.0
0x5d92  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions::set_DownloadOfflineInstaller(bool)
0x5d97  dup
0x5d98  ldc.i4.1
0x5d99  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions::set_ThrowOnUpdateRequired(bool)
0x5d9e  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions <ChannelUpdateCheckAsync>d__1::<updateOption>5__2
0x5da3  ldarg.0
0x5da4  ldfld    class [System]System.Uri <ChannelUpdateCheckAsync>d__1::installChannelUri
0x5da9  brfalse  loc_5EAA
0x5dae  ldarg.0
0x5daf  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5db4  ldloc.2
0x5db5  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_ChannelUri()
0x5dba  ldarg.0
0x5dbb  ldfld    class [System]System.Uri <ChannelUpdateCheckAsync>d__1::installChannelUri
0x5dc0  ldarg.0
0x5dc1  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ChannelUpdateCheckAsync>d__1::cancellationToken
0x5dc6  ldnull
0x5dc7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::AddAsync(class [System]System.Uri, class [System]System.Uri, valuetype [mscorlib]System.Threading.CancellationToken, class [System]System.Uri)
0x5dcc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetAwaiter()
0x5dd1  stloc.s  7
0x5dd3  ldloca.s 7
0x5dd5  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::get_IsCompleted()
0x5dda  brtrue.s loc_5E1D
0x5ddc  ldarg.0
0x5ddd  ldc.i4.1
0x5dde  dup
0x5ddf  stloc.0
0x5de0  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5de5  ldarg.0
0x5de6  ldloc.s  7
0x5de8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChannelUpdateCheckAsync>d__1::<>u__2
0x5ded  ldarg.0
0x5dee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5df3  ldloca.s 7
0x5df5  ldarg.0
0x5df6  call     T0x2B00006D
0x5dfb  leave    loc_5F54
0x5e00  ldarg.0
0x5e01  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChannelUpdateCheckAsync>d__1::<>u__2
0x5e06  stloc.s  7
0x5e08  ldarg.0
0x5e09  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChannelUpdateCheckAsync>d__1::<>u__2
0x5e0e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>
0x5e14  ldarg.0
0x5e15  ldc.i4.m1
0x5e16  dup
0x5e17  stloc.0
0x5e18  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5e1d  ldloca.s 7
0x5e1f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetResult()
0x5e24  stloc.s  6
0x5e26  ldarg.0
0x5e27  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5e2c  ldarg.0
0x5e2d  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ChannelUpdateCheckAsync>d__1::cancellationToken
0x5e32  ldarg.0
0x5e33  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions <ChannelUpdateCheckAsync>d__1::<updateOption>5__2
0x5e38  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions::get_ThrowOnUpdateRequired()
0x5e3d  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::EnsureEngineCanReadManifests(valuetype [mscorlib]System.Threading.CancellationToken, bool)
0x5e42  ldarg.0
0x5e43  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5e48  ldloc.s  6
0x5e4a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::AddCatalogForChannelAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair)
0x5e4f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x5e54  stloc.s  4
0x5e56  ldloca.s 4
0x5e58  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x5e5d  brtrue.s loc_5EA0
0x5e5f  ldarg.0
0x5e60  ldc.i4.2
0x5e61  dup
0x5e62  stloc.0
0x5e63  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5e68  ldarg.0
0x5e69  ldloc.s  4
0x5e6b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5e70  ldarg.0
0x5e71  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5e76  ldloca.s 4
0x5e78  ldarg.0
0x5e79  call     T0x2B00006B
0x5e7e  leave    loc_5F54
0x5e83  ldarg.0
0x5e84  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5e89  stloc.s  4
0x5e8b  ldarg.0
0x5e8c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ChannelUpdateCheckAsync>d__1::<>u__1
0x5e91  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x5e97  ldarg.0
0x5e98  ldc.i4.m1
0x5e99  dup
0x5e9a  stloc.0
0x5e9b  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5ea0  ldloca.s 4
0x5ea2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x5ea7  pop
0x5ea8  br.s     loc_5F18
0x5eaa  ldarg.0
0x5eab  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <ChannelUpdateCheckAsync>d__1::channelManager
0x5eb0  ldloc.3
0x5eb1  ldarg.0
0x5eb2  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions <ChannelUpdateCheckAsync>d__1::<updateOption>5__2
0x5eb7  ldarg.0
0x5eb8  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ChannelUpdateCheckAsync>d__1::cancellationToken
0x5ebd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::UpdateAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions, valuetype [mscorlib]System.Threading.CancellationToken)
0x5ec2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetAwaiter()
0x5ec7  stloc.s  8
0x5ec9  ldloca.s 8
0x5ecb  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::get_IsCompleted()
0x5ed0  brtrue.s loc_5F10
0x5ed2  ldarg.0
0x5ed3  ldc.i4.3
0x5ed4  dup
0x5ed5  stloc.0
0x5ed6  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5edb  ldarg.0
0x5edc  ldloc.s  8
0x5ede  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <ChannelUpdateCheckAsync>d__1::<>u__3
0x5ee3  ldarg.0
0x5ee4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5ee9  ldloca.s 8
0x5eeb  ldarg.0
0x5eec  call     T0x2B00006E
0x5ef1  leave.s  loc_5F54
0x5ef3  ldarg.0
0x5ef4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <ChannelUpdateCheckAsync>d__1::<>u__3
0x5ef9  stloc.s  8
0x5efb  ldarg.0
0x5efc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <ChannelUpdateCheckAsync>d__1::<>u__3
0x5f01  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation>
0x5f07  ldarg.0
0x5f08  ldc.i4.m1
0x5f09  dup
0x5f0a  stloc.0
0x5f0b  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5f10  ldloca.s 8
0x5f12  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetResult()
0x5f17  pop
0x5f18  leave.s  loc_5F3A
0x5f1a  stloc.s  9
0x5f1c  ldarg.0
0x5f1d  ldc.i4.s 0xFE
0x5f1f  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5f24  ldarg.0
0x5f25  ldnull
0x5f26  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions <ChannelUpdateCheckAsync>d__1::<updateOption>5__2
0x5f2b  ldarg.0
0x5f2c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5f31  ldloc.s  9
0x5f33  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x5f38  leave.s  loc_5F54
0x5f3a  ldarg.0
0x5f3b  ldc.i4.s 0xFE
0x5f3d  stfld    int32 <ChannelUpdateCheckAsync>d__1::<>1__state
0x5f42  ldarg.0
0x5f43  ldnull
0x5f44  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelSets.UpdateOptions <ChannelUpdateCheckAsync>d__1::<updateOption>5__2
0x5f49  ldarg.0
0x5f4a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ChannelUpdateCheckAsync>d__1::<>t__builder
0x5f4f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x5f54  ret
```
