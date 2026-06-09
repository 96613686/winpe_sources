# <TryUpdateServiceConfigAndRestartProcesses>d__32::MoveNext

- ea: `0x3110`
- end: `0x31cb`
- name: `<TryUpdateServiceConfigAndRestartProcesses>d__32::MoveNext`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0xce0`
- `0xe50`
- `0xfb0`
- `0x13b0`
- `0x3110`

## pseudocode

```c

```

## disassembly

```asm
0x3110  ldarg.0
0x3111  ldfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0x3116  stloc.0
0x3117  ldarg.0
0x3118  ldfld    class Microsoft.BIServer.BIService.BIService <TryUpdateServiceConfigAndRestartProcesses>d__32::<>4__this
0x311d  stloc.1
0x311e  ldloc.0
0x311f  brfalse.s loc_3158
0x3121  ldloc.1
0x3122  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::GetSystemState()
0x3127  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x312c  stloc.s  5
0x312e  ldloca.s 5
0x3130  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x3135  brtrue.s loc_3175
0x3137  ldarg.0
0x3138  ldc.i4.0
0x3139  dup
0x313a  stloc.0
0x313b  stfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0x3140  ldarg.0
0x3141  ldloc.s  5
0x3143  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <TryUpdateServiceConfigAndRestartProcesses>d__32::<>u__1
0x3148  ldarg.0
0x3149  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0x314e  ldloca.s 5
0x3150  ldarg.0
0x3151  call     T0x2B000020
0x3156  leave.s  loc_31CA
0x3158  ldarg.0
0x3159  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <TryUpdateServiceConfigAndRestartProcesses>d__32::<>u__1
0x315e  stloc.s  5
0x3160  ldarg.0
0x3161  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <TryUpdateServiceConfigAndRestartProcesses>d__32::<>u__1
0x3166  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x316c  ldarg.0
0x316d  ldc.i4.m1
0x316e  dup
0x316f  stloc.0
0x3170  stfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0x3175  ldloca.s 5
0x3177  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x317c  stloc.2
0x317d  ldloc.1
0x317e  ldloc.2
0x317f  call     instance class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::GetLatestServiceConfig(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState currentMananagementState)
0x3184  stloc.3
0x3185  ldloc.3
0x3186  ldloc.1
0x3187  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x318c  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.BIServer.BIService.BIService::GetManagedProcessesToRestart(class Microsoft.BIServer.BIService.ServiceConfig currentServiceConfig, class Microsoft.BIServer.BIService.ServiceConfig previousServiceConfig)
0x3191  stloc.s  4
0x3193  ldloc.1
0x3194  ldloc.s  4
0x3196  ldloc.3
0x3197  call     instance void Microsoft.BIServer.BIService.BIService::UpdateConfigsAndRestartProcesses(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> processesToRestart, class Microsoft.BIServer.BIService.ServiceConfig currentServiceConfig)
0x319c  leave.s  loc_31B7
0x319e  stloc.s  6
0x31a0  ldarg.0
0x31a1  ldc.i4.s 0xFE
0x31a3  stfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0x31a8  ldarg.0
0x31a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0x31ae  ldloc.s  6
0x31b0  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x31b5  leave.s  loc_31CA
0x31b7  ldarg.0
0x31b8  ldc.i4.s 0xFE
0x31ba  stfld    int32 <TryUpdateServiceConfigAndRestartProcesses>d__32::<>1__state
0x31bf  ldarg.0
0x31c0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryUpdateServiceConfigAndRestartProcesses>d__32::<>t__builder
0x31c5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x31ca  ret
```
