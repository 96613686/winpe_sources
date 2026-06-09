# Microsoft.VisualStudio.Setup.Extensions::IsHybridFeatureEnabledAsync

- ea: `0x24d0`
- end: `0x250f`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsHybridFeatureEnabledAsync`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x51a0`

## pseudocode

```c

```

## disassembly

```asm
0x24d0  ldloca.s 0
0x24d2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::Create()
0x24d7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x24dc  ldloca.s 0
0x24de  ldarg.0
0x24df  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <IsHybridFeatureEnabledAsync>d__0::remoteSettings
0x24e4  ldloca.s 0
0x24e6  ldarg.1
0x24e7  stfld    valuetype [mscorlib]System.Threading.CancellationToken <IsHybridFeatureEnabledAsync>d__0::token
0x24ec  ldloca.s 0
0x24ee  ldc.i4.m1
0x24ef  stfld    int32 <IsHybridFeatureEnabledAsync>d__0::<>1__state
0x24f4  ldloca.s 0
0x24f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x24fb  ldloca.s 0
0x24fd  call     T0x2B000037
0x2502  ldloca.s 0
0x2504  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <IsHybridFeatureEnabledAsync>d__0::<>t__builder
0x2509  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::get_Task()
0x250e  ret
```
