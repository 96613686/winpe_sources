# Microsoft.VisualStudio.Setup.CompositionRoot::GetHybridExperimentFlagAsync

- ea: `0x23e0`
- end: `0x2417`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::GetHybridExperimentFlagAsync`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4de0`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  ldloca.s 0
0x23e2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::Create()
0x23e7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x23ec  ldloca.s 0
0x23ee  ldarg.0
0x23ef  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <GetHybridExperimentFlagAsync>d__4::remoteSettings
0x23f4  ldloca.s 0
0x23f6  ldc.i4.m1
0x23f7  stfld    int32 <GetHybridExperimentFlagAsync>d__4::<>1__state
0x23fc  ldloca.s 0
0x23fe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x2403  ldloca.s 0
0x2405  call     T0x2B000033
0x240a  ldloca.s 0
0x240c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <GetHybridExperimentFlagAsync>d__4::<>t__builder
0x2411  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::get_Task()
0x2416  ret
```
