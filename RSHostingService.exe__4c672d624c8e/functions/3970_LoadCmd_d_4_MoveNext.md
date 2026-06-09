# <LoadCmd>d__4::MoveNext

- ea: `0x3970`
- end: `0x3a6a`
- name: `<LoadCmd>d__4::MoveNext`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0xb10`
- `0x10a0`
- `0x1670`
- `0x3970`

## string_xrefs

- `0x3984`: `Enter Path to config file, or hit enter to reload current:`
- `0x3997`: `Attempting to load config file from [{0}]`
- `0x39b5`: `Load Cancelled: Config file not found at [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x3970  ldarg.0
0x3971  ldfld    int32 <LoadCmd>d__4::<>1__state
0x3976  stloc.0
0x3977  ldarg.0
0x3978  ldfld    class Microsoft.BIServer.BIService.ConsoleDriver <LoadCmd>d__4::<>4__this
0x397d  stloc.1
0x397e  ldloc.0
0x397f  brfalse  loc_3A0E
0x3984  ldstr    aEnterPathToCon// "Enter Path to config file, or hit enter"...
0x3989  call     string Microsoft.BIServer.BIService.ConsoleDriver::GetCommand(string prompt)
0x398e  stloc.2
0x398f  ldloc.2
0x3990  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3995  brfalse.s loc_39CA
0x3997  ldstr    aAttemptingToLo// "Attempting to load config file from [{0"...
0x399c  ldloc.2
0x399d  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x39a2  call     void [mscorlib]System.Console::WriteLine(string, object)
0x39a7  ldloc.1
0x39a8  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x39ad  ldloc.2
0x39ae  callvirt instance bool Microsoft.BIServer.BIService.BIService::SetNewConfigFilePathIfExists(string configFilePath)
0x39b3  brtrue.s loc_39CA
0x39b5  ldstr    aLoadCancelledC// "Load Cancelled: Config file not found a"...
0x39ba  ldloc.2
0x39bb  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x39c0  call     void [mscorlib]System.Console::WriteLine(string, object)
0x39c5  leave    loc_3A56
0x39ca  ldstr    aLoadingHosting// "Loading Hosting State"
0x39cf  call     void [mscorlib]System.Console::WriteLine(string)
0x39d4  ldloc.1
0x39d5  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x39da  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::ReloadHostingState()
0x39df  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x39e4  stloc.3
0x39e5  ldloca.s 3
0x39e7  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x39ec  brtrue.s loc_3A2A
0x39ee  ldarg.0
0x39ef  ldc.i4.0
0x39f0  dup
0x39f1  stloc.0
0x39f2  stfld    int32 <LoadCmd>d__4::<>1__state
0x39f7  ldarg.0
0x39f8  ldloc.3
0x39f9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <LoadCmd>d__4::<>u__1
0x39fe  ldarg.0
0x39ff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <LoadCmd>d__4::<>t__builder
0x3a04  ldloca.s 3
0x3a06  ldarg.0
0x3a07  call     T0x2B000027
0x3a0c  leave.s  loc_3A69
0x3a0e  ldarg.0
0x3a0f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <LoadCmd>d__4::<>u__1
0x3a14  stloc.3
0x3a15  ldarg.0
0x3a16  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <LoadCmd>d__4::<>u__1
0x3a1b  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x3a21  ldarg.0
0x3a22  ldc.i4.m1
0x3a23  dup
0x3a24  stloc.0
0x3a25  stfld    int32 <LoadCmd>d__4::<>1__state
0x3a2a  ldloca.s 3
0x3a2c  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x3a31  ldstr    aFinishedLoadin// "Finished Loading Hosting State"
0x3a36  call     void [mscorlib]System.Console::WriteLine(string)
0x3a3b  leave.s  loc_3A56
0x3a3d  stloc.s  4
0x3a3f  ldarg.0
0x3a40  ldc.i4.s 0xFE
0x3a42  stfld    int32 <LoadCmd>d__4::<>1__state
0x3a47  ldarg.0
0x3a48  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <LoadCmd>d__4::<>t__builder
0x3a4d  ldloc.s  4
0x3a4f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetException(class [mscorlib]System.Exception)
0x3a54  leave.s  loc_3A69
0x3a56  ldarg.0
0x3a57  ldc.i4.s 0xFE
0x3a59  stfld    int32 <LoadCmd>d__4::<>1__state
0x3a5e  ldarg.0
0x3a5f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <LoadCmd>d__4::<>t__builder
0x3a64  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetResult()
0x3a69  ret
```
