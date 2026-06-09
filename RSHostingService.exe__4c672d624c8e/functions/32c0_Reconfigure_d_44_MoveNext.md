# <Reconfigure>d__44::MoveNext

- ea: `0x32c0`
- end: `0x336c`
- name: `<Reconfigure>d__44::MoveNext`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x10a0`
- `0x18e0`
- `0x19c0`
- `0x32c0`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.0
0x32c1  ldfld    int32 <Reconfigure>d__44::<>1__state
0x32c6  stloc.0
0x32c7  ldarg.0
0x32c8  ldfld    class Microsoft.BIServer.BIService.BIService <Reconfigure>d__44::<>4__this
0x32cd  stloc.1
0x32ce  ldloc.0
0x32cf  brfalse.s loc_331C
0x32d1  ldloc.1
0x32d2  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0x32d7  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StopProcesses()
0x32dc  ldloc.1
0x32dd  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0x32e2  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::Clear()
0x32e7  ldloc.1
0x32e8  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::ReloadHostingState()
0x32ed  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x32f2  stloc.2
0x32f3  ldloca.s 2
0x32f5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x32fa  brtrue.s loc_3338
0x32fc  ldarg.0
0x32fd  ldc.i4.0
0x32fe  dup
0x32ff  stloc.0
0x3300  stfld    int32 <Reconfigure>d__44::<>1__state
0x3305  ldarg.0
0x3306  ldloc.2
0x3307  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Reconfigure>d__44::<>u__1
0x330c  ldarg.0
0x330d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x3312  ldloca.s 2
0x3314  ldarg.0
0x3315  call     T0x2B000021
0x331a  leave.s  loc_336B
0x331c  ldarg.0
0x331d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Reconfigure>d__44::<>u__1
0x3322  stloc.2
0x3323  ldarg.0
0x3324  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Reconfigure>d__44::<>u__1
0x3329  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x332f  ldarg.0
0x3330  ldc.i4.m1
0x3331  dup
0x3332  stloc.0
0x3333  stfld    int32 <Reconfigure>d__44::<>1__state
0x3338  ldloca.s 2
0x333a  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x333f  leave.s  loc_3358
0x3341  stloc.3
0x3342  ldarg.0
0x3343  ldc.i4.s 0xFE
0x3345  stfld    int32 <Reconfigure>d__44::<>1__state
0x334a  ldarg.0
0x334b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x3350  ldloc.3
0x3351  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x3356  leave.s  loc_336B
0x3358  ldarg.0
0x3359  ldc.i4.s 0xFE
0x335b  stfld    int32 <Reconfigure>d__44::<>1__state
0x3360  ldarg.0
0x3361  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x3366  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x336b  ret
```
