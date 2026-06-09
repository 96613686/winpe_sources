# <ThrottledStart>d__20::MoveNext

- ea: `0x3a90`
- end: `0x3b8a`
- name: `<ThrottledStart>d__20::MoveNext`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1bd0`
- `0x1f10`
- `0x20d0`
- `0x3a90`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  ldarg.0
0x3a91  ldfld    int32 <ThrottledStart>d__20::<>1__state
0x3a96  stloc.0
0x3a97  ldarg.0
0x3a98  ldfld    class Microsoft.BIServer.BIService.ManagedProcess <ThrottledStart>d__20::<>4__this
0x3a9d  stloc.1
0x3a9e  ldloc.0
0x3a9f  brfalse.s loc_3ADE
0x3aa1  ldloc.1
0x3aa2  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff Microsoft.BIServer.BIService.ManagedProcess::_exponentialBackoff
0x3aa7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<float64> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::BackoffAsync()
0x3aac  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<float64>::GetAwaiter()
0x3ab1  stloc.3
0x3ab2  ldloca.s 3
0x3ab4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>::get_IsCompleted()
0x3ab9  brtrue.s loc_3AFA
0x3abb  ldarg.0
0x3abc  ldc.i4.0
0x3abd  dup
0x3abe  stloc.0
0x3abf  stfld    int32 <ThrottledStart>d__20::<>1__state
0x3ac4  ldarg.0
0x3ac5  ldloc.3
0x3ac6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <ThrottledStart>d__20::<>u__1
0x3acb  ldarg.0
0x3acc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <ThrottledStart>d__20::<>t__builder
0x3ad1  ldloca.s 3
0x3ad3  ldarg.0
0x3ad4  call     T0x2B000028
0x3ad9  leave    loc_3B89
0x3ade  ldarg.0
0x3adf  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <ThrottledStart>d__20::<>u__1
0x3ae4  stloc.3
0x3ae5  ldarg.0
0x3ae6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64> <ThrottledStart>d__20::<>u__1
0x3aeb  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>
0x3af1  ldarg.0
0x3af2  ldc.i4.m1
0x3af3  dup
0x3af4  stloc.0
0x3af5  stfld    int32 <ThrottledStart>d__20::<>1__state
0x3afa  ldloca.s 3
0x3afc  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<float64>::GetResult()
0x3b01  stloc.2
0x3b02  ldloc.2
0x3b03  ldc.r8   0.0
0x3b0c  ble.un.s loc_3B37
0x3b0e  ldstr    aThrottledResta// "Throttled restart of process by {0:#,##"...
0x3b13  ldc.i4.2
0x3b14  newarr   [mscorlib]System.Object
0x3b19  dup
0x3b1a  ldc.i4.0
0x3b1b  ldloc.2
0x3b1c  box      [mscorlib]System.Double
0x3b21  stelem.ref
0x3b22  dup
0x3b23  ldc.i4.1
0x3b24  ldloc.1
0x3b25  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x3b2a  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x3b2f  stelem.ref
0x3b30  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3b35  br.s     loc_3B55
0x3b37  ldstr    aImmediateResta// "Immediate restart of process {0}"
0x3b3c  ldc.i4.1
0x3b3d  newarr   [mscorlib]System.Object
0x3b42  dup
0x3b43  ldc.i4.0
0x3b44  ldloc.1
0x3b45  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x3b4a  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x3b4f  stelem.ref
0x3b50  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3b55  ldloc.1
0x3b56  call     instance void Microsoft.BIServer.BIService.ManagedProcess::Start()
0x3b5b  leave.s  loc_3B76
0x3b5d  stloc.s  4
0x3b5f  ldarg.0
0x3b60  ldc.i4.s 0xFE
0x3b62  stfld    int32 <ThrottledStart>d__20::<>1__state
0x3b67  ldarg.0
0x3b68  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <ThrottledStart>d__20::<>t__builder
0x3b6d  ldloc.s  4
0x3b6f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetException(class [mscorlib]System.Exception)
0x3b74  leave.s  loc_3B89
0x3b76  ldarg.0
0x3b77  ldc.i4.s 0xFE
0x3b79  stfld    int32 <ThrottledStart>d__20::<>1__state
0x3b7e  ldarg.0
0x3b7f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <ThrottledStart>d__20::<>t__builder
0x3b84  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetResult()
0x3b89  ret
```
