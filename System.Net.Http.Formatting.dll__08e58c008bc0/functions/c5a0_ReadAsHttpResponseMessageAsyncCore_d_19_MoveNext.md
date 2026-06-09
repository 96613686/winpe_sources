# <ReadAsHttpResponseMessageAsyncCore>d__19::MoveNext

- ea: `0xc5a0`
- end: `0xc7a4`
- name: `<ReadAsHttpResponseMessageAsyncCore>d__19::MoveNext`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1ca0`
- `0x2720`
- `0x3450`
- `0x34b0`
- `0x3810`
- `0x9f60`
- `0x9fb0`
- `0xb4b0`
- `0xc5a0`

## pseudocode

```c

```

## disassembly

```asm
0xc5a0  ldarg.0
0xc5a1  ldfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc5a6  stloc.0
0xc5a7  ldloc.0
0xc5a8  brfalse.s loc_C5FB
0xc5aa  ldloc.0
0xc5ab  ldc.i4.1
0xc5ac  beq      loc_C66A
0xc5b1  ldarg.0
0xc5b2  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <ReadAsHttpResponseMessageAsyncCore>d__19::cancellationToken
0xc5b7  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xc5bc  ldarg.0
0xc5bd  ldfld    class [System.Net.Http]System.Net.Http.HttpContent <ReadAsHttpResponseMessageAsyncCore>d__19::content
0xc5c2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStreamAsync()
0xc5c7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xc5cc  stloc.s  5
0xc5ce  ldloca.s 5
0xc5d0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xc5d5  brtrue.s loc_C618
0xc5d7  ldarg.0
0xc5d8  ldc.i4.0
0xc5d9  dup
0xc5da  stloc.0
0xc5db  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc5e0  ldarg.0
0xc5e1  ldloc.s  5
0xc5e3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__1
0xc5e8  ldarg.0
0xc5e9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ReadAsHttpResponseMessageAsyncCore>d__19::<>t__builder
0xc5ee  ldloca.s 5
0xc5f0  ldarg.0
0xc5f1  call     T0x2B00006E
0xc5f6  leave    loc_C7A3
0xc5fb  ldarg.0
0xc5fc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__1
0xc601  stloc.s  5
0xc603  ldarg.0
0xc604  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__1
0xc609  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xc60f  ldarg.0
0xc610  ldc.i4.m1
0xc611  dup
0xc612  stloc.0
0xc613  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc618  ldloca.s 5
0xc61a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xc61f  stloc.s  4
0xc621  ldarg.0
0xc622  ldloc.s  4
0xc624  stfld    class [mscorlib]System.IO.Stream <ReadAsHttpResponseMessageAsyncCore>d__19::<stream>5__2
0xc629  ldarg.0
0xc62a  newobj   instance void System.Net.Http.HttpUnsortedResponse::.ctor()
0xc62f  stfld    class System.Net.Http.HttpUnsortedResponse <ReadAsHttpResponseMessageAsyncCore>d__19::<httpResponse>5__3
0xc634  ldarg.0
0xc635  ldarg.0
0xc636  ldfld    class System.Net.Http.HttpUnsortedResponse <ReadAsHttpResponseMessageAsyncCore>d__19::<httpResponse>5__3
0xc63b  ldc.i4   0x800
0xc640  ldarg.0
0xc641  ldfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::maxHeaderSize
0xc646  newobj   instance void System.Net.Http.Formatting.Parsers.HttpResponseHeaderParser::.ctor(class System.Net.Http.HttpUnsortedResponse httpResponse, int32 maxResponseLineSize, int32 maxHeaderSize)
0xc64b  stfld    class System.Net.Http.Formatting.Parsers.HttpResponseHeaderParser <ReadAsHttpResponseMessageAsyncCore>d__19::<parser>5__4
0xc650  ldarg.0
0xc651  ldarg.0
0xc652  ldfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::bufferSize
0xc657  newarr   [mscorlib]System.Byte
0xc65c  stfld    unsigned int8[] <ReadAsHttpResponseMessageAsyncCore>d__19::<buffer>5__5
0xc661  ldc.i4.0
0xc662  stloc.3
0xc663  ldarg.0
0xc664  ldc.i4.0
0xc665  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<headerConsumed>5__6
0xc66a  nop
0xc66b  ldloc.0
0xc66c  ldc.i4.1
0xc66d  beq.s    loc_C6C3
0xc66f  ldarg.0
0xc670  ldfld    class [mscorlib]System.IO.Stream <ReadAsHttpResponseMessageAsyncCore>d__19::<stream>5__2
0xc675  ldarg.0
0xc676  ldfld    unsigned int8[] <ReadAsHttpResponseMessageAsyncCore>d__19::<buffer>5__5
0xc67b  ldc.i4.0
0xc67c  ldarg.0
0xc67d  ldfld    unsigned int8[] <ReadAsHttpResponseMessageAsyncCore>d__19::<buffer>5__5
0xc682  ldlen
0xc683  conv.i4
0xc684  ldarg.0
0xc685  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ReadAsHttpResponseMessageAsyncCore>d__19::cancellationToken
0xc68a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [mscorlib]System.IO.Stream::ReadAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xc68f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0xc694  stloc.s  6
0xc696  ldloca.s 6
0xc698  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0xc69d  brtrue.s loc_C6E0
0xc69f  ldarg.0
0xc6a0  ldc.i4.1
0xc6a1  dup
0xc6a2  stloc.0
0xc6a3  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc6a8  ldarg.0
0xc6a9  ldloc.s  6
0xc6ab  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__2
0xc6b0  ldarg.0
0xc6b1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ReadAsHttpResponseMessageAsyncCore>d__19::<>t__builder
0xc6b6  ldloca.s 6
0xc6b8  ldarg.0
0xc6b9  call     T0x2B00006F
0xc6be  leave    loc_C7A3
0xc6c3  ldarg.0
0xc6c4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__2
0xc6c9  stloc.s  6
0xc6cb  ldarg.0
0xc6cc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsHttpResponseMessageAsyncCore>d__19::<>u__2
0xc6d1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0xc6d7  ldarg.0
0xc6d8  ldc.i4.m1
0xc6d9  dup
0xc6da  stloc.0
0xc6db  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc6e0  ldloca.s 6
0xc6e2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0xc6e7  stloc.3
0xc6e8  leave.s  loc_C6F9
0xc6ea  stloc.s  7
0xc6ec  call     string System.Net.Http.Properties.Resources::get_HttpMessageErrorReading()
0xc6f1  ldloc.s  7
0xc6f3  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0xc6f8  throw
0xc6f9  nop
0xc6fa  ldarg.0
0xc6fb  ldfld    class System.Net.Http.Formatting.Parsers.HttpResponseHeaderParser <ReadAsHttpResponseMessageAsyncCore>d__19::<parser>5__4
0xc700  ldarg.0
0xc701  ldfld    unsigned int8[] <ReadAsHttpResponseMessageAsyncCore>d__19::<buffer>5__5
0xc706  ldloc.3
0xc707  ldarg.0
0xc708  ldflda   int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<headerConsumed>5__6
0xc70d  callvirt instance valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.HttpResponseHeaderParser::ParseBuffer(unsigned int8[] buffer, int32 bytesReady, int32& bytesConsumed)
0xc712  stloc.2
0xc713  leave.s  loc_C71A
0xc715  pop
0xc716  ldc.i4.2
0xc717  stloc.2
0xc718  leave.s  loc_C71A
0xc71a  ldloc.2
0xc71b  ldc.i4.1
0xc71c  bne.un.s loc_C73A
0xc71e  ldarg.0
0xc71f  ldfld    class System.Net.Http.HttpUnsortedResponse <ReadAsHttpResponseMessageAsyncCore>d__19::<httpResponse>5__3
0xc724  ldarg.0
0xc725  ldfld    class [mscorlib]System.IO.Stream <ReadAsHttpResponseMessageAsyncCore>d__19::<stream>5__2
0xc72a  ldloc.3
0xc72b  ldarg.0
0xc72c  ldfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<headerConsumed>5__6
0xc731  sub
0xc732  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage System.Net.Http.HttpContentMessageExtensions::CreateHttpResponseMessage(class System.Net.Http.HttpUnsortedResponse httpResponse, class [mscorlib]System.IO.Stream contentStream, int32 rewind)
0xc737  stloc.1
0xc738  leave.s  loc_C78F
0xc73a  ldloc.2
0xc73b  brfalse.s loc_C765
0xc73d  call     string System.Net.Http.Properties.Resources::get_HttpMessageParserError()
0xc742  ldc.i4.2
0xc743  newarr   [mscorlib]System.Object
0xc748  dup
0xc749  ldc.i4.0
0xc74a  ldarg.0
0xc74b  ldfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<headerConsumed>5__6
0xc750  box      [mscorlib]System.Int32
0xc755  stelem.ref
0xc756  dup
0xc757  ldc.i4.1
0xc758  ldarg.0
0xc759  ldfld    unsigned int8[] <ReadAsHttpResponseMessageAsyncCore>d__19::<buffer>5__5
0xc75e  stelem.ref
0xc75f  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0xc764  throw
0xc765  ldloc.3
0xc766  brtrue   loc_C66A
0xc76b  call     string System.Net.Http.Properties.Resources::get_ReadAsHttpMessageUnexpectedTermination()
0xc770  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0xc775  throw
0xc776  stloc.s  8
0xc778  ldarg.0
0xc779  ldc.i4.s 0xFE
0xc77b  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc780  ldarg.0
0xc781  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ReadAsHttpResponseMessageAsyncCore>d__19::<>t__builder
0xc786  ldloc.s  8
0xc788  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0xc78d  leave.s  loc_C7A3
0xc78f  ldarg.0
0xc790  ldc.i4.s 0xFE
0xc792  stfld    int32 <ReadAsHttpResponseMessageAsyncCore>d__19::<>1__state
0xc797  ldarg.0
0xc798  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ReadAsHttpResponseMessageAsyncCore>d__19::<>t__builder
0xc79d  ldloc.1
0xc79e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0xc7a3  ret
```
