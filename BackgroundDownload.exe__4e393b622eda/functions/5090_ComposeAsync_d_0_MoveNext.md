# <ComposeAsync>d__0::MoveNext

- ea: `0x5090`
- end: `0x517d`
- name: `<ComposeAsync>d__0::MoveNext`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1c50`
- `0x2170`
- `0x2320`
- `0x23a0`
- `0x5090`

## pseudocode

```c

```

## disassembly

```asm
0x5090  ldarg.0
0x5091  ldfld    int32 <ComposeAsync>d__0::<>1__state
0x5096  stloc.0
0x5097  ldloc.0
0x5098  brfalse.s loc_5117
0x509a  ldarg.0
0x509b  ldnull
0x509c  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider::.ctor(class [mscorlib]System.IServiceProvider)
0x50a1  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x50a6  ldarg.0
0x50a7  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x50ac  ldarg.0
0x50ad  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <ComposeAsync>d__0::commandLine
0x50b2  call     void Microsoft.VisualStudio.Setup.CompositionRoot::AddDefaultServices(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x50b7  ldarg.0
0x50b8  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <ComposeAsync>d__0::commandLine
0x50bd  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsUpdateCheckOnly()
0x50c2  brfalse.s loc_50D7
0x50c4  ldarg.0
0x50c5  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x50ca  ldarg.0
0x50cb  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <ComposeAsync>d__0::commandLine
0x50d0  call     void Microsoft.VisualStudio.Setup.CompositionRoot::AddUpdateCheckServices(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x50d5  br.s     loc_513A
0x50d7  ldarg.0
0x50d8  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x50dd  ldarg.0
0x50de  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <ComposeAsync>d__0::commandLine
0x50e3  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadServicesAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x50e8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x50ed  stloc.2
0x50ee  ldloca.s 2
0x50f0  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x50f5  brtrue.s loc_5133
0x50f7  ldarg.0
0x50f8  ldc.i4.0
0x50f9  dup
0x50fa  stloc.0
0x50fb  stfld    int32 <ComposeAsync>d__0::<>1__state
0x5100  ldarg.0
0x5101  ldloc.2
0x5102  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ComposeAsync>d__0::<>u__1
0x5107  ldarg.0
0x5108  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x510d  ldloca.s 2
0x510f  ldarg.0
0x5110  call     T0x2B00005E
0x5115  leave.s  loc_517C
0x5117  ldarg.0
0x5118  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ComposeAsync>d__0::<>u__1
0x511d  stloc.2
0x511e  ldarg.0
0x511f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ComposeAsync>d__0::<>u__1
0x5124  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x512a  ldarg.0
0x512b  ldc.i4.m1
0x512c  dup
0x512d  stloc.0
0x512e  stfld    int32 <ComposeAsync>d__0::<>1__state
0x5133  ldloca.s 2
0x5135  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x513a  ldarg.0
0x513b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x5140  stloc.1
0x5141  leave.s  loc_5161
0x5143  stloc.3
0x5144  ldarg.0
0x5145  ldc.i4.s 0xFE
0x5147  stfld    int32 <ComposeAsync>d__0::<>1__state
0x514c  ldarg.0
0x514d  ldnull
0x514e  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x5153  ldarg.0
0x5154  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x5159  ldloc.3
0x515a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::SetException(class [mscorlib]System.Exception)
0x515f  leave.s  loc_517C
0x5161  ldarg.0
0x5162  ldc.i4.s 0xFE
0x5164  stfld    int32 <ComposeAsync>d__0::<>1__state
0x5169  ldarg.0
0x516a  ldnull
0x516b  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <ComposeAsync>d__0::<services>5__2
0x5170  ldarg.0
0x5171  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer> <ComposeAsync>d__0::<>t__builder
0x5176  ldloc.1
0x5177  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer>::SetResult(var<u1>)
0x517c  ret
```
