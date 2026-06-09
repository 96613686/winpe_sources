# <AddResponseProgressAsync>d__12::MoveNext

- ea: `0xd220`
- end: `0xd30f`
- name: `<AddResponseProgressAsync>d__12::MoveNext`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1ed0`
- `0x4590`
- `0xd220`

## pseudocode

```c

```

## disassembly

```asm
0xd220  ldarg.0
0xd221  ldfld    int32 <AddResponseProgressAsync>d__12::<>1__state
0xd226  stloc.0
0xd227  ldarg.0
0xd228  ldfld    class System.Net.Http.Handlers.ProgressMessageHandler <AddResponseProgressAsync>d__12::<>4__this
0xd22d  stloc.1
0xd22e  ldloc.0
0xd22f  brfalse.s loc_D275
0xd231  ldarg.0
0xd232  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <AddResponseProgressAsync>d__12::response
0xd237  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0xd23c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStreamAsync()
0xd241  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xd246  stloc.s  4
0xd248  ldloca.s 4
0xd24a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xd24f  brtrue.s loc_D292
0xd251  ldarg.0
0xd252  ldc.i4.0
0xd253  dup
0xd254  stloc.0
0xd255  stfld    int32 <AddResponseProgressAsync>d__12::<>1__state
0xd25a  ldarg.0
0xd25b  ldloc.s  4
0xd25d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <AddResponseProgressAsync>d__12::<>u__1
0xd262  ldarg.0
0xd263  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <AddResponseProgressAsync>d__12::<>t__builder
0xd268  ldloca.s 4
0xd26a  ldarg.0
0xd26b  call     T0x2B000078
0xd270  leave    loc_D30E
0xd275  ldarg.0
0xd276  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <AddResponseProgressAsync>d__12::<>u__1
0xd27b  stloc.s  4
0xd27d  ldarg.0
0xd27e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <AddResponseProgressAsync>d__12::<>u__1
0xd283  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xd289  ldarg.0
0xd28a  ldc.i4.m1
0xd28b  dup
0xd28c  stloc.0
0xd28d  stfld    int32 <AddResponseProgressAsync>d__12::<>1__state
0xd292  ldloca.s 4
0xd294  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xd299  ldloc.1
0xd29a  ldarg.0
0xd29b  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <AddResponseProgressAsync>d__12::request
0xd2a0  ldarg.0
0xd2a1  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <AddResponseProgressAsync>d__12::response
0xd2a6  newobj   instance void System.Net.Http.Handlers.ProgressStream::.ctor(class [mscorlib]System.IO.Stream innerStream, class System.Net.Http.Handlers.ProgressMessageHandler handler, class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [System.Net.Http]System.Net.Http.HttpResponseMessage response)
0xd2ab  newobj   instance void [System.Net.Http]System.Net.Http.StreamContent::.ctor(class [mscorlib]System.IO.Stream)
0xd2b0  stloc.3
0xd2b1  ldarg.0
0xd2b2  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <AddResponseProgressAsync>d__12::response
0xd2b7  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0xd2bc  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0xd2c1  ldloc.3
0xd2c2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0xd2c7  call     void System.Net.Http.HttpHeaderExtensions::CopyTo(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders fromHeaders, class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders toHeaders)
0xd2cc  ldarg.0
0xd2cd  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <AddResponseProgressAsync>d__12::response
0xd2d2  ldloc.3
0xd2d3  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xd2d8  ldarg.0
0xd2d9  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <AddResponseProgressAsync>d__12::response
0xd2de  stloc.2
0xd2df  leave.s  loc_D2FA
0xd2e1  stloc.s  5
0xd2e3  ldarg.0
0xd2e4  ldc.i4.s 0xFE
0xd2e6  stfld    int32 <AddResponseProgressAsync>d__12::<>1__state
0xd2eb  ldarg.0
0xd2ec  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <AddResponseProgressAsync>d__12::<>t__builder
0xd2f1  ldloc.s  5
0xd2f3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0xd2f8  leave.s  loc_D30E
0xd2fa  ldarg.0
0xd2fb  ldc.i4.s 0xFE
0xd2fd  stfld    int32 <AddResponseProgressAsync>d__12::<>1__state
0xd302  ldarg.0
0xd303  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <AddResponseProgressAsync>d__12::<>t__builder
0xd308  ldloc.2
0xd309  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0xd30e  ret
```
