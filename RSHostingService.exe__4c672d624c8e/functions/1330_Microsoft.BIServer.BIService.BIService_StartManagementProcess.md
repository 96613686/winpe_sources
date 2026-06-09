# Microsoft.BIServer.BIService.BIService::StartManagementProcess

- ea: `0x1330`
- end: `0x1369`
- name: `Microsoft.BIServer.BIService.BIService::StartManagementProcess`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x1330  ldloca.s 0
0x1332  ldarg.0
0x1333  stfld    class Microsoft.BIServer.BIService.BIService <StartManagementProcess>d__50::<>4__this
0x1338  ldloca.s 0
0x133a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::Create()
0x133f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x1344  ldloca.s 0
0x1346  ldc.i4.m1
0x1347  stfld    int32 <StartManagementProcess>d__50::<>1__state
0x134c  ldloc.0
0x134d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x1352  stloc.1
0x1353  ldloca.s 1
0x1355  ldloca.s 0
0x1357  call     T0x2B000011
0x135c  ldloca.s 0
0x135e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <StartManagementProcess>d__50::<>t__builder
0x1363  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_Task()
0x1368  ret
```
