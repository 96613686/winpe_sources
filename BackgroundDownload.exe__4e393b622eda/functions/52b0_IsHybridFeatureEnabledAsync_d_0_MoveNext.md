# <IsHybridFeatureEnabledAsync>d__0::MoveNext

- ea: `0x52b0`
- end: `0x535f`
- name: `<IsHybridFeatureEnabledAsync>d__0::MoveNext`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x52b0`

## pseudocode

```c

```

## disassembly

```asm
0x52b0  ldarg.0
0x52b1  ldfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x52b6  stloc.0
0x52b7  ldloc.0
0x52b8  pop
0x52b9  nop
0x52ba  ldloc.0
0x52bb  brfalse.s loc_5308
0x52bd  ldarg.0
0x52be  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <IsHybridFeatureEnabledAsync>d__0::remoteSettings
0x52c3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::FeaturesPath
0x52c8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::EnableHybridBackgroundDownload
0x52cd  ldc.i4.0
0x52ce  ldarg.0
0x52cf  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <IsHybridFeatureEnabledAsync>d__0::token
0x52d4  callvirt T0x2B000055
0x52d9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x52de  stloc.2
0x52df  ldloca.s 2
0x52e1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x52e6  brtrue.s loc_5324
0x52e8  ldarg.0
0x52e9  ldc.i4.0
0x52ea  dup
0x52eb  stloc.0
0x52ec  stfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x52f1  ldarg.0
0x52f2  ldloc.2
0x52f3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>u__1
0x52f8  ldarg.0
0x52f9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x52fe  ldloca.s 2
0x5300  ldarg.0
0x5301  call     T0x2B000060
0x5306  leave.s  loc_535E
0x5308  ldarg.0
0x5309  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>u__1
0x530e  stloc.2
0x530f  ldarg.0
0x5310  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>u__1
0x5315  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x531b  ldarg.0
0x531c  ldc.i4.m1
0x531d  dup
0x531e  stloc.0
0x531f  stfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x5324  ldloca.s 2
0x5326  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x532b  stloc.1
0x532c  leave.s  loc_534A
0x532e  pop
0x532f  ldc.i4.0
0x5330  stloc.1
0x5331  leave.s  loc_534A
0x5333  stloc.3
0x5334  ldarg.0
0x5335  ldc.i4.s 0xFE
0x5337  stfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x533c  ldarg.0
0x533d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x5342  ldloc.3
0x5343  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x5348  leave.s  loc_535E
0x534a  ldarg.0
0x534b  ldc.i4.s 0xFE
0x534d  stfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x5352  ldarg.0
0x5353  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x5358  ldloc.1
0x5359  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x535e  ret
```
