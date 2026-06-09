# Microsoft.BIServer.BIService.BIService::GetSystemState

- ea: `0x13b0`
- end: `0x13e9`
- name: `Microsoft.BIServer.BIService.BIService::GetSystemState`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3110`
- `0x36e0`

## pseudocode

```c

```

## disassembly

```asm
0x13b0  ldloca.s 0
0x13b2  ldarg.0
0x13b3  stfld    class Microsoft.BIServer.BIService.BIService <GetSystemState>d__52::<>4__this
0x13b8  ldloca.s 0
0x13ba  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::Create()
0x13bf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x13c4  ldloca.s 0
0x13c6  ldc.i4.m1
0x13c7  stfld    int32 <GetSystemState>d__52::<>1__state
0x13cc  ldloc.0
0x13cd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x13d2  stloc.1
0x13d3  ldloca.s 1
0x13d5  ldloca.s 0
0x13d7  call     T0x2B000013
0x13dc  ldloca.s 0
0x13de  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetSystemState>d__52::<>t__builder
0x13e3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_Task()
0x13e8  ret
```
