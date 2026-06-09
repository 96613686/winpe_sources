# Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::Write

- ea: `0x1f3a0`
- end: `0x1f55c`
- name: `Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::Write`
- size: `444`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1e970`
- `0x1f560`
- `0x1fab0`
- `0x27830`

## callees

- `0xa30`
- `0xa50`
- `0x2960`
- `0x2cf0`
- `0x2f10`
- `0xe010`
- `0xe110`
- `0xe6c0`
- `0x152f0`
- `0x1f380`
- `0x1f3a0`
- `0x1f560`
- `0x1f7c0`
- `0x1fe60`
- `0x21840`

## string_xrefs

- `0x1f3bf`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x1f3a0  ldarg.0
0x1f3a1  brtrue.s loc_1F3AE
0x1f3a3  ldstr    aValue// "value"
0x1f3a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f3ad  throw
0x1f3ae  ldarg.1
0x1f3af  brtrue.s loc_1F3BC
0x1f3b1  ldstr    aServerstub// "serverStub"
0x1f3b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f3bb  throw
0x1f3bc  ldarg.3
0x1f3bd  brtrue.s loc_1F3CA
0x1f3bf  ldstr    aWriter// "writer"
0x1f3c4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f3c9  throw
0x1f3ca  ldarg.s  4
0x1f3cc  brtrue.s loc_1F3D9
0x1f3ce  ldstr    aQuery// "query"
0x1f3d3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f3d8  throw
0x1f3d9  ldarg.s  5
0x1f3db  brtrue.s loc_1F3E8
0x1f3dd  ldstr    aProxycontext// "proxyContext"
0x1f3e2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f3e7  throw
0x1f3e8  call     bool Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1f3ed  brfalse  loc_1F4C1
0x1f3f2  ldarg.s  5
0x1f3f4  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f3f9  ldarg.1
0x1f3fa  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1f3ff  ldstr    aSerializetooda// "_SerializeToOData"
0x1f404  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName)
0x1f409  stloc.0
0x1f40a  ldarg.3
0x1f40b  ldarg.s  5
0x1f40d  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f412  stloc.1
0x1f413  ldarg.1
0x1f414  ldarg.0
0x1f415  ldarg.2
0x1f416  ldloc.1
0x1f417  ldarg.s  4
0x1f419  ldarg.s  5
0x1f41b  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryWriteToODataWriter(object value, class [System]System.Uri path, class Microsoft.SharePoint.Client.RESTfulODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f420  brfalse.s loc_1F483
0x1f422  ldarg.1
0x1f423  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x1f428  brfalse.s loc_1F4A6
0x1f42a  ldarg.s  4
0x1f42c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f431  stloc.s  4
0x1f433  ldloca.s 4
0x1f435  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1f43a  brfalse.s loc_1F4A6
0x1f43c  ldarg.s  4
0x1f43e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f443  stloc.s  5
0x1f445  ldloca.s 5
0x1f447  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1f44c  brfalse.s loc_1F4A6
0x1f44e  ldarg.1
0x1f44f  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_FeedCustomWriteSupportInlineCount()
0x1f454  brtrue.s loc_1F4A6
0x1f456  ldarg.s  5
0x1f458  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f45d  ldc.i4   0x6407DF
0x1f462  ldc.i4.2
0x1f463  ldstr    aTheRequestSpec// "The request specified $inlinecount but "...
0x1f468  ldc.i4.1
0x1f469  newarr   [mscorlib]System.Object
0x1f46e  stloc.s  6
0x1f470  ldloc.s  6
0x1f472  ldc.i4.0
0x1f473  ldarg.1
0x1f474  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x1f479  stelem.ref
0x1f47a  ldloc.s  6
0x1f47c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1f481  br.s     loc_1F4A6
0x1f483  ldarg.1
0x1f484  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x1f489  brfalse.s loc_1F499
0x1f48b  ldarg.0
0x1f48c  ldarg.1
0x1f48d  ldarg.3
0x1f48e  ldarg.s  4
0x1f490  ldarg.s  5
0x1f492  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsFeed(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f497  br.s     loc_1F4A6
0x1f499  ldarg.0
0x1f49a  ldarg.1
0x1f49b  ldarg.2
0x1f49c  ldarg.3
0x1f49d  ldarg.s  4
0x1f49f  ldarg.s  5
0x1f4a1  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntityWithMonitoredScope(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f4a6  leave.s  loc_1F4B2
0x1f4a8  stloc.2
0x1f4a9  ldloc.0
0x1f4aa  ldloc.2
0x1f4ab  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x1f4b0  rethrow
0x1f4b2  leave    loc_1F55B
0x1f4b7  ldloc.0
0x1f4b8  brfalse.s loc_1F4C0
0x1f4ba  ldloc.0
0x1f4bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f4c0  endfinally
0x1f4c1  ldarg.3
0x1f4c2  ldarg.s  5
0x1f4c4  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataWriterWrapper::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f4c9  stloc.3
0x1f4ca  ldarg.1
0x1f4cb  ldarg.0
0x1f4cc  ldarg.2
0x1f4cd  ldloc.3
0x1f4ce  ldarg.s  4
0x1f4d0  ldarg.s  5
0x1f4d2  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryWriteToODataWriter(object value, class [System]System.Uri path, class Microsoft.SharePoint.Client.RESTfulODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f4d7  brfalse.s loc_1F539
0x1f4d9  ldarg.1
0x1f4da  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x1f4df  brfalse.s loc_1F55B
0x1f4e1  ldarg.s  4
0x1f4e3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f4e8  stloc.s  7
0x1f4ea  ldloca.s 7
0x1f4ec  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1f4f1  brfalse.s loc_1F55B
0x1f4f3  ldarg.s  4
0x1f4f5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f4fa  stloc.s  8
0x1f4fc  ldloca.s 8
0x1f4fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1f503  brfalse.s loc_1F55B
0x1f505  ldarg.1
0x1f506  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_FeedCustomWriteSupportInlineCount()
0x1f50b  brtrue.s loc_1F55B
0x1f50d  ldarg.s  5
0x1f50f  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f514  ldc.i4   0x224F009
0x1f519  ldc.i4.2
0x1f51a  ldstr    aTheRequestSpec// "The request specified $inlinecount but "...
0x1f51f  ldc.i4.1
0x1f520  newarr   [mscorlib]System.Object
0x1f525  stloc.s  9
0x1f527  ldloc.s  9
0x1f529  ldc.i4.0
0x1f52a  ldarg.1
0x1f52b  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x1f530  stelem.ref
0x1f531  ldloc.s  9
0x1f533  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1f538  ret
0x1f539  ldarg.1
0x1f53a  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x1f53f  brfalse.s loc_1F54E
0x1f541  ldarg.0
0x1f542  ldarg.1
0x1f543  ldarg.3
0x1f544  ldarg.s  4
0x1f546  ldarg.s  5
0x1f548  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsFeed(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f54d  ret
0x1f54e  ldarg.0
0x1f54f  ldarg.1
0x1f550  ldarg.2
0x1f551  ldarg.3
0x1f552  ldarg.s  4
0x1f554  ldarg.s  5
0x1f556  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntityWithMonitoredScope(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f55b  ret
```
