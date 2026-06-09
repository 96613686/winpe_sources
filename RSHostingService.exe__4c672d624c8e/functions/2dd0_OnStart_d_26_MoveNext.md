# <OnStart>d__26::MoveNext

- ea: `0x2dd0`
- end: `0x2e7d`
- name: `<OnStart>d__26::MoveNext`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xb80`
- `0xbb0`
- `0x1040`
- `0x1800`
- `0x2dd0`

## pseudocode

```c

```

## disassembly

```asm
0x2dd0  ldarg.0
0x2dd1  ldfld    int32 <OnStart>d__26::<>1__state
0x2dd6  stloc.0
0x2dd7  ldarg.0
0x2dd8  ldfld    class Microsoft.BIServer.BIService.BIService <OnStart>d__26::<>4__this
0x2ddd  stloc.1
0x2dde  ldloc.0
0x2ddf  brfalse.s loc_2E1C
0x2de1  ldloc.1
0x2de2  call     instance void Microsoft.BIServer.BIService.BIService::UpdateServiceConfigs()
0x2de7  ldloc.1
0x2de8  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::Reconfigure()
0x2ded  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2df2  stloc.2
0x2df3  ldloca.s 2
0x2df5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x2dfa  brtrue.s loc_2E38
0x2dfc  ldarg.0
0x2dfd  ldc.i4.0
0x2dfe  dup
0x2dff  stloc.0
0x2e00  stfld    int32 <OnStart>d__26::<>1__state
0x2e05  ldarg.0
0x2e06  ldloc.2
0x2e07  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <OnStart>d__26::<>u__1
0x2e0c  ldarg.0
0x2e0d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <OnStart>d__26::<>t__builder
0x2e12  ldloca.s 2
0x2e14  ldarg.0
0x2e15  call     T0x2B00001D
0x2e1a  leave.s  loc_2E7C
0x2e1c  ldarg.0
0x2e1d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <OnStart>d__26::<>u__1
0x2e22  stloc.2
0x2e23  ldarg.0
0x2e24  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <OnStart>d__26::<>u__1
0x2e29  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x2e2f  ldarg.0
0x2e30  ldc.i4.m1
0x2e31  dup
0x2e32  stloc.0
0x2e33  stfld    int32 <OnStart>d__26::<>1__state
0x2e38  ldloca.s 2
0x2e3a  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x2e3f  ldloc.1
0x2e40  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0x2e45  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StartWorkerProcesses()
0x2e4a  ldloc.1
0x2e4b  call     instance void Microsoft.BIServer.BIService.BIService::StartServiceWatchdog()
0x2e50  leave.s  loc_2E69
0x2e52  stloc.3
0x2e53  ldarg.0
0x2e54  ldc.i4.s 0xFE
0x2e56  stfld    int32 <OnStart>d__26::<>1__state
0x2e5b  ldarg.0
0x2e5c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <OnStart>d__26::<>t__builder
0x2e61  ldloc.3
0x2e62  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetException(class [mscorlib]System.Exception)
0x2e67  leave.s  loc_2E7C
0x2e69  ldarg.0
0x2e6a  ldc.i4.s 0xFE
0x2e6c  stfld    int32 <OnStart>d__26::<>1__state
0x2e71  ldarg.0
0x2e72  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <OnStart>d__26::<>t__builder
0x2e77  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetResult()
0x2e7c  ret
```
