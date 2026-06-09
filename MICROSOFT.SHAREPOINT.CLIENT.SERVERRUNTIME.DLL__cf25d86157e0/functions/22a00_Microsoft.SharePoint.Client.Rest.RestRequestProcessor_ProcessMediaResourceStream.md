# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMediaResourceStream

- ea: `0x22a00`
- end: `0x22bb2`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMediaResourceStream`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x222f0`

## callees

- `0x2a80`
- `0x2ca0`
- `0x2cb0`
- `0x98e0`
- `0xe010`
- `0xeea0`
- `0xefc0`
- `0xf0a0`
- `0x12df0`
- `0x12e20`
- `0x16f10`
- `0x20240`
- `0x21bc0`
- `0x21c60`
- `0x21d20`
- `0x22a00`
- `0x22c30`
- `0x23de0`
- `0x23e20`

## string_xrefs

- `0x22acd`: `The type {0} does not support media resource write operation.`
- `0x22b31`: `application/json; odata=verbose`
- `0x22b70`: `The http method {0} cannot be used to access media resource.`

## pseudocode

```c

```

## disassembly

```asm
0x22a00  ldarg.0
0x22a01  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22a06  ldstr    aGet_0// "GET"
0x22a0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22a10  brtrue.s loc_22A24
0x22a12  ldarg.0
0x22a13  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22a18  ldstr    aHead// "HEAD"
0x22a1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22a22  brfalse.s loc_22A9F
0x22a24  ldarg.2
0x22a25  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_ReadStreamMethodName()
0x22a2a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22a2f  brfalse.s loc_22A66
0x22a31  ldarg.0
0x22a32  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22a37  ldc.i4   0x1C50C7
0x22a3c  ldc.i4.1
0x22a3d  ldstr    aTheType0DoesNo// "The type {0} does not support media str"...
0x22a42  ldc.i4.1
0x22a43  newarr   [mscorlib]System.Object
0x22a48  stloc.s  6
0x22a4a  ldloc.s  6
0x22a4c  ldc.i4.0
0x22a4d  ldarg.2
0x22a4e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22a53  callvirt instance string [mscorlib]System.Type::get_FullName()
0x22a58  stelem.ref
0x22a59  ldloc.s  6
0x22a5b  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x22a60  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x22a65  throw
0x22a66  ldarg.0
0x22a67  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22a6c  newobj   instance void Microsoft.SharePoint.Client.ClientValueCollection::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22a71  stloc.0
0x22a72  ldarg.2
0x22a73  ldarg.1
0x22a74  ldarg.2
0x22a75  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_ReadStreamMethodName()
0x22a7a  ldloc.0
0x22a7b  ldarg.0
0x22a7c  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22a81  ldloca.s 1
0x22a83  callvirt instance object Microsoft.SharePoint.Client.ServerStub::InvokeMethodWithMonitoredScope(object target, string methodName, class Microsoft.SharePoint.Client.ClientValueCollection args, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] bool& isVoid)
0x22a88  isinst   [mscorlib]System.IO.Stream
0x22a8d  stloc.2
0x22a8e  ldloc.2
0x22a8f  brtrue.s loc_22A97
0x22a91  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x22a96  stloc.2
0x22a97  ldarg.0
0x22a98  ldloc.2
0x22a99  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetRestRequestResultWithStream(class [mscorlib]System.IO.Stream rawStream)
0x22a9e  ret
0x22a9f  ldarg.0
0x22aa0  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22aa5  ldstr    aPut// "PUT"
0x22aaa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22aaf  brfalse  loc_22B64
0x22ab4  ldarg.2
0x22ab5  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_WriteStreamMethodName()
0x22aba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22abf  brfalse.s loc_22AF6
0x22ac1  ldarg.0
0x22ac2  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22ac7  ldc.i4   0x1C50C8
0x22acc  ldc.i4.1
0x22acd  ldstr    aTheType0DoesNo_0// "The type {0} does not support media res"...
0x22ad2  ldc.i4.1
0x22ad3  newarr   [mscorlib]System.Object
0x22ad8  stloc.s  7
0x22ada  ldloc.s  7
0x22adc  ldc.i4.0
0x22add  ldarg.2
0x22ade  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22ae3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x22ae8  stelem.ref
0x22ae9  ldloc.s  7
0x22aeb  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x22af0  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x22af5  throw
0x22af6  ldarg.0
0x22af7  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22afc  newobj   instance void Microsoft.SharePoint.Client.ClientValueCollection::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22b01  stloc.3
0x22b02  ldloc.3
0x22b03  ldc.i4.0
0x22b04  ldarg.0
0x22b05  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22b0a  ldarg.0
0x22b0b  call     instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream()
0x22b10  newobj   instance void Microsoft.SharePoint.Client.ServerObjectClientValue::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext, object value)
0x22b15  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x22b1a  ldarg.2
0x22b1b  ldarg.1
0x22b1c  ldarg.2
0x22b1d  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_WriteStreamMethodName()
0x22b22  ldloc.3
0x22b23  ldarg.0
0x22b24  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22b29  ldloca.s 4
0x22b2b  callvirt instance object Microsoft.SharePoint.Client.ServerStub::InvokeMethodWithMonitoredScope(object target, string methodName, class Microsoft.SharePoint.Client.ClientValueCollection args, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] bool& isVoid)
0x22b30  pop
0x22b31  ldstr    aApplicationJso_1// "application/json; odata=verbose"
0x22b36  ldarg.0
0x22b37  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x22b3c  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x22b41  stloc.s  5
0x22b43  ldloc.s  5
0x22b45  ldc.i4   0xCC
0x22b4a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x22b4f  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_StatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x22b54  ldloc.s  5
0x22b56  ldc.i4.1
0x22b57  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x22b5c  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_SuppressEntityBody(valuetype [mscorlib]System.Nullable`1<bool> value)
0x22b61  ldloc.s  5
0x22b63  ret
0x22b64  ldarg.0
0x22b65  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22b6a  ldc.i4   0x1C50C9
0x22b6f  ldc.i4.1
0x22b70  ldstr    aTheHttpMethod0// "The http method {0} cannot be used to a"...
0x22b75  ldc.i4.1
0x22b76  newarr   [mscorlib]System.Object
0x22b7b  stloc.s  8
0x22b7d  ldloc.s  8
0x22b7f  ldc.i4.0
0x22b80  ldarg.0
0x22b81  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22b86  stelem.ref
0x22b87  ldloc.s  8
0x22b89  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x22b8e  ldstr    aNotsupportedht// "NotSupportedHttpMethodMediaResource"
0x22b93  ldc.i4.1
0x22b94  newarr   [mscorlib]System.Object
0x22b99  stloc.s  9
0x22b9b  ldloc.s  9
0x22b9d  ldc.i4.0
0x22b9e  ldarg.0
0x22b9f  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22ba4  stelem.ref
0x22ba5  ldloc.s  9
0x22ba7  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x22bac  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x22bb1  throw
```
