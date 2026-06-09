# <Main>d__0::MoveNext

- ea: `0x5380`
- end: `0x550a`
- name: `<Main>d__0::MoveNext`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1df0`
- `0x1fb0`
- `0x2130`
- `0x2520`
- `0x37a0`
- `0x5380`

## pseudocode

```c

```

## disassembly

```asm
0x5380  ldarg.0
0x5381  ldfld    int32 <Main>d__0::<>1__state
0x5386  stloc.0
0x5387  ldloc.0
0x5388  ldc.i4.1
0x5389  pop
0x538a  pop
0x538b  nop
0x538c  ldloc.0
0x538d  brfalse.s loc_53DE
0x538f  ldloc.0
0x5390  ldc.i4.1
0x5391  beq.s    loc_540A
0x5393  newobj   instance void Microsoft.VisualStudio.Setup.CommandLine::.ctor()
0x5398  dup
0x5399  ldarg.0
0x539a  ldfld    string[] <Main>d__0::args
0x539f  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::ParseCommandLine(class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> args)
0x53a4  pop
0x53a5  call     class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> Microsoft.VisualStudio.Setup.CompositionRoot::ComposeAsync(class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x53aa  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::GetAwaiter()
0x53af  stloc.s  4
0x53b1  ldloca.s 4
0x53b3  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::get_IsCompleted()
0x53b8  brtrue.s loc_53FB
0x53ba  ldarg.0
0x53bb  ldc.i4.0
0x53bc  dup
0x53bd  stloc.0
0x53be  stfld    int32 <Main>d__0::<>1__state
0x53c3  ldarg.0
0x53c4  ldloc.s  4
0x53c6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <Main>d__0::<>u__1
0x53cb  ldarg.0
0x53cc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <Main>d__0::<>t__builder
0x53d1  ldloca.s 4
0x53d3  ldarg.0
0x53d4  call     T0x2B000061
0x53d9  leave    loc_5509
0x53de  ldarg.0
0x53df  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <Main>d__0::<>u__1
0x53e4  stloc.s  4
0x53e6  ldarg.0
0x53e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <Main>d__0::<>u__1
0x53ec  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>
0x53f2  ldarg.0
0x53f3  ldc.i4.m1
0x53f4  dup
0x53f5  stloc.0
0x53f6  stfld    int32 <Main>d__0::<>1__state
0x53fb  ldloca.s 4
0x53fd  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::GetResult()
0x5402  stloc.3
0x5403  ldarg.0
0x5404  ldloc.3
0x5405  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer <Main>d__0::<services>5__2
0x540a  nop
0x540b  ldloc.0
0x540c  ldc.i4.1
0x540d  beq.s    loc_542E
0x540f  ldarg.0
0x5410  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer <Main>d__0::<services>5__2
0x5415  ldc.i4.1
0x5416  call     T0x2B000062
0x541b  stloc.2
0x541c  ldarg.0
0x541d  ldarg.0
0x541e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer <Main>d__0::<services>5__2
0x5423  ldc.i4.1
0x5424  call     T0x2B000063
0x5429  stfld    class Microsoft.VisualStudio.Setup.IBackgroundDownloadJob <Main>d__0::<job>5__3
0x542e  nop
0x542f  ldloc.0
0x5430  ldc.i4.1
0x5431  beq.s    loc_5478
0x5433  ldarg.0
0x5434  ldfld    class Microsoft.VisualStudio.Setup.IBackgroundDownloadJob <Main>d__0::<job>5__3
0x5439  ldloc.2
0x543a  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.VisualStudio.Setup.Services.ICancellationService::get_CancellationToken()
0x543f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.VisualStudio.Setup.IBackgroundDownloadJob::RunAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x5444  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x5449  stloc.s  5
0x544b  ldloca.s 5
0x544d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x5452  brtrue.s loc_5495
0x5454  ldarg.0
0x5455  ldc.i4.1
0x5456  dup
0x5457  stloc.0
0x5458  stfld    int32 <Main>d__0::<>1__state
0x545d  ldarg.0
0x545e  ldloc.s  5
0x5460  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <Main>d__0::<>u__2
0x5465  ldarg.0
0x5466  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <Main>d__0::<>t__builder
0x546b  ldloca.s 5
0x546d  ldarg.0
0x546e  call     T0x2B000064
0x5473  leave    loc_5509
0x5478  ldarg.0
0x5479  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <Main>d__0::<>u__2
0x547e  stloc.s  5
0x5480  ldarg.0
0x5481  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <Main>d__0::<>u__2
0x5486  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x548c  ldarg.0
0x548d  ldc.i4.m1
0x548e  dup
0x548f  stloc.0
0x5490  stfld    int32 <Main>d__0::<>1__state
0x5495  ldloca.s 5
0x5497  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x549c  stloc.1
0x549d  leave.s  loc_54F5
0x549f  ldloc.0
0x54a0  ldc.i4.0
0x54a1  bge.s    loc_54B6
0x54a3  ldarg.0
0x54a4  ldfld    class Microsoft.VisualStudio.Setup.IBackgroundDownloadJob <Main>d__0::<job>5__3
0x54a9  brfalse.s loc_54B6
0x54ab  ldarg.0
0x54ac  ldfld    class Microsoft.VisualStudio.Setup.IBackgroundDownloadJob <Main>d__0::<job>5__3
0x54b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54b6  endfinally
0x54b7  ldloc.0
0x54b8  ldc.i4.0
0x54b9  bge.s    loc_54CE
0x54bb  ldarg.0
0x54bc  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer <Main>d__0::<services>5__2
0x54c1  brfalse.s loc_54CE
0x54c3  ldarg.0
0x54c4  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer <Main>d__0::<services>5__2
0x54c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54ce  endfinally
0x54cf  pop
0x54d0  ldc.i4.0
0x54d1  stloc.1
0x54d2  leave.s  loc_54F5
0x54d4  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x54d9  stloc.1
0x54da  leave.s  loc_54F5
0x54dc  stloc.s  6
0x54de  ldarg.0
0x54df  ldc.i4.s 0xFE
0x54e1  stfld    int32 <Main>d__0::<>1__state
0x54e6  ldarg.0
0x54e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <Main>d__0::<>t__builder
0x54ec  ldloc.s  6
0x54ee  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x54f3  leave.s  loc_5509
0x54f5  ldarg.0
0x54f6  ldc.i4.s 0xFE
0x54f8  stfld    int32 <Main>d__0::<>1__state
0x54fd  ldarg.0
0x54fe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <Main>d__0::<>t__builder
0x5503  ldloc.1
0x5504  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x5509  ret
```
