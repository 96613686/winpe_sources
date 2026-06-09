# Microsoft.BIServer.Management.WebApi.Controllers.StateController::ManagementStateInternal

- ea: `0x7c0`
- end: `0x7f9`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::ManagementStateInternal`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb30`
- `0xc50`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  ldloca.s 0
0x7c2  ldarg.0
0x7c3  stfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <ManagementStateInternal>d__3::<>4__this
0x7c8  ldloca.s 0
0x7ca  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::Create()
0x7cf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0x7d4  ldloca.s 0
0x7d6  ldc.i4.m1
0x7d7  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0x7dc  ldloc.0
0x7dd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0x7e2  stloc.1
0x7e3  ldloca.s 1
0x7e5  ldloca.s 0
0x7e7  call     T0x2B000006
0x7ec  ldloca.s 0
0x7ee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0x7f3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_Task()
0x7f8  ret
```
