# Microsoft.BIServer.BIService.BIService::WaitForDbStatus

- ea: `0x1370`
- end: `0x13a9`
- name: `Microsoft.BIServer.BIService.BIService::WaitForDbStatus`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x35f0`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldloca.s 0
0x1372  ldarg.0
0x1373  stfld    class Microsoft.BIServer.BIService.BIService <WaitForDbStatus>d__51::<>4__this
0x1378  ldloca.s 0
0x137a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::Create()
0x137f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x1384  ldloca.s 0
0x1386  ldc.i4.m1
0x1387  stfld    int32 <WaitForDbStatus>d__51::<>1__state
0x138c  ldloc.0
0x138d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x1392  stloc.1
0x1393  ldloca.s 1
0x1395  ldloca.s 0
0x1397  call     T0x2B000012
0x139c  ldloca.s 0
0x139e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <WaitForDbStatus>d__51::<>t__builder
0x13a3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_Task()
0x13a8  ret
```
