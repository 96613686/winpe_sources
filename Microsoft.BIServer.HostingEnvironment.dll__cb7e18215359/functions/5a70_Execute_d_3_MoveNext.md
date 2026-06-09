# <Execute>d__3::MoveNext

- ea: `0x5a70`
- end: `0x5baa`
- name: `<Execute>d__3::MoveNext`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa60`
- `0x15d0`
- `0x23c0`
- `0x5a70`

## pseudocode

```c

```

## disassembly

```asm
0x5a70  ldarg.0
0x5a71  ldfld    int32 valuetype <Execute>d__3<var<u1>>::<>1__state
0x5a76  stloc.0
0x5a77  ldarg.0
0x5a78  ldfld    class Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<var<u1>> valuetype <Execute>d__3<var<u1>>::<>4__this
0x5a7d  stloc.1
0x5a7e  ldloc.0
0x5a7f  brfalse.s loc_5A8C
0x5a81  ldarg.0
0x5a82  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterServiceAccountContext()
0x5a87  stfld    class [mscorlib]System.IDisposable valuetype <Execute>d__3<var<u1>>::<>7__wrap1
0x5a8c  nop
0x5a8d  ldloc.0
0x5a8e  brfalse.s loc_5ADB
0x5a90  ldloc.1
0x5a91  ldfld    class [System]System.Uri class Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<var<u1>>::_uri
0x5a96  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x5a9b  dup
0x5a9c  ldc.i4.1
0x5a9d  callvirt instance void [System]System.Net.WebRequest::set_UseDefaultCredentials(bool)
0x5aa2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse> [System]System.Net.WebRequest::GetResponseAsync()
0x5aa7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse>::GetAwaiter()
0x5aac  stloc.s  4
0x5aae  ldloca.s 4
0x5ab0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse>::get_IsCompleted()
0x5ab5  brtrue.s loc_5AF8
0x5ab7  ldarg.0
0x5ab8  ldc.i4.0
0x5ab9  dup
0x5aba  stloc.0
0x5abb  stfld    int32 valuetype <Execute>d__3<var<u1>>::<>1__state
0x5ac0  ldarg.0
0x5ac1  ldloc.s  4
0x5ac3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse> valuetype <Execute>d__3<var<u1>>::<>u__1
0x5ac8  ldarg.0
0x5ac9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <Execute>d__3<var<u1>>::<>t__builder
0x5ace  ldloca.s 4
0x5ad0  ldarg.0
0x5ad1  call     T0x2B00003A
0x5ad6  leave    loc_5BA9
0x5adb  ldarg.0
0x5adc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse> valuetype <Execute>d__3<var<u1>>::<>u__1
0x5ae1  stloc.s  4
0x5ae3  ldarg.0
0x5ae4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse> valuetype <Execute>d__3<var<u1>>::<>u__1
0x5ae9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse>
0x5aef  ldarg.0
0x5af0  ldc.i4.m1
0x5af1  dup
0x5af2  stloc.0
0x5af3  stfld    int32 valuetype <Execute>d__3<var<u1>>::<>1__state
0x5af8  ldloca.s 4
0x5afa  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Net.WebResponse>::GetResult()
0x5aff  castclass [System]System.Net.HttpWebResponse
0x5b04  stloc.3
0x5b05  ldloc.3
0x5b06  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x5b0b  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x5b10  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x5b15  ldloc.3
0x5b16  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5b1b  ldc.i4   0xC8
0x5b20  beq.s    loc_5B4E
0x5b22  ldstr    aTrustedwebapiF// "TrustedWebApi failed. Status code {0}"
0x5b27  ldloc.3
0x5b28  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5b2d  box      [System]System.Net.HttpStatusCode
0x5b32  call     string [mscorlib]System.String::Format(string, object)
0x5b37  dup
0x5b38  call     T0x2B00000A
0x5b3d  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x5b42  ldloc.3
0x5b43  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5b48  newobj   instance void Microsoft.BIServer.HostingEnvironment.WebApiException::.ctor(string message, valuetype [System]System.Net.HttpStatusCode status)
0x5b4d  throw
0x5b4e  call     T0x2B00003B
0x5b53  stloc.2
0x5b54  leave.s  loc_5B95
0x5b56  ldloc.0
0x5b57  ldc.i4.0
0x5b58  bge.s    loc_5B63
0x5b5a  ldloc.3
0x5b5b  brfalse.s loc_5B63
0x5b5d  ldloc.3
0x5b5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b63  endfinally
0x5b64  ldloc.0
0x5b65  ldc.i4.0
0x5b66  bge.s    loc_5B7B
0x5b68  ldarg.0
0x5b69  ldfld    class [mscorlib]System.IDisposable valuetype <Execute>d__3<var<u1>>::<>7__wrap1
0x5b6e  brfalse.s loc_5B7B
0x5b70  ldarg.0
0x5b71  ldfld    class [mscorlib]System.IDisposable valuetype <Execute>d__3<var<u1>>::<>7__wrap1
0x5b76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b7b  endfinally
0x5b7c  stloc.s  5
0x5b7e  ldarg.0
0x5b7f  ldc.i4.s 0xFE
0x5b81  stfld    int32 valuetype <Execute>d__3<var<u1>>::<>1__state
0x5b86  ldarg.0
0x5b87  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <Execute>d__3<var<u1>>::<>t__builder
0x5b8c  ldloc.s  5
0x5b8e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x5b93  leave.s  loc_5BA9
0x5b95  ldarg.0
0x5b96  ldc.i4.s 0xFE
0x5b98  stfld    int32 valuetype <Execute>d__3<var<u1>>::<>1__state
0x5b9d  ldarg.0
0x5b9e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <Execute>d__3<var<u1>>::<>t__builder
0x5ba3  ldloc.2
0x5ba4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x5ba9  ret
```
