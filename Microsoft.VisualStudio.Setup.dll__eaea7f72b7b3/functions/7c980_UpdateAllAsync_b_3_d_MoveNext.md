# <<UpdateAllAsync>b__3>d::MoveNext

- ea: `0x7c980`
- end: `0x7cc05`
- name: `<<UpdateAllAsync>b__3>d::MoveNext`
- size: `645`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x4b70`
- `0x4be0`
- `0x116a0`
- `0x7c980`

## string_xrefs

- `0x7cad6`: `UpdateAllAsync canceled for channel: `
- `0x7cb19`: `UpdateAllAsync failed for channel: `
- `0x7cb8e`: `UpdateAllAsync`

## pseudocode

```c

```

## disassembly

```asm
0x7c980  ldarg.0
0x7c981  ldfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7c986  stloc.0
0x7c987  ldarg.0
0x7c988  ldfld    class <>c__DisplayClass56_1 <<UpdateAllAsync>b__3>d::<>4__this
0x7c98d  stloc.1
0x7c98e  ldloc.0
0x7c98f  ldc.i4.1
0x7c990  pop
0x7c991  pop
0x7c992  nop
0x7c993  ldloc.0
0x7c994  brfalse.s loc_7CA07
0x7c996  ldloc.0
0x7c997  ldc.i4.1
0x7c998  beq      loc_7CA95
0x7c99d  ldnull
0x7c99e  stloc.3
0x7c99f  ldloc.1
0x7c9a0  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7c9a5  ldfld    bool <>c__DisplayClass56_0::updateCatalogs
0x7c9aa  brfalse  loc_7CA3D
0x7c9af  ldloc.1
0x7c9b0  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7c9b5  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <>c__DisplayClass56_0::<>4__this
0x7c9ba  ldloc.1
0x7c9bb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <>c__DisplayClass56_1::channelManifestItem
0x7c9c0  ldc.i4.0
0x7c9c1  ldc.i4.0
0x7c9c2  ldc.i4.0
0x7c9c3  ldloc.1
0x7c9c4  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7c9c9  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass56_0::cancellationToken
0x7c9ce  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> Microsoft.VisualStudio.Setup.ChannelManager::UpdateAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, bool throwOnUpdateRequired, bool downloadOfflineInstaller, bool alwaysCacheManifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7c9d3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetAwaiter()
0x7c9d8  stloc.s  4
0x7c9da  ldloca.s 4
0x7c9dc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::get_IsCompleted()
0x7c9e1  brtrue.s loc_7CA24
0x7c9e3  ldarg.0
0x7c9e4  ldc.i4.0
0x7c9e5  dup
0x7c9e6  stloc.0
0x7c9e7  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7c9ec  ldarg.0
0x7c9ed  ldloc.s  4
0x7c9ef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7c9f4  ldarg.0
0x7c9f5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <<UpdateAllAsync>b__3>d::<>t__builder
0x7c9fa  ldloca.s 4
0x7c9fc  ldarg.0
0x7c9fd  call     T0x2B000395
0x7ca02  leave    loc_7CC04
0x7ca07  ldarg.0
0x7ca08  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7ca0d  stloc.s  4
0x7ca0f  ldarg.0
0x7ca10  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7ca15  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>
0x7ca1b  ldarg.0
0x7ca1c  ldc.i4.m1
0x7ca1d  dup
0x7ca1e  stloc.0
0x7ca1f  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7ca24  ldloca.s 4
0x7ca26  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetResult()
0x7ca2b  dup
0x7ca2c  brtrue.s loc_7CA32
0x7ca2e  pop
0x7ca2f  ldnull
0x7ca30  br.s     loc_7CA37
0x7ca32  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.IChannelUpdateInformation::get_ChannelManifest()
0x7ca37  stloc.3
0x7ca38  br       loc_7CAC6
0x7ca3d  ldloc.1
0x7ca3e  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7ca43  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <>c__DisplayClass56_0::<>4__this
0x7ca48  ldloc.1
0x7ca49  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <>c__DisplayClass56_1::channelManifestItem
0x7ca4e  ldc.i4.0
0x7ca4f  ldc.i4.0
0x7ca50  ldc.i4.0
0x7ca51  ldloc.1
0x7ca52  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7ca57  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass56_0::cancellationToken
0x7ca5c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> Microsoft.VisualStudio.Setup.ChannelManager::UpdateChannelManifestAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, bool throwOnUpdateRequired, bool downloadOfflineInstaller, bool alwaysCacheManifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7ca61  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetAwaiter()
0x7ca66  stloc.s  4
0x7ca68  ldloca.s 4
0x7ca6a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::get_IsCompleted()
0x7ca6f  brtrue.s loc_7CAB2
0x7ca71  ldarg.0
0x7ca72  ldc.i4.1
0x7ca73  dup
0x7ca74  stloc.0
0x7ca75  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7ca7a  ldarg.0
0x7ca7b  ldloc.s  4
0x7ca7d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7ca82  ldarg.0
0x7ca83  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <<UpdateAllAsync>b__3>d::<>t__builder
0x7ca88  ldloca.s 4
0x7ca8a  ldarg.0
0x7ca8b  call     T0x2B000395
0x7ca90  leave    loc_7CC04
0x7ca95  ldarg.0
0x7ca96  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7ca9b  stloc.s  4
0x7ca9d  ldarg.0
0x7ca9e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation> <<UpdateAllAsync>b__3>d::<>u__1
0x7caa3  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>
0x7caa9  ldarg.0
0x7caaa  ldc.i4.m1
0x7caab  dup
0x7caac  stloc.0
0x7caad  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7cab2  ldloca.s 4
0x7cab4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.IChannelUpdateInformation>::GetResult()
0x7cab9  dup
0x7caba  brtrue.s loc_7CAC0
0x7cabc  pop
0x7cabd  ldnull
0x7cabe  br.s     loc_7CAC5
0x7cac0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.IChannelUpdateInformation::get_ChannelManifest()
0x7cac5  stloc.3
0x7cac6  ldloc.3
0x7cac7  brfalse.s loc_7CAD0
0x7cac9  ldc.i4.1
0x7caca  stloc.2
0x7cacb  leave    loc_7CBF0
0x7cad0  leave    loc_7CBD3
0x7cad5  pop
0x7cad6  ldstr    aUpdateallasync// "UpdateAllAsync canceled for channel: "
0x7cadb  ldloc.1
0x7cadc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <>c__DisplayClass56_1::channelManifestItem
0x7cae1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x7cae6  ldc.i4.1
0x7cae7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::GetChannel(bool)
0x7caec  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x7caf1  ldstr    asc_80DBA// "."
0x7caf6  call     string [mscorlib]System.String::Concat(string, string, string)
0x7cafb  stloc.s  5
0x7cafd  ldloc.1
0x7cafe  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cb03  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <>c__DisplayClass56_0::updateAllAsyncOperation
0x7cb08  dup
0x7cb09  brtrue.s loc_7CB0E
0x7cb0b  pop
0x7cb0c  br.s     loc_7CB15
0x7cb0e  ldloc.s  5
0x7cb10  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x7cb15  rethrow
0x7cb17  stloc.s  6
0x7cb19  ldstr    aUpdateallasync_0// "UpdateAllAsync failed for channel: "
0x7cb1e  ldloc.1
0x7cb1f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <>c__DisplayClass56_1::channelManifestItem
0x7cb24  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x7cb29  ldc.i4.1
0x7cb2a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::GetChannel(bool)
0x7cb2f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x7cb34  ldstr    asc_80DBA// "."
0x7cb39  call     string [mscorlib]System.String::Concat(string, string, string)
0x7cb3e  stloc.s  7
0x7cb40  ldloc.1
0x7cb41  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cb46  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <>c__DisplayClass56_0::<>4__this
0x7cb4b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x7cb50  dup
0x7cb51  brtrue.s loc_7CB56
0x7cb53  pop
0x7cb54  br.s     loc_7CB64
0x7cb56  ldloc.s  6
0x7cb58  ldloc.s  7
0x7cb5a  call     T0x2B000003
0x7cb5f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7cb64  ldloc.1
0x7cb65  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cb6a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass56_0::properties
0x7cb6f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x7cb74  ldstr    aChannelmanager_0// "ChannelManager"
0x7cb79  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cb7e  ldloc.1
0x7cb7f  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cb84  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass56_0::properties
0x7cb89  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x7cb8e  ldstr    aUpdateallasync_1// "UpdateAllAsync"
0x7cb93  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cb98  ldloc.1
0x7cb99  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cb9e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass56_0::properties
0x7cba3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTDESCRIPTIONPROPERTY
0x7cba8  ldloc.s  7
0x7cbaa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cbaf  ldloc.1
0x7cbb0  ldfld    class <>c__DisplayClass56_0 <>c__DisplayClass56_1::CS$<>8__locals1
0x7cbb5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <>c__DisplayClass56_0::updateAllAsyncOperation
0x7cbba  dup
0x7cbbb  brtrue.s loc_7CBC0
0x7cbbd  pop
0x7cbbe  br.s     loc_7CBD1
0x7cbc0  ldloc.s  7
0x7cbc2  ldloc.s  6
0x7cbc4  ldloc.s  6
0x7cbc6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7cbcb  ldc.i4.1
0x7cbcc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x7cbd1  leave.s  loc_7CBD3
0x7cbd3  ldc.i4.0
0x7cbd4  stloc.2
0x7cbd5  leave.s  loc_7CBF0
0x7cbd7  stloc.s  8
0x7cbd9  ldarg.0
0x7cbda  ldc.i4.s 0xFE
0x7cbdc  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7cbe1  ldarg.0
0x7cbe2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <<UpdateAllAsync>b__3>d::<>t__builder
0x7cbe7  ldloc.s  8
0x7cbe9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x7cbee  leave.s  loc_7CC04
0x7cbf0  ldarg.0
0x7cbf1  ldc.i4.s 0xFE
0x7cbf3  stfld    int32 <<UpdateAllAsync>b__3>d::<>1__state
0x7cbf8  ldarg.0
0x7cbf9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <<UpdateAllAsync>b__3>d::<>t__builder
0x7cbfe  ldloc.2
0x7cbff  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x7cc04  ret
```
