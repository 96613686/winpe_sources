# <StartManagementProcess>d__50::MoveNext

- ea: `0x35f0`
- end: `0x36b7`
- name: `<StartManagementProcess>d__50::MoveNext`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1370`
- `0x1f10`
- `0x35f0`

## string_xrefs

- `0x3609`: `No management process configured in {0}`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  ldarg.0
0x35f1  ldfld    int32 <StartManagementProcess>d__50::<>1__state
0x35f6  stloc.0
0x35f7  ldarg.0
0x35f8  ldfld    class Microsoft.BIServer.BIService.BIService <StartManagementProcess>d__50::<>4__this
0x35fd  stloc.1
0x35fe  ldloc.0
0x35ff  brfalse.s loc_3663
0x3601  ldloc.1
0x3602  ldfld    class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.BIService::_managementProcess
0x3607  brtrue.s loc_3623
0x3609  ldstr    aNoManagementPr// "No management process configured in {0}"
0x360e  ldc.i4.1
0x360f  newarr   [mscorlib]System.Object
0x3614  dup
0x3615  ldc.i4.0
0x3616  ldloc.1
0x3617  ldfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0x361c  stelem.ref
0x361d  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Exceptions.HostingEnvironmentException::.ctor(string, object[])
0x3622  throw
0x3623  ldloc.1
0x3624  ldfld    class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.BIService::_managementProcess
0x3629  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::Start()
0x362e  ldloc.1
0x362f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::WaitForDbStatus()
0x3634  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x3639  stloc.3
0x363a  ldloca.s 3
0x363c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x3641  brtrue.s loc_367F
0x3643  ldarg.0
0x3644  ldc.i4.0
0x3645  dup
0x3646  stloc.0
0x3647  stfld    int32 <StartManagementProcess>d__50::<>1__state
0x364c  ldarg.0
0x364d  ldloc.3
0x364e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>u__1
0x3653  ldarg.0
0x3654  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x3659  ldloca.s 3
0x365b  ldarg.0
0x365c  call     T0x2B000023
0x3661  leave.s  loc_36B6
0x3663  ldarg.0
0x3664  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>u__1
0x3669  stloc.3
0x366a  ldarg.0
0x366b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>u__1
0x3670  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x3676  ldarg.0
0x3677  ldc.i4.m1
0x3678  dup
0x3679  stloc.0
0x367a  stfld    int32 <StartManagementProcess>d__50::<>1__state
0x367f  ldloca.s 3
0x3681  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x3686  stloc.2
0x3687  leave.s  loc_36A2
0x3689  stloc.s  4
0x368b  ldarg.0
0x368c  ldc.i4.s 0xFE
0x368e  stfld    int32 <StartManagementProcess>d__50::<>1__state
0x3693  ldarg.0
0x3694  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x3699  ldloc.s  4
0x369b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetException(class [mscorlib]System.Exception)
0x36a0  leave.s  loc_36B6
0x36a2  ldarg.0
0x36a3  ldc.i4.s 0xFE
0x36a5  stfld    int32 <StartManagementProcess>d__50::<>1__state
0x36aa  ldarg.0
0x36ab  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x36b0  ldloc.2
0x36b1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetResult(var<u1>)
0x36b6  ret
```
