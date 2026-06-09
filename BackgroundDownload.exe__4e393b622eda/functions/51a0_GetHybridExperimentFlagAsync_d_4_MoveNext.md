# <GetHybridExperimentFlagAsync>d__4::MoveNext

- ea: `0x51a0`
- end: `0x5286`
- name: `<GetHybridExperimentFlagAsync>d__4::MoveNext`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x24d0`
- `0x51a0`

## pseudocode

```c

```

## disassembly

```asm
0x51a0  ldarg.0
0x51a1  ldfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x51a6  stloc.0
0x51a7  ldloc.0
0x51a8  brfalse.s loc_51B5
0x51aa  ldarg.0
0x51ab  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x51b0  stfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x51b5  nop
0x51b6  ldloc.0
0x51b7  brfalse.s loc_520E
0x51b9  ldarg.0
0x51ba  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x51bf  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.BackgroundDownloadConstants::RemoteSettingsTimeout
0x51c4  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::CancelAfter(valuetype [mscorlib]System.TimeSpan)
0x51c9  ldarg.0
0x51ca  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <GetHybridExperimentFlagAsync>d__4::remoteSettings
0x51cf  ldarg.0
0x51d0  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x51d5  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x51da  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Extensions::IsHybridFeatureEnabledAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService remoteSettings, valuetype [mscorlib]System.Threading.CancellationToken token)
0x51df  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x51e4  stloc.2
0x51e5  ldloca.s 2
0x51e7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x51ec  brtrue.s loc_522A
0x51ee  ldarg.0
0x51ef  ldc.i4.0
0x51f0  dup
0x51f1  stloc.0
0x51f2  stfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x51f7  ldarg.0
0x51f8  ldloc.2
0x51f9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <GetHybridExperimentFlagAsync>d__4::<>u__1
0x51fe  ldarg.0
0x51ff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x5204  ldloca.s 2
0x5206  ldarg.0
0x5207  call     T0x2B00005F
0x520c  leave.s  loc_5285
0x520e  ldarg.0
0x520f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <GetHybridExperimentFlagAsync>d__4::<>u__1
0x5214  stloc.2
0x5215  ldarg.0
0x5216  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <GetHybridExperimentFlagAsync>d__4::<>u__1
0x521b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x5221  ldarg.0
0x5222  ldc.i4.m1
0x5223  dup
0x5224  stloc.0
0x5225  stfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x522a  ldloca.s 2
0x522c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x5231  stloc.1
0x5232  leave.s  loc_526A
0x5234  ldloc.0
0x5235  ldc.i4.0
0x5236  bge.s    loc_524B
0x5238  ldarg.0
0x5239  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x523e  brfalse.s loc_524B
0x5240  ldarg.0
0x5241  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x5246  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x524b  endfinally
0x524c  stloc.3
0x524d  ldarg.0
0x524e  ldc.i4.s 0xFE
0x5250  stfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x5255  ldarg.0
0x5256  ldnull
0x5257  stfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x525c  ldarg.0
0x525d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x5262  ldloc.3
0x5263  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x5268  leave.s  loc_5285
0x526a  ldarg.0
0x526b  ldc.i4.s 0xFE
0x526d  stfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x5272  ldarg.0
0x5273  ldnull
0x5274  stfld    class [mscorlib]System.Threading.CancellationTokenSource <GetHybridExperimentFlagAsync>d__4::<cancellationTokenSource>5__2
0x5279  ldarg.0
0x527a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x527f  ldloc.1
0x5280  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x5285  ret
```
