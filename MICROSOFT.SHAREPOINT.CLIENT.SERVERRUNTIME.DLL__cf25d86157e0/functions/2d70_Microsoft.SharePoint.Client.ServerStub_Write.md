# Microsoft.SharePoint.Client.ServerStub::Write

- ea: `0x2d70`
- end: `0x2f0c`
- name: `Microsoft.SharePoint.Client.ServerStub::Write`
- size: `412`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x2f30`
- `0x3390`
- `0x222f0`

## callees

- `0xa30`
- `0xa50`
- `0x2960`
- `0x2ce0`
- `0x2d70`
- `0x2f10`
- `0x2f30`
- `0x3130`
- `0x3a40`
- `0xe010`
- `0xe110`
- `0xe6c0`
- `0x152f0`
- `0x21840`

## string_xrefs

- `0x2d81`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x2d70  ldarg.1
0x2d71  brtrue.s loc_2D7E
0x2d73  ldstr    aValue// "value"
0x2d78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d7d  throw
0x2d7e  ldarg.3
0x2d7f  brtrue.s loc_2D8C
0x2d81  ldstr    aWriter// "writer"
0x2d86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d8b  throw
0x2d8c  ldarg.s  4
0x2d8e  brtrue.s loc_2D9B
0x2d90  ldstr    aQuery// "query"
0x2d95  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d9a  throw
0x2d9b  ldarg.s  5
0x2d9d  brtrue.s loc_2DAA
0x2d9f  ldstr    aProxycontext// "proxyContext"
0x2da4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2da9  throw
0x2daa  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x2daf  brfalse  loc_2E79
0x2db4  ldarg.s  5
0x2db6  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x2dbb  ldarg.0
0x2dbc  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x2dc1  ldstr    aSerializetooda// "_SerializeToOData"
0x2dc6  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName)
0x2dcb  stloc.0
0x2dcc  ldarg.0
0x2dcd  ldarg.1
0x2dce  ldarg.2
0x2dcf  ldarg.3
0x2dd0  ldarg.s  4
0x2dd2  ldarg.s  5
0x2dd4  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::CustomWrite(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2dd9  brfalse.s loc_2E3A
0x2ddb  ldarg.0
0x2ddc  call     instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x2de1  brfalse.s loc_2E5E
0x2de3  ldarg.s  4
0x2de5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2dea  stloc.2
0x2deb  ldloca.s 2
0x2ded  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2df2  brfalse.s loc_2E5E
0x2df4  ldarg.s  4
0x2df6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2dfb  stloc.3
0x2dfc  ldloca.s 3
0x2dfe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2e03  brfalse.s loc_2E5E
0x2e05  ldarg.0
0x2e06  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_FeedCustomWriteSupportInlineCount()
0x2e0b  brtrue.s loc_2E5E
0x2e0d  ldarg.s  5
0x2e0f  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x2e14  ldc.i4   0x5555D5
0x2e19  ldc.i4.2
0x2e1a  ldstr    aTheRequestSpec// "The request specified $inlinecount but "...
0x2e1f  ldc.i4.1
0x2e20  newarr   [mscorlib]System.Object
0x2e25  stloc.s  4
0x2e27  ldloc.s  4
0x2e29  ldc.i4.0
0x2e2a  ldarg.0
0x2e2b  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x2e30  stelem.ref
0x2e31  ldloc.s  4
0x2e33  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x2e38  br.s     loc_2E5E
0x2e3a  ldarg.0
0x2e3b  call     instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x2e40  brfalse.s loc_2E50
0x2e42  ldarg.0
0x2e43  ldarg.1
0x2e44  ldarg.3
0x2e45  ldarg.s  4
0x2e47  ldarg.s  5
0x2e49  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsFeed(object value, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2e4e  br.s     loc_2E5E
0x2e50  ldarg.0
0x2e51  ldarg.1
0x2e52  ldarg.2
0x2e53  ldarg.3
0x2e54  ldarg.s  4
0x2e56  ldarg.s  5
0x2e58  ldc.i4.0
0x2e59  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsEntityWithMonitoredScope(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x2e5e  leave.s  loc_2E6A
0x2e60  stloc.1
0x2e61  ldloc.0
0x2e62  ldloc.1
0x2e63  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x2e68  rethrow
0x2e6a  leave    loc_2F0B
0x2e6f  ldloc.0
0x2e70  brfalse.s loc_2E78
0x2e72  ldloc.0
0x2e73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e78  endfinally
0x2e79  ldarg.0
0x2e7a  ldarg.1
0x2e7b  ldarg.2
0x2e7c  ldarg.3
0x2e7d  ldarg.s  4
0x2e7f  ldarg.s  5
0x2e81  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::CustomWrite(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2e86  brfalse.s loc_2EE8
0x2e88  ldarg.0
0x2e89  call     instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x2e8e  brfalse.s loc_2F0B
0x2e90  ldarg.s  4
0x2e92  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2e97  stloc.s  5
0x2e99  ldloca.s 5
0x2e9b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2ea0  brfalse.s loc_2F0B
0x2ea2  ldarg.s  4
0x2ea4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2ea9  stloc.s  6
0x2eab  ldloca.s 6
0x2ead  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2eb2  brfalse.s loc_2F0B
0x2eb4  ldarg.0
0x2eb5  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_FeedCustomWriteSupportInlineCount()
0x2eba  brtrue.s loc_2F0B
0x2ebc  ldarg.s  5
0x2ebe  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x2ec3  ldc.i4   0x224F008
0x2ec8  ldc.i4.2
0x2ec9  ldstr    aTheRequestSpec// "The request specified $inlinecount but "...
0x2ece  ldc.i4.1
0x2ecf  newarr   [mscorlib]System.Object
0x2ed4  stloc.s  7
0x2ed6  ldloc.s  7
0x2ed8  ldc.i4.0
0x2ed9  ldarg.0
0x2eda  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x2edf  stelem.ref
0x2ee0  ldloc.s  7
0x2ee2  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x2ee7  ret
0x2ee8  ldarg.0
0x2ee9  call     instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x2eee  brfalse.s loc_2EFD
0x2ef0  ldarg.0
0x2ef1  ldarg.1
0x2ef2  ldarg.3
0x2ef3  ldarg.s  4
0x2ef5  ldarg.s  5
0x2ef7  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsFeed(object value, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2efc  ret
0x2efd  ldarg.0
0x2efe  ldarg.1
0x2eff  ldarg.2
0x2f00  ldarg.3
0x2f01  ldarg.s  4
0x2f03  ldarg.s  5
0x2f05  ldc.i4.0
0x2f06  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsEntityWithMonitoredScope(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x2f0b  ret
```
