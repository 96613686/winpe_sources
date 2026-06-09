# <Upload>d__6::MoveNext

- ea: `0x7590`
- end: `0x7713`
- name: `<Upload>d__6::MoveNext`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x63c0`
- `0x6500`
- `0x6550`
- `0x7590`

## pseudocode

```c

```

## disassembly

```asm
0x7590  ldarg.0
0x7591  ldfld    int32 <Upload>d__6::<>1__state
0x7596  stloc.0
0x7597  ldarg.0
0x7598  ldfld    class Microsoft.BIServer.Configuration.Http.BinaryUploader <Upload>d__6::<>4__this
0x759d  stloc.1
0x759e  ldloc.0
0x759f  brfalse.s loc_75C2
0x75a1  ldarg.0
0x75a2  ldc.i4.2
0x75a3  newarr   [mscorlib]System.String
0x75a8  dup
0x75a9  ldc.i4.0
0x75aa  ldstr    aBinaryuploader// "BinaryUploader"
0x75af  stelem.ref
0x75b0  dup
0x75b1  ldc.i4.1
0x75b2  ldstr    aUpload// "Upload"
0x75b7  stelem.ref
0x75b8  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x75bd  stfld    class [mscorlib]System.IDisposable <Upload>d__6::<>7__wrap1
0x75c2  nop
0x75c3  ldloc.0
0x75c4  brfalse  loc_76A1
0x75c9  ldarg.0
0x75ca  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <Upload>d__6::request
0x75cf  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x75d4  call     bool [System.Net.Http.Formatting]System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent(class [System.Net.Http]System.Net.Http.HttpContent)
0x75d9  brtrue.s loc_760E
0x75db  ldstr    aRequestMustBeM// "Request must be MIME multipart/form-dat"...
0x75e0  ldc.i4.1
0x75e1  newarr   [mscorlib]System.Object
0x75e6  dup
0x75e7  ldc.i4.0
0x75e8  ldarg.0
0x75e9  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <Upload>d__6::request
0x75ee  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x75f3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x75f8  callvirt instance string [mscorlib]System.Object::ToString()
0x75fd  stelem.ref
0x75fe  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x7603  ldc.i4   0x19F
0x7608  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x760d  throw
0x760e  ldarg.0
0x760f  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <Upload>d__6::request
0x7614  call     int64 Microsoft.BIServer.Configuration.Http.BinaryUploader::ApproximateUploadSize(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x7619  stloc.3
0x761a  ldloc.3
0x761b  ldloc.1
0x761c  ldfld    int64 Microsoft.BIServer.Configuration.Http.BinaryUploader::_maxUploadSize
0x7621  ble.s    loc_764F
0x7623  ldstr    aUploadSizeOf0E// "Upload size of {0} exceeds max allowabl"...
0x7628  ldloc.3
0x7629  box      [mscorlib]System.Int64
0x762e  ldloc.1
0x762f  ldfld    int64 Microsoft.BIServer.Configuration.Http.BinaryUploader::_maxUploadSize
0x7634  box      [mscorlib]System.Int64
0x7639  call     string [mscorlib]System.String::Format(string, object, object)
0x763e  dup
0x763f  call     T0x2B000015
0x7644  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x7649  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x764e  throw
0x764f  ldarg.0
0x7650  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <Upload>d__6::request
0x7655  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x765a  ldloc.1
0x765b  ldfld    string Microsoft.BIServer.Configuration.Http.BinaryUploader::_uploadPath
0x7660  ldloc.1
0x7661  ldfld    string Microsoft.BIServer.Configuration.Http.BinaryUploader::_uploadFilePrefix
0x7666  newobj   instance void Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider::.ctor(string localDir, string localPrefix)
0x766b  call     T0x2B000042
0x7670  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider>::GetAwaiter()
0x7675  stloc.s  4
0x7677  ldloca.s 4
0x7679  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider>::get_IsCompleted()
0x767e  brtrue.s loc_76BE
0x7680  ldarg.0
0x7681  ldc.i4.0
0x7682  dup
0x7683  stloc.0
0x7684  stfld    int32 <Upload>d__6::<>1__state
0x7689  ldarg.0
0x768a  ldloc.s  4
0x768c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider> <Upload>d__6::<>u__1
0x7691  ldarg.0
0x7692  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.IO.FileInfo> <Upload>d__6::<>t__builder
0x7697  ldloca.s 4
0x7699  ldarg.0
0x769a  call     T0x2B000043
0x769f  leave.s  loc_7712
0x76a1  ldarg.0
0x76a2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider> <Upload>d__6::<>u__1
0x76a7  stloc.s  4
0x76a9  ldarg.0
0x76aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider> <Upload>d__6::<>u__1
0x76af  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider>
0x76b5  ldarg.0
0x76b6  ldc.i4.m1
0x76b7  dup
0x76b8  stloc.0
0x76b9  stfld    int32 <Upload>d__6::<>1__state
0x76be  ldloca.s 4
0x76c0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider>::GetResult()
0x76c5  callvirt instance class [mscorlib]System.IO.FileInfo Microsoft.BIServer.Configuration.Http.LocalFileStreamProvider::GetUploadedFile()
0x76ca  stloc.2
0x76cb  leave.s  loc_76FE
0x76cd  ldloc.0
0x76ce  ldc.i4.0
0x76cf  bge.s    loc_76E4
0x76d1  ldarg.0
0x76d2  ldfld    class [mscorlib]System.IDisposable <Upload>d__6::<>7__wrap1
0x76d7  brfalse.s loc_76E4
0x76d9  ldarg.0
0x76da  ldfld    class [mscorlib]System.IDisposable <Upload>d__6::<>7__wrap1
0x76df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76e4  endfinally
0x76e5  stloc.s  5
0x76e7  ldarg.0
0x76e8  ldc.i4.s 0xFE
0x76ea  stfld    int32 <Upload>d__6::<>1__state
0x76ef  ldarg.0
0x76f0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.IO.FileInfo> <Upload>d__6::<>t__builder
0x76f5  ldloc.s  5
0x76f7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.IO.FileInfo>::SetException(class [mscorlib]System.Exception)
0x76fc  leave.s  loc_7712
0x76fe  ldarg.0
0x76ff  ldc.i4.s 0xFE
0x7701  stfld    int32 <Upload>d__6::<>1__state
0x7706  ldarg.0
0x7707  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.IO.FileInfo> <Upload>d__6::<>t__builder
0x770c  ldloc.2
0x770d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.IO.FileInfo>::SetResult(var<u1>)
0x7712  ret
```
