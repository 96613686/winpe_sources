# <HandleStatusChanges>d__31::MoveNext

- ea: `0x3030`
- end: `0x30eb`
- name: `<HandleStatusChanges>d__31::MoveNext`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xca0`
- `0xda0`
- `0xdd0`
- `0xdf0`
- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0x3030  ldarg.0
0x3031  ldfld    int32 <HandleStatusChanges>d__31::<>1__state
0x3036  stloc.0
0x3037  ldarg.0
0x3038  ldfld    class Microsoft.BIServer.BIService.BIService <HandleStatusChanges>d__31::<>4__this
0x303d  stloc.1
0x303e  ldloc.0
0x303f  brfalse.s loc_304E
0x3041  ldloc.1
0x3042  call     instance bool Microsoft.BIServer.BIService.BIService::IsTimeForConfigRead()
0x3047  brtrue.s loc_304E
0x3049  leave    loc_30D7
0x304e  nop
0x304f  ldloc.0
0x3050  brfalse.s loc_3087
0x3052  ldloc.1
0x3053  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::TryUpdateServiceConfigAndRestartProcesses()
0x3058  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x305d  stloc.2
0x305e  ldloca.s 2
0x3060  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x3065  brtrue.s loc_30A3
0x3067  ldarg.0
0x3068  ldc.i4.0
0x3069  dup
0x306a  stloc.0
0x306b  stfld    int32 <HandleStatusChanges>d__31::<>1__state
0x3070  ldarg.0
0x3071  ldloc.2
0x3072  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleStatusChanges>d__31::<>u__1
0x3077  ldarg.0
0x3078  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0x307d  ldloca.s 2
0x307f  ldarg.0
0x3080  call     T0x2B00001F
0x3085  leave.s  loc_30EA
0x3087  ldarg.0
0x3088  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleStatusChanges>d__31::<>u__1
0x308d  stloc.2
0x308e  ldarg.0
0x308f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleStatusChanges>d__31::<>u__1
0x3094  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x309a  ldarg.0
0x309b  ldc.i4.m1
0x309c  dup
0x309d  stloc.0
0x309e  stfld    int32 <HandleStatusChanges>d__31::<>1__state
0x30a3  ldloca.s 2
0x30a5  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x30aa  ldloc.1
0x30ab  call     instance void Microsoft.BIServer.BIService.BIService::ResetReadConfigAttempt()
0x30b0  leave.s  loc_30BC
0x30b2  stloc.3
0x30b3  ldloc.1
0x30b4  ldloc.3
0x30b5  call     instance void Microsoft.BIServer.BIService.BIService::HandleServiceConfigUpdateFailure(class [mscorlib]System.Exception e)
0x30ba  leave.s  loc_30BC
0x30bc  leave.s  loc_30D7
0x30be  stloc.s  4
0x30c0  ldarg.0
0x30c1  ldc.i4.s 0xFE
0x30c3  stfld    int32 <HandleStatusChanges>d__31::<>1__state
0x30c8  ldarg.0
0x30c9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0x30ce  ldloc.s  4
0x30d0  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x30d5  leave.s  loc_30EA
0x30d7  ldarg.0
0x30d8  ldc.i4.s 0xFE
0x30da  stfld    int32 <HandleStatusChanges>d__31::<>1__state
0x30df  ldarg.0
0x30e0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0x30e5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x30ea  ret
```
