# <SendAsync>d__2::MoveNext

- ea: `0x17cb0`
- end: `0x17d74`
- name: `<SendAsync>d__2::MoveNext`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14230`
- `0x14eb0`
- `0x15490`
- `0x17cb0`

## string_xrefs

- `0x17d29`: `Outbound TLS Protocol (HttpClient): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x17cb0  ldarg.0
0x17cb1  ldfld    int32 <SendAsync>d__2::<>1__state
0x17cb6  stloc.0
0x17cb7  ldarg.0
0x17cb8  ldfld    class Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsTracingHttpMessageHandler <SendAsync>d__2::<>4__this
0x17cbd  stloc.1
0x17cbe  ldloc.0
0x17cbf  brfalse.s loc_17D04
0x17cc1  ldloc.1
0x17cc2  ldarg.0
0x17cc3  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__2::request
0x17cc8  ldarg.0
0x17cc9  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__2::cancellationToken
0x17cce  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsTracingHttpMessageHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x17cd3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x17cd8  stloc.s  4
0x17cda  ldloca.s 4
0x17cdc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x17ce1  brtrue.s loc_17D21
0x17ce3  ldarg.0
0x17ce4  ldc.i4.0
0x17ce5  dup
0x17ce6  stloc.0
0x17ce7  stfld    int32 <SendAsync>d__2::<>1__state
0x17cec  ldarg.0
0x17ced  ldloc.s  4
0x17cef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>u__1
0x17cf4  ldarg.0
0x17cf5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>t__builder
0x17cfa  ldloca.s 4
0x17cfc  ldarg.0
0x17cfd  call     T0x2B000014
0x17d02  leave.s  loc_17D73
0x17d04  ldarg.0
0x17d05  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>u__1
0x17d0a  stloc.s  4
0x17d0c  ldarg.0
0x17d0d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>u__1
0x17d12  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x17d18  ldarg.0
0x17d19  ldc.i4.m1
0x17d1a  dup
0x17d1b  stloc.0
0x17d1c  stfld    int32 <SendAsync>d__2::<>1__state
0x17d21  ldloca.s 4
0x17d23  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x17d28  stloc.3
0x17d29  ldstr    aOutboundTlsPro_0// "Outbound TLS Protocol (HttpClient): {0}"
0x17d2e  ldc.i4.1
0x17d2f  newarr   [mscorlib]System.Object
0x17d34  dup
0x17d35  ldc.i4.0
0x17d36  ldloc.3
0x17d37  call     string Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetTlsProtocol(class [System.Net.Http]System.Net.Http.HttpResponseMessage httpResponseMessage)
0x17d3c  stelem.ref
0x17d3d  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Info(string messageFormat, object[] parameters)
0x17d42  ldloc.3
0x17d43  stloc.2
0x17d44  leave.s  loc_17D5F
0x17d46  stloc.s  5
0x17d48  ldarg.0
0x17d49  ldc.i4.s 0xFE
0x17d4b  stfld    int32 <SendAsync>d__2::<>1__state
0x17d50  ldarg.0
0x17d51  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>t__builder
0x17d56  ldloc.s  5
0x17d58  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x17d5d  leave.s  loc_17D73
0x17d5f  ldarg.0
0x17d60  ldc.i4.s 0xFE
0x17d62  stfld    int32 <SendAsync>d__2::<>1__state
0x17d67  ldarg.0
0x17d68  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__2::<>t__builder
0x17d6d  ldloc.2
0x17d6e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x17d73  ret
```
