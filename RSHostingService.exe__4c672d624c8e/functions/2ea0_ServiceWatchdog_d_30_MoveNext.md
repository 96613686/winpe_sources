# <ServiceWatchdog>d__30::MoveNext

- ea: `0x2ea0`
- end: `0x3010`
- name: `<ServiceWatchdog>d__30::MoveNext`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0xc60`
- `0x1010`
- `0x1030`
- `0x2ea0`

## string_xrefs

- `0x2ebd`: `Service watchdog: starting`
- `0x2fb3`: `Service watchdog: Exception. `
- `0x2fd4`: `Service watchdog: stopping`

## pseudocode

```c

```

## disassembly

```asm
0x2ea0  ldarg.0
0x2ea1  ldfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2ea6  stloc.0
0x2ea7  ldarg.0
0x2ea8  ldfld    class Microsoft.BIServer.BIService.BIService <ServiceWatchdog>d__30::<>4__this
0x2ead  stloc.1
0x2eae  ldloc.0
0x2eaf  ldc.i4.1
0x2eb0  ble.un.s loc_2ED1
0x2eb2  ldarg.0
0x2eb3  call     class Microsoft.BIServer.RSHostingService.RsTraceConfig Microsoft.BIServer.BIService.BIService::LoadConfig()
0x2eb8  stfld    class Microsoft.BIServer.RSHostingService.RsTraceConfig <ServiceWatchdog>d__30::<rsTraceConfig>5__2
0x2ebd  ldstr    aServiceWatchdo// "Service watchdog: starting"
0x2ec2  call     T0x2B000001
0x2ec7  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2ecc  br       loc_2FC4
0x2ed1  nop
0x2ed2  ldloc.0
0x2ed3  brfalse.s loc_2F14
0x2ed5  ldloc.0
0x2ed6  ldc.i4.1
0x2ed7  beq      loc_2F8B
0x2edc  ldloc.1
0x2edd  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::HandleStatusChanges()
0x2ee2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2ee7  stloc.2
0x2ee8  ldloca.s 2
0x2eea  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x2eef  brtrue.s loc_2F30
0x2ef1  ldarg.0
0x2ef2  ldc.i4.0
0x2ef3  dup
0x2ef4  stloc.0
0x2ef5  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2efa  ldarg.0
0x2efb  ldloc.2
0x2efc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f01  ldarg.0
0x2f02  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0x2f07  ldloca.s 2
0x2f09  ldarg.0
0x2f0a  call     T0x2B00001E
0x2f0f  leave    loc_300F
0x2f14  ldarg.0
0x2f15  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f1a  stloc.2
0x2f1b  ldarg.0
0x2f1c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f21  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x2f27  ldarg.0
0x2f28  ldc.i4.m1
0x2f29  dup
0x2f2a  stloc.0
0x2f2b  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2f30  ldloca.s 2
0x2f32  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x2f37  ldloc.1
0x2f38  ldarg.0
0x2f39  ldfld    class Microsoft.BIServer.RSHostingService.RsTraceConfig <ServiceWatchdog>d__30::<rsTraceConfig>5__2
0x2f3e  call     instance void Microsoft.BIServer.BIService.BIService::CleanupExpiredLogFiles(class Microsoft.BIServer.RSHostingService.RsTraceConfig rsTraceConfig)
0x2f43  ldsfld   int32 Microsoft.BIServer.BIService.BIService::ServiceWatchdogIntervalInSeconds
0x2f48  conv.r8
0x2f49  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x2f4e  ldarg.0
0x2f4f  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ServiceWatchdog>d__30::cancellationToken
0x2f54  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Threading.CancellationToken)
0x2f59  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2f5e  stloc.2
0x2f5f  ldloca.s 2
0x2f61  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x2f66  brtrue.s loc_2FA7
0x2f68  ldarg.0
0x2f69  ldc.i4.1
0x2f6a  dup
0x2f6b  stloc.0
0x2f6c  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2f71  ldarg.0
0x2f72  ldloc.2
0x2f73  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f78  ldarg.0
0x2f79  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0x2f7e  ldloca.s 2
0x2f80  ldarg.0
0x2f81  call     T0x2B00001E
0x2f86  leave    loc_300F
0x2f8b  ldarg.0
0x2f8c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f91  stloc.2
0x2f92  ldarg.0
0x2f93  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ServiceWatchdog>d__30::<>u__1
0x2f98  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x2f9e  ldarg.0
0x2f9f  ldc.i4.m1
0x2fa0  dup
0x2fa1  stloc.0
0x2fa2  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2fa7  ldloca.s 2
0x2fa9  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x2fae  leave.s  loc_2FC4
0x2fb0  pop
0x2fb1  leave.s  loc_2FC4
0x2fb3  ldstr    aServiceWatchdo_0// "Service watchdog: Exception. "
0x2fb8  call     T0x2B000001
0x2fbd  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x2fc2  leave.s  loc_2FC4
0x2fc4  ldarg.0
0x2fc5  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <ServiceWatchdog>d__30::cancellationToken
0x2fca  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x2fcf  brfalse  loc_2ED1
0x2fd4  ldstr    aServiceWatchdo_1// "Service watchdog: stopping"
0x2fd9  call     T0x2B000001
0x2fde  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2fe3  leave.s  loc_2FFC
0x2fe5  stloc.3
0x2fe6  ldarg.0
0x2fe7  ldc.i4.s 0xFE
0x2fe9  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x2fee  ldarg.0
0x2fef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0x2ff4  ldloc.3
0x2ff5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x2ffa  leave.s  loc_300F
0x2ffc  ldarg.0
0x2ffd  ldc.i4.s 0xFE
0x2fff  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0x3004  ldarg.0
0x3005  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0x300a  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x300f  ret
```
