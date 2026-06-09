# <GetSystemState>d__52::MoveNext

- ea: `0x3890`
- end: `0x394e`
- name: `<GetSystemState>d__52::MoveNext`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x3890`

## pseudocode

```c

```

## disassembly

```asm
0x3890  ldarg.0
0x3891  ldfld    int32 <GetSystemState>d__52::<>1__state
0x3896  stloc.0
0x3897  ldarg.0
0x3898  ldfld    class Microsoft.BIServer.BIService.BIService <GetSystemState>d__52::<>4__this
0x389d  stloc.1
0x389e  ldloc.0
0x389f  pop
0x38a0  nop
0x38a1  ldloc.0
0x38a2  brfalse.s loc_38F1
0x38a4  ldloc.1
0x38a5  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::_managementStateAccessor
0x38aa  brtrue.s loc_38B7
0x38ac  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_Pending()
0x38b1  stloc.2
0x38b2  leave    loc_3939
0x38b7  ldloc.1
0x38b8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::_managementStateAccessor
0x38bd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::Execute()
0x38c2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x38c7  stloc.3
0x38c8  ldloca.s 3
0x38ca  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x38cf  brtrue.s loc_390D
0x38d1  ldarg.0
0x38d2  ldc.i4.0
0x38d3  dup
0x38d4  stloc.0
0x38d5  stfld    int32 <GetSystemState>d__52::<>1__state
0x38da  ldarg.0
0x38db  ldloc.3
0x38dc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>u__1
0x38e1  ldarg.0
0x38e2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x38e7  ldloca.s 3
0x38e9  ldarg.0
0x38ea  call     T0x2B000026
0x38ef  leave.s  loc_394D
0x38f1  ldarg.0
0x38f2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>u__1
0x38f7  stloc.3
0x38f8  ldarg.0
0x38f9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>u__1
0x38fe  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x3904  ldarg.0
0x3905  ldc.i4.m1
0x3906  dup
0x3907  stloc.0
0x3908  stfld    int32 <GetSystemState>d__52::<>1__state
0x390d  ldloca.s 3
0x390f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x3914  stloc.2
0x3915  leave.s  loc_3939
0x3917  pop
0x3918  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_Pending()
0x391d  stloc.2
0x391e  leave.s  loc_3939
0x3920  stloc.s  4
0x3922  ldarg.0
0x3923  ldc.i4.s 0xFE
0x3925  stfld    int32 <GetSystemState>d__52::<>1__state
0x392a  ldarg.0
0x392b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x3930  ldloc.s  4
0x3932  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetException(class [mscorlib]System.Exception)
0x3937  leave.s  loc_394D
0x3939  ldarg.0
0x393a  ldc.i4.s 0xFE
0x393c  stfld    int32 <GetSystemState>d__52::<>1__state
0x3941  ldarg.0
0x3942  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x3947  ldloc.2
0x3948  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetResult(var<u1>)
0x394d  ret
```
