# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryDeleteEntity

- ea: `0x23c50`
- end: `0x23d18`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryDeleteEntity`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x222f0`

## callees

- `0xa50`
- `0x2a80`
- `0x2c90`
- `0x2f10`
- `0x3720`
- `0x98e0`
- `0xe010`
- `0xefc0`
- `0x12df0`
- `0x12e20`
- `0x16f10`
- `0x20240`
- `0x23c50`

## string_xrefs

- `0x23c56`: `DELETE`

## pseudocode

```c

```

## disassembly

```asm
0x23c50  ldarg.0
0x23c51  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x23c56  ldstr    aDelete// "DELETE"
0x23c5b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x23c60  brfalse.s loc_23C64
0x23c62  ldc.i4.0
0x23c63  ret
0x23c64  ldarg.2
0x23c65  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x23c6a  brtrue.s loc_23C79
0x23c6c  ldarg.2
0x23c6d  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_DeleteMethodName()
0x23c72  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23c77  brfalse.s loc_23CA3
0x23c79  ldstr    aNotsupportedht_0// "NotSupportedHttpMethod"
0x23c7e  ldc.i4.2
0x23c7f  newarr   [mscorlib]System.Object
0x23c84  stloc.3
0x23c85  ldloc.3
0x23c86  ldc.i4.0
0x23c87  ldarg.2
0x23c88  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x23c8d  stelem.ref
0x23c8e  ldloc.3
0x23c8f  ldc.i4.1
0x23c90  ldarg.0
0x23c91  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x23c96  stelem.ref
0x23c97  ldloc.3
0x23c98  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x23c9d  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x23ca2  throw
0x23ca3  ldarg.2
0x23ca4  ldarg.2
0x23ca5  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_DeleteMethodName()
0x23caa  ldarg.0
0x23cab  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x23cb0  ldloca.s 0
0x23cb2  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryGetMethodInfo(string name, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] class Microsoft.SharePoint.Client.MethodInformation& method)
0x23cb7  brtrue.s loc_23CF3
0x23cb9  ldarg.0
0x23cba  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x23cbf  ldc.i4   0x1C50D5
0x23cc4  ldc.i4.1
0x23cc5  ldstr    aCannotFindMeth_0// "Cannot find method {0} for type {1}"
0x23cca  ldc.i4.2
0x23ccb  newarr   [mscorlib]System.Object
0x23cd0  stloc.s  4
0x23cd2  ldloc.s  4
0x23cd4  ldc.i4.0
0x23cd5  ldarg.2
0x23cd6  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_DeleteMethodName()
0x23cdb  stelem.ref
0x23cdc  ldloc.s  4
0x23cde  ldc.i4.1
0x23cdf  ldarg.2
0x23ce0  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x23ce5  stelem.ref
0x23ce6  ldloc.s  4
0x23ce8  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x23ced  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x23cf2  throw
0x23cf3  ldarg.0
0x23cf4  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x23cf9  newobj   instance void Microsoft.SharePoint.Client.ClientValueCollection::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x23cfe  stloc.1
0x23cff  ldarg.2
0x23d00  ldarg.1
0x23d01  ldarg.2
0x23d02  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_DeleteMethodName()
0x23d07  ldloc.1
0x23d08  ldarg.0
0x23d09  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x23d0e  ldloca.s 2
0x23d10  callvirt instance object Microsoft.SharePoint.Client.ServerStub::InvokeMethodWithMonitoredScope(object target, string methodName, class Microsoft.SharePoint.Client.ClientValueCollection args, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] bool& isVoid)
0x23d15  pop
0x23d16  ldc.i4.1
0x23d17  ret
```
