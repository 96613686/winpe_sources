# <ReadAsHttpRequestMessageAsyncCore>d__12::MoveNext

- ea: `0xc370`
- end: `0xc57a`
- name: `<ReadAsHttpRequestMessageAsyncCore>d__12::MoveNext`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1c50`
- `0x2670`
- `0x3450`
- `0x34b0`
- `0x3810`
- `0x99f0`
- `0x9a40`
- `0xb4b0`
- `0xc370`

## pseudocode

```c

```

## disassembly

```asm
0xc370  ldarg.0
0xc371  ldfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc376  stloc.0
0xc377  ldloc.0
0xc378  brfalse.s loc_C3CB
0xc37a  ldloc.0
0xc37b  ldc.i4.1
0xc37c  beq      loc_C43A
0xc381  ldarg.0
0xc382  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <ReadAsHttpRequestMessageAsyncCore>d__12::cancellationToken
0xc387  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xc38c  ldarg.0
0xc38d  ldfld    class [System.Net.Http]System.Net.Http.HttpContent <ReadAsHttpRequestMessageAsyncCore>d__12::content
0xc392  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStreamAsync()
0xc397  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xc39c  stloc.s  5
0xc39e  ldloca.s 5
0xc3a0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xc3a5  brtrue.s loc_C3E8
0xc3a7  ldarg.0
0xc3a8  ldc.i4.0
0xc3a9  dup
0xc3aa  stloc.0
0xc3ab  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc3b0  ldarg.0
0xc3b1  ldloc.s  5
0xc3b3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__1
0xc3b8  ldarg.0
0xc3b9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> <ReadAsHttpRequestMessageAsyncCore>d__12::<>t__builder
0xc3be  ldloca.s 5
0xc3c0  ldarg.0
0xc3c1  call     T0x2B00006C
0xc3c6  leave    loc_C579
0xc3cb  ldarg.0
0xc3cc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__1
0xc3d1  stloc.s  5
0xc3d3  ldarg.0
0xc3d4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__1
0xc3d9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xc3df  ldarg.0
0xc3e0  ldc.i4.m1
0xc3e1  dup
0xc3e2  stloc.0
0xc3e3  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc3e8  ldloca.s 5
0xc3ea  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xc3ef  stloc.s  4
0xc3f1  ldarg.0
0xc3f2  ldloc.s  4
0xc3f4  stfld    class [mscorlib]System.IO.Stream <ReadAsHttpRequestMessageAsyncCore>d__12::<stream>5__2
0xc3f9  ldarg.0
0xc3fa  newobj   instance void System.Net.Http.HttpUnsortedRequest::.ctor()
0xc3ff  stfld    class System.Net.Http.HttpUnsortedRequest <ReadAsHttpRequestMessageAsyncCore>d__12::<httpRequest>5__3
0xc404  ldarg.0
0xc405  ldarg.0
0xc406  ldfld    class System.Net.Http.HttpUnsortedRequest <ReadAsHttpRequestMessageAsyncCore>d__12::<httpRequest>5__3
0xc40b  ldc.i4   0x800
0xc410  ldarg.0
0xc411  ldfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::maxHeaderSize
0xc416  newobj   instance void System.Net.Http.Formatting.Parsers.HttpRequestHeaderParser::.ctor(class System.Net.Http.HttpUnsortedRequest httpRequest, int32 maxRequestLineSize, int32 maxHeaderSize)
0xc41b  stfld    class System.Net.Http.Formatting.Parsers.HttpRequestHeaderParser <ReadAsHttpRequestMessageAsyncCore>d__12::<parser>5__4
0xc420  ldarg.0
0xc421  ldarg.0
0xc422  ldfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::bufferSize
0xc427  newarr   [mscorlib]System.Byte
0xc42c  stfld    unsigned int8[] <ReadAsHttpRequestMessageAsyncCore>d__12::<buffer>5__5
0xc431  ldc.i4.0
0xc432  stloc.3
0xc433  ldarg.0
0xc434  ldc.i4.0
0xc435  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<headerConsumed>5__6
0xc43a  nop
0xc43b  ldloc.0
0xc43c  ldc.i4.1
0xc43d  beq.s    loc_C493
0xc43f  ldarg.0
0xc440  ldfld    class [mscorlib]System.IO.Stream <ReadAsHttpRequestMessageAsyncCore>d__12::<stream>5__2
0xc445  ldarg.0
0xc446  ldfld    unsigned int8[] <ReadAsHttpRequestMessageAsyncCore>d__12::<buffer>5__5
0xc44b  ldc.i4.0
0xc44c  ldarg.0
0xc44d  ldfld    unsigned int8[] <ReadAsHttpRequestMessageAsyncCore>d__12::<buffer>5__5
0xc452  ldlen
0xc453  conv.i4
0xc454  ldarg.0
0xc455  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ReadAsHttpRequestMessageAsyncCore>d__12::cancellationToken
0xc45a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [mscorlib]System.IO.Stream::ReadAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xc45f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0xc464  stloc.s  6
0xc466  ldloca.s 6
0xc468  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0xc46d  brtrue.s loc_C4B0
0xc46f  ldarg.0
0xc470  ldc.i4.1
0xc471  dup
0xc472  stloc.0
0xc473  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc478  ldarg.0
0xc479  ldloc.s  6
0xc47b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__2
0xc480  ldarg.0
0xc481  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> <ReadAsHttpRequestMessageAsyncCore>d__12::<>t__builder
0xc486  ldloca.s 6
0xc488  ldarg.0
0xc489  call     T0x2B00006D
0xc48e  leave    loc_C579
0xc493  ldarg.0
0xc494  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__2
0xc499  stloc.s  6
0xc49b  ldarg.0
0xc49c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpRequestMessageAsyncCore>d__12::<>u__2
0xc4a1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0xc4a7  ldarg.0
0xc4a8  ldc.i4.m1
0xc4a9  dup
0xc4aa  stloc.0
0xc4ab  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc4b0  ldloca.s 6
0xc4b2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0xc4b7  stloc.3
0xc4b8  leave.s  loc_C4C9
0xc4ba  stloc.s  7
0xc4bc  call     string System.Net.Http.Properties.Resources::get_HttpMessageErrorReading()
0xc4c1  ldloc.s  7
0xc4c3  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0xc4c8  throw
0xc4c9  nop
0xc4ca  ldarg.0
0xc4cb  ldfld    class System.Net.Http.Formatting.Parsers.HttpRequestHeaderParser <ReadAsHttpRequestMessageAsyncCore>d__12::<parser>5__4
0xc4d0  ldarg.0
0xc4d1  ldfld    unsigned int8[] <ReadAsHttpRequestMessageAsyncCore>d__12::<buffer>5__5
0xc4d6  ldloc.3
0xc4d7  ldarg.0
0xc4d8  ldflda   int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<headerConsumed>5__6
0xc4dd  callvirt instance valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.HttpRequestHeaderParser::ParseBuffer(unsigned int8[] buffer, int32 bytesReady, int32& bytesConsumed)
0xc4e2  stloc.2
0xc4e3  leave.s  loc_C4EA
0xc4e5  pop
0xc4e6  ldc.i4.2
0xc4e7  stloc.2
0xc4e8  leave.s  loc_C4EA
0xc4ea  ldloc.2
0xc4eb  ldc.i4.1
0xc4ec  bne.un.s loc_C510
0xc4ee  ldarg.0
0xc4ef  ldfld    string <ReadAsHttpRequestMessageAsyncCore>d__12::uriScheme
0xc4f4  ldarg.0
0xc4f5  ldfld    class System.Net.Http.HttpUnsortedRequest <ReadAsHttpRequestMessageAsyncCore>d__12::<httpRequest>5__3
0xc4fa  ldarg.0
0xc4fb  ldfld    class [mscorlib]System.IO.Stream <ReadAsHttpRequestMessageAsyncCore>d__12::<stream>5__2
0xc500  ldloc.3
0xc501  ldarg.0
0xc502  ldfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<headerConsumed>5__6
0xc507  sub
0xc508  call     class [System.Net.Http]System.Net.Http.HttpRequestMessage System.Net.Http.HttpContentMessageExtensions::CreateHttpRequestMessage(string uriScheme, class System.Net.Http.HttpUnsortedRequest httpRequest, class [mscorlib]System.IO.Stream contentStream, int32 rewind)
0xc50d  stloc.1
0xc50e  leave.s  loc_C565
0xc510  ldloc.2
0xc511  brfalse.s loc_C53B
0xc513  call     string System.Net.Http.Properties.Resources::get_HttpMessageParserError()
0xc518  ldc.i4.2
0xc519  newarr   [mscorlib]System.Object
0xc51e  dup
0xc51f  ldc.i4.0
0xc520  ldarg.0
0xc521  ldfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<headerConsumed>5__6
0xc526  box      [mscorlib]System.Int32
0xc52b  stelem.ref
0xc52c  dup
0xc52d  ldc.i4.1
0xc52e  ldarg.0
0xc52f  ldfld    unsigned int8[] <ReadAsHttpRequestMessageAsyncCore>d__12::<buffer>5__5
0xc534  stelem.ref
0xc535  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0xc53a  throw
0xc53b  ldloc.3
0xc53c  brtrue   loc_C43A
0xc541  call     string System.Net.Http.Properties.Resources::get_ReadAsHttpMessageUnexpectedTermination()
0xc546  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0xc54b  throw
0xc54c  stloc.s  8
0xc54e  ldarg.0
0xc54f  ldc.i4.s 0xFE
0xc551  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc556  ldarg.0
0xc557  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> <ReadAsHttpRequestMessageAsyncCore>d__12::<>t__builder
0xc55c  ldloc.s  8
0xc55e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage>::SetException(class [mscorlib]System.Exception)
0xc563  leave.s  loc_C579
0xc565  ldarg.0
0xc566  ldc.i4.s 0xFE
0xc568  stfld    int32 <ReadAsHttpRequestMessageAsyncCore>d__12::<>1__state
0xc56d  ldarg.0
0xc56e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> <ReadAsHttpRequestMessageAsyncCore>d__12::<>t__builder
0xc573  ldloc.1
0xc574  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage>::SetResult(var<u1>)
0xc579  ret
```
