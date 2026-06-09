# <GetDocument>d__3::MoveNext

- ea: `0x6a20`
- end: `0x6b23`
- name: `<GetDocument>d__3::MoveNext`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6a20`

## pseudocode

```c

```

## disassembly

```asm
0x6a20  ldarg.0
0x6a21  ldfld    int32 <GetDocument>d__3::<>1__state
0x6a26  stloc.0
0x6a27  ldarg.0
0x6a28  ldfld    class Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration <GetDocument>d__3::<>4__this
0x6a2d  stloc.1
0x6a2e  ldloc.0
0x6a2f  brfalse.s loc_6A3C
0x6a31  ldarg.0
0x6a32  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor()
0x6a37  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetDocument>d__3::<client>5__2
0x6a3c  nop
0x6a3d  ldloc.0
0x6a3e  brfalse.s loc_6A9C
0x6a40  ldarg.0
0x6a41  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x6a46  stfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<xmldoc>5__3
0x6a4b  ldarg.0
0x6a4c  ldarg.0
0x6a4d  ldfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<xmldoc>5__3
0x6a52  stfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<>7__wrap3
0x6a57  ldarg.0
0x6a58  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetDocument>d__3::<client>5__2
0x6a5d  ldloc.1
0x6a5e  ldfld    class [System]System.Uri Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::_officeOnlineDiscoveryUrl
0x6a63  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpClient::GetStringAsync(class [System]System.Uri)
0x6a68  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x6a6d  stloc.s  4
0x6a6f  ldloca.s 4
0x6a71  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x6a76  brtrue.s loc_6AB9
0x6a78  ldarg.0
0x6a79  ldc.i4.0
0x6a7a  dup
0x6a7b  stloc.0
0x6a7c  stfld    int32 <GetDocument>d__3::<>1__state
0x6a81  ldarg.0
0x6a82  ldloc.s  4
0x6a84  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetDocument>d__3::<>u__1
0x6a89  ldarg.0
0x6a8a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x6a8f  ldloca.s 4
0x6a91  ldarg.0
0x6a92  call     T0x2B00003D
0x6a97  leave    loc_6B22
0x6a9c  ldarg.0
0x6a9d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetDocument>d__3::<>u__1
0x6aa2  stloc.s  4
0x6aa4  ldarg.0
0x6aa5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetDocument>d__3::<>u__1
0x6aaa  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x6ab0  ldarg.0
0x6ab1  ldc.i4.m1
0x6ab2  dup
0x6ab3  stloc.0
0x6ab4  stfld    int32 <GetDocument>d__3::<>1__state
0x6ab9  ldloca.s 4
0x6abb  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x6ac0  stloc.3
0x6ac1  ldarg.0
0x6ac2  ldfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<>7__wrap3
0x6ac7  ldloc.3
0x6ac8  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x6acd  ldarg.0
0x6ace  ldnull
0x6acf  stfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<>7__wrap3
0x6ad4  ldarg.0
0x6ad5  ldfld    class [System.Xml]System.Xml.XmlDocument <GetDocument>d__3::<xmldoc>5__3
0x6ada  stloc.2
0x6adb  leave.s  loc_6B0E
0x6add  ldloc.0
0x6ade  ldc.i4.0
0x6adf  bge.s    loc_6AF4
0x6ae1  ldarg.0
0x6ae2  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetDocument>d__3::<client>5__2
0x6ae7  brfalse.s loc_6AF4
0x6ae9  ldarg.0
0x6aea  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetDocument>d__3::<client>5__2
0x6aef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6af4  endfinally
0x6af5  stloc.s  5
0x6af7  ldarg.0
0x6af8  ldc.i4.s 0xFE
0x6afa  stfld    int32 <GetDocument>d__3::<>1__state
0x6aff  ldarg.0
0x6b00  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x6b05  ldloc.s  5
0x6b07  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument>::SetException(class [mscorlib]System.Exception)
0x6b0c  leave.s  loc_6B22
0x6b0e  ldarg.0
0x6b0f  ldc.i4.s 0xFE
0x6b11  stfld    int32 <GetDocument>d__3::<>1__state
0x6b16  ldarg.0
0x6b17  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument> <GetDocument>d__3::<>t__builder
0x6b1c  ldloc.2
0x6b1d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Xml]System.Xml.XmlDocument>::SetResult(var<u1>)
0x6b22  ret
```
