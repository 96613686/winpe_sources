# <WaitForDbStatus>d__51::MoveNext

- ea: `0x36e0`
- end: `0x3862`
- name: `<WaitForDbStatus>d__51::MoveNext`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x13b0`
- `0x36e0`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  ldarg.0
0x36e1  ldfld    int32 <WaitForDbStatus>d__51::<>1__state
0x36e6  stloc.0
0x36e7  ldarg.0
0x36e8  ldfld    class Microsoft.BIServer.BIService.BIService <WaitForDbStatus>d__51::<>4__this
0x36ed  stloc.1
0x36ee  ldloc.0
0x36ef  switch   loc_373A, loc_37A3, loc_37FF
0x3700  ldloc.1
0x3701  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::GetSystemState()
0x3706  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x370b  stloc.s  4
0x370d  ldloca.s 4
0x370f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x3714  brtrue.s loc_3757
0x3716  ldarg.0
0x3717  ldc.i4.0
0x3718  dup
0x3719  stloc.0
0x371a  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x371f  ldarg.0
0x3720  ldloc.s  4
0x3722  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x3727  ldarg.0
0x3728  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x372d  ldloca.s 4
0x372f  ldarg.0
0x3730  call     T0x2B000024
0x3735  leave    loc_3861
0x373a  ldarg.0
0x373b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x3740  stloc.s  4
0x3742  ldarg.0
0x3743  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x3748  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x374e  ldarg.0
0x374f  ldc.i4.m1
0x3750  dup
0x3751  stloc.0
0x3752  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x3757  ldloca.s 4
0x3759  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x375e  stloc.3
0x375f  br       loc_3824
0x3764  ldloc.1
0x3765  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff Microsoft.BIServer.BIService.BIService::_managementBackoff
0x376a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<float64> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::BackoffAsync()
0x376f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<float64>::GetAwaiter()
0x3774  stloc.s  5
0x3776  ldloca.s 5
0x3778  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>::get_IsCompleted()
0x377d  brtrue.s loc_37C0
0x377f  ldarg.0
0x3780  ldc.i4.1
0x3781  dup
0x3782  stloc.0
0x3783  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x3788  ldarg.0
0x3789  ldloc.s  5
0x378b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <WaitForDbStatus>d__51::<>u__2
0x3790  ldarg.0
0x3791  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x3796  ldloca.s 5
0x3798  ldarg.0
0x3799  call     T0x2B000025
0x379e  leave    loc_3861
0x37a3  ldarg.0
0x37a4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <WaitForDbStatus>d__51::<>u__2
0x37a9  stloc.s  5
0x37ab  ldarg.0
0x37ac  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <WaitForDbStatus>d__51::<>u__2
0x37b1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>
0x37b7  ldarg.0
0x37b8  ldc.i4.m1
0x37b9  dup
0x37ba  stloc.0
0x37bb  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x37c0  ldloca.s 5
0x37c2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>::GetResult()
0x37c7  pop
0x37c8  ldloc.1
0x37c9  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::GetSystemState()
0x37ce  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x37d3  stloc.s  4
0x37d5  ldloca.s 4
0x37d7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x37dc  brtrue.s loc_381C
0x37de  ldarg.0
0x37df  ldc.i4.2
0x37e0  dup
0x37e1  stloc.0
0x37e2  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x37e7  ldarg.0
0x37e8  ldloc.s  4
0x37ea  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x37ef  ldarg.0
0x37f0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x37f5  ldloca.s 4
0x37f7  ldarg.0
0x37f8  call     T0x2B000024
0x37fd  leave.s  loc_3861
0x37ff  ldarg.0
0x3800  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x3805  stloc.s  4
0x3807  ldarg.0
0x3808  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>u__1
0x380d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x3813  ldarg.0
0x3814  ldc.i4.m1
0x3815  dup
0x3816  stloc.0
0x3817  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x381c  ldloca.s 4
0x381e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x3823  stloc.3
0x3824  ldloc.3
0x3825  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_DatabaseValidationStatus()
0x382a  ldc.i4.1
0x382b  beq      loc_3764
0x3830  ldloc.3
0x3831  stloc.2
0x3832  leave.s  loc_384D
0x3834  stloc.s  6
0x3836  ldarg.0
0x3837  ldc.i4.s 0xFE
0x3839  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x383e  ldarg.0
0x383f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x3844  ldloc.s  6
0x3846  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetException(class [mscorlib]System.Exception)
0x384b  leave.s  loc_3861
0x384d  ldarg.0
0x384e  ldc.i4.s 0xFE
0x3850  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x3855  ldarg.0
0x3856  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x385b  ldloc.2
0x385c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetResult(var<u1>)
0x3861  ret
```
