# <WaitForConnectionAsync>d__6::MoveNext

- ea: `0x2100`
- end: `0x21e0`
- name: `<WaitForConnectionAsync>d__6::MoveNext`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x2100`

## pseudocode

```c

```

## disassembly

```asm
0x2100  ldarg.0
0x2101  ldfld    int32 <WaitForConnectionAsync>d__6::<>1__state
0x2106  stloc.0
0x2107  ldarg.0
0x2108  ldfld    class Microsoft.VisualStudio.Setup.ServerPipeFacade <WaitForConnectionAsync>d__6::<>4__this
0x210d  stloc.1
0x210e  ldloc.0
0x210f  brfalse.s loc_2190
0x2111  ldloc.1
0x2112  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x2117  callvirt instance bool [System.Core]System.IO.Pipes.PipeStream::get_IsAsync()
0x211c  brtrue.s loc_2129
0x211e  ldstr    aCannotWaitAsyn// "Cannot wait asynchronously for a synchr"...
0x2123  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2128  throw
0x2129  call     class [mscorlib]System.Threading.Tasks.TaskFactory [mscorlib]System.Threading.Tasks.Task::get_Factory()
0x212e  ldloc.1
0x212f  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x2134  ldftn    instance class [mscorlib]System.IAsyncResult [System.Core]System.IO.Pipes.NamedPipeServerStream::BeginWaitForConnection(class [mscorlib]System.AsyncCallback, object)
0x213a  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.AsyncCallback, object, class [mscorlib]System.IAsyncResult>::.ctor(object, native int)
0x213f  ldloc.1
0x2140  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x2145  ldftn    instance void [System.Core]System.IO.Pipes.NamedPipeServerStream::EndWaitForConnection(class [mscorlib]System.IAsyncResult)
0x214b  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.IAsyncResult>::.ctor(object, native int)
0x2150  ldnull
0x2151  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.TaskFactory::FromAsync(class [mscorlib]System.Func`3<class [mscorlib]System.AsyncCallback, object, class [mscorlib]System.IAsyncResult>, class [mscorlib]System.Action`1<class [mscorlib]System.IAsyncResult>, object)
0x2156  ldarg.0
0x2157  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <WaitForConnectionAsync>d__6::token
0x215c  call     class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.ThreadingTools::WithCancellation(class [mscorlib]System.Threading.Tasks.Task, valuetype [mscorlib]System.Threading.CancellationToken)
0x2161  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2166  stloc.2
0x2167  ldloca.s 2
0x2169  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x216e  brtrue.s loc_21AC
0x2170  ldarg.0
0x2171  ldc.i4.0
0x2172  dup
0x2173  stloc.0
0x2174  stfld    int32 <WaitForConnectionAsync>d__6::<>1__state
0x2179  ldarg.0
0x217a  ldloc.2
0x217b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForConnectionAsync>d__6::<>u__1
0x2180  ldarg.0
0x2181  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForConnectionAsync>d__6::<>t__builder
0x2186  ldloca.s 2
0x2188  ldarg.0
0x2189  call     T0x2B00001C
0x218e  leave.s  loc_21DF
0x2190  ldarg.0
0x2191  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForConnectionAsync>d__6::<>u__1
0x2196  stloc.2
0x2197  ldarg.0
0x2198  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForConnectionAsync>d__6::<>u__1
0x219d  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x21a3  ldarg.0
0x21a4  ldc.i4.m1
0x21a5  dup
0x21a6  stloc.0
0x21a7  stfld    int32 <WaitForConnectionAsync>d__6::<>1__state
0x21ac  ldloca.s 2
0x21ae  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x21b3  leave.s  loc_21CC
0x21b5  stloc.3
0x21b6  ldarg.0
0x21b7  ldc.i4.s 0xFE
0x21b9  stfld    int32 <WaitForConnectionAsync>d__6::<>1__state
0x21be  ldarg.0
0x21bf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForConnectionAsync>d__6::<>t__builder
0x21c4  ldloc.3
0x21c5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x21ca  leave.s  loc_21DF
0x21cc  ldarg.0
0x21cd  ldc.i4.s 0xFE
0x21cf  stfld    int32 <WaitForConnectionAsync>d__6::<>1__state
0x21d4  ldarg.0
0x21d5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForConnectionAsync>d__6::<>t__builder
0x21da  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x21df  ret
```
