# <SendAsync>d__8::MoveNext

- ea: `0xd090`
- end: `0xd1f3`
- name: `<SendAsync>d__8::MoveNext`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x44f0`
- `0x4520`
- `0x4570`
- `0xd090`

## pseudocode

```c

```

## disassembly

```asm
0xd090  ldarg.0
0xd091  ldfld    int32 <SendAsync>d__8::<>1__state
0xd096  stloc.0
0xd097  ldarg.0
0xd098  ldfld    class System.Net.Http.Handlers.ProgressMessageHandler <SendAsync>d__8::<>4__this
0xd09d  stloc.1
0xd09e  ldloc.0
0xd09f  brfalse.s loc_D0FA
0xd0a1  ldloc.0
0xd0a2  ldc.i4.1
0xd0a3  beq      loc_D197
0xd0a8  ldloc.1
0xd0a9  ldarg.0
0xd0aa  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__8::request
0xd0af  call     instance void System.Net.Http.Handlers.ProgressMessageHandler::AddRequestProgress(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0xd0b4  ldloc.1
0xd0b5  ldarg.0
0xd0b6  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__8::request
0xd0bb  ldarg.0
0xd0bc  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__8::cancellationToken
0xd0c1  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> System.Net.Http.Handlers.ProgressMessageHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xd0c6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0xd0cb  stloc.s  4
0xd0cd  ldloca.s 4
0xd0cf  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0xd0d4  brtrue.s loc_D117
0xd0d6  ldarg.0
0xd0d7  ldc.i4.0
0xd0d8  dup
0xd0d9  stloc.0
0xd0da  stfld    int32 <SendAsync>d__8::<>1__state
0xd0df  ldarg.0
0xd0e0  ldloc.s  4
0xd0e2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd0e7  ldarg.0
0xd0e8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>t__builder
0xd0ed  ldloca.s 4
0xd0ef  ldarg.0
0xd0f0  call     T0x2B000077
0xd0f5  leave    loc_D1F2
0xd0fa  ldarg.0
0xd0fb  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd100  stloc.s  4
0xd102  ldarg.0
0xd103  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd108  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0xd10e  ldarg.0
0xd10f  ldc.i4.m1
0xd110  dup
0xd111  stloc.0
0xd112  stfld    int32 <SendAsync>d__8::<>1__state
0xd117  ldloca.s 4
0xd119  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0xd11e  stloc.3
0xd11f  ldarg.0
0xd120  ldloc.3
0xd121  stfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SendAsync>d__8::<response>5__2
0xd126  ldloc.1
0xd127  ldfld    class [mscorlib]System.EventHandler`1<class System.Net.Http.Handlers.HttpProgressEventArgs> System.Net.Http.Handlers.ProgressMessageHandler::HttpReceiveProgress
0xd12c  brfalse  loc_D1BC
0xd131  ldarg.0
0xd132  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SendAsync>d__8::<response>5__2
0xd137  brfalse  loc_D1BC
0xd13c  ldarg.0
0xd13d  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SendAsync>d__8::<response>5__2
0xd142  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0xd147  brfalse.s loc_D1BC
0xd149  ldarg.0
0xd14a  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__8::cancellationToken
0xd14f  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xd154  ldloc.1
0xd155  ldarg.0
0xd156  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__8::request
0xd15b  ldarg.0
0xd15c  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SendAsync>d__8::<response>5__2
0xd161  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> System.Net.Http.Handlers.ProgressMessageHandler::AddResponseProgressAsync(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [System.Net.Http]System.Net.Http.HttpResponseMessage response)
0xd166  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0xd16b  stloc.s  4
0xd16d  ldloca.s 4
0xd16f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0xd174  brtrue.s loc_D1B4
0xd176  ldarg.0
0xd177  ldc.i4.1
0xd178  dup
0xd179  stloc.0
0xd17a  stfld    int32 <SendAsync>d__8::<>1__state
0xd17f  ldarg.0
0xd180  ldloc.s  4
0xd182  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd187  ldarg.0
0xd188  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>t__builder
0xd18d  ldloca.s 4
0xd18f  ldarg.0
0xd190  call     T0x2B000077
0xd195  leave.s  loc_D1F2
0xd197  ldarg.0
0xd198  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd19d  stloc.s  4
0xd19f  ldarg.0
0xd1a0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>u__1
0xd1a5  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0xd1ab  ldarg.0
0xd1ac  ldc.i4.m1
0xd1ad  dup
0xd1ae  stloc.0
0xd1af  stfld    int32 <SendAsync>d__8::<>1__state
0xd1b4  ldloca.s 4
0xd1b6  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0xd1bb  pop
0xd1bc  ldarg.0
0xd1bd  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SendAsync>d__8::<response>5__2
0xd1c2  stloc.2
0xd1c3  leave.s  loc_D1DE
0xd1c5  stloc.s  5
0xd1c7  ldarg.0
0xd1c8  ldc.i4.s 0xFE
0xd1ca  stfld    int32 <SendAsync>d__8::<>1__state
0xd1cf  ldarg.0
0xd1d0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>t__builder
0xd1d5  ldloc.s  5
0xd1d7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0xd1dc  leave.s  loc_D1F2
0xd1de  ldarg.0
0xd1df  ldc.i4.s 0xFE
0xd1e1  stfld    int32 <SendAsync>d__8::<>1__state
0xd1e6  ldarg.0
0xd1e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__8::<>t__builder
0xd1ec  ldloc.2
0xd1ed  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0xd1f2  ret
```
