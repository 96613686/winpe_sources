# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPathMember

- ea: `0x24c40`
- end: `0x2526f`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPathMember`
- size: `1583`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x24410`

## callees

- `0x300`
- `0x5b0`
- `0xa30`
- `0xa50`
- `0xc90`
- `0x2940`
- `0x2950`
- `0x2c50`
- `0x2d30`
- `0x2f10`
- `0x3790`
- `0x4890`
- `0x48b0`
- `0x48d0`
- `0x8b10`
- `0x8b30`
- `0x8b70`
- `0x98e0`
- `0xe010`
- `0x12e20`
- `0x168e0`
- `0x16920`
- `0x16ad0`
- `0x16f10`
- `0x1b970`
- `0x1b990`
- `0x1b9f0`
- `0x1ba30`
- `0x20240`
- `0x24c40`
- `0x25270`
- `0x252a0`
- `0x252e0`
- `0x25360`
- `0x26360`
- `0x26380`
- `0x26410`
- `0x29560`
- `0x297b0`
- `0x297d0`

## string_xrefs

- `0x25114`: `Extension property access. PropertyName={0}`
- `0x25183`: `Extension property indexer access. PropertyName={0}`

## pseudocode

```c

```

## disassembly

```asm
0x24c40  ldarg.s  6
0x24c42  ldnull
0x24c43  stind.ref
0x24c44  ldarg.3
0x24c45  brtrue.s loc_24C5C
0x24c47  ldarg.0
0x24c48  ldarg.2
0x24c49  ldc.i4.0
0x24c4a  ldarg.s  4
0x24c4c  callvirt instance int32 Microsoft.SharePoint.Client.Rest.EdmParserNode::get_TokenPosition()
0x24c51  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x24c56  call     instance class Microsoft.SharePoint.Client.ResourceNotFoundException Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateResourceNotFoundException(string resource)
0x24c5b  throw
0x24c5c  ldarg.3
0x24c5d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x24c62  ldarg.0
0x24c63  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24c68  call     class Microsoft.SharePoint.Client.ValueTypeConverter Microsoft.SharePoint.Client.ProxyMap::GetValueTypeConverter(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x24c6d  stloc.1
0x24c6e  ldloc.1
0x24c6f  brfalse  loc_24D31
0x24c74  ldarg.s  4
0x24c76  callvirt instance valuetype Microsoft.SharePoint.Client.Rest.EdmParserNodeType Microsoft.SharePoint.Client.Rest.EdmParserNode::get_NodeType()
0x24c7b  ldc.i4.1
0x24c7c  beq.s    loc_24C8C
0x24c7e  ldarg.0
0x24c7f  ldarg.s  4
0x24c81  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24c86  call     instance class Microsoft.SharePoint.Client.ResourceNotFoundException Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateResourceNotFoundException(string resource)
0x24c8b  throw
0x24c8c  ldarg.s  4
0x24c8e  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24c93  ldstr    aApi// "$api"
0x24c98  ldc.i4.5
0x24c99  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24c9e  brfalse.s loc_24CD7
0x24ca0  ldarg.0
0x24ca1  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CheckApiMetadataEnabled()
0x24ca6  newobj   instance void ObjectWithPathName::.ctor()
0x24cab  stloc.2
0x24cac  ldloc.2
0x24cad  ldstr    aApi_0// "Api"
0x24cb2  stfld    string ObjectWithPathName::PathName
0x24cb7  ldloc.2
0x24cb8  ldarg.0
0x24cb9  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24cbe  call     class Microsoft.SharePoint.Client.ApiMetadataBuilder Microsoft.SharePoint.Client.ApiMetadataBuilder::GetInstance(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x24cc3  ldloc.1
0x24cc4  callvirt instance class Microsoft.SharePoint.Client.TypeInformation Microsoft.SharePoint.Client.ApiMetadataBuilder::GetTypeInformation(class Microsoft.SharePoint.Client.ValueTypeConverter valueTypeConverter)
0x24cc9  stfld    object ObjectWithPathName::Value
0x24cce  ldloc.2
0x24ccf  ldc.i4.0
0x24cd0  stfld    valuetype ObjectResultType ObjectWithPathName::ResultType
0x24cd5  ldloc.2
0x24cd6  ret
0x24cd7  ldloc.1
0x24cd8  ldarg.s  4
0x24cda  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24cdf  ldarg.0
0x24ce0  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24ce5  ldloca.s 0
0x24ce7  callvirt instance bool Microsoft.SharePoint.Client.ValueTypeConverter::TryGetPropertyInfo(string name, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] class Microsoft.SharePoint.Client.PropertyInformation& property)
0x24cec  brtrue.s loc_24CFC
0x24cee  ldarg.0
0x24cef  ldarg.s  4
0x24cf1  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24cf6  call     instance class Microsoft.SharePoint.Client.ResourceNotFoundException Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateResourceNotFoundException(string resource)
0x24cfb  throw
0x24cfc  newobj   instance void ObjectWithPathName::.ctor()
0x24d01  stloc.3
0x24d02  ldloc.3
0x24d03  ldloc.0
0x24d04  callvirt instance string Microsoft.SharePoint.Client.PropertyInformation::get_Name()
0x24d09  stfld    string ObjectWithPathName::PathName
0x24d0e  ldloc.3
0x24d0f  ldloc.1
0x24d10  ldarg.3
0x24d11  ldarg.s  4
0x24d13  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24d18  ldarg.0
0x24d19  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24d1e  callvirt instance object Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object obj, string propertyName, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x24d23  stfld    object ObjectWithPathName::Value
0x24d28  ldloc.3
0x24d29  ldc.i4.2
0x24d2a  stfld    valuetype ObjectResultType ObjectWithPathName::ResultType
0x24d2f  ldloc.3
0x24d30  ret
0x24d31  ldarg.3
0x24d32  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x24d37  ldarg.0
0x24d38  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24d3d  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x24d42  stloc.s  4
0x24d44  ldloc.s  4
0x24d46  brtrue.s loc_24D56
0x24d48  ldarg.0
0x24d49  ldarg.s  4
0x24d4b  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24d50  call     instance class Microsoft.SharePoint.Client.ResourceNotFoundException Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateResourceNotFoundException(string resource)
0x24d55  throw
0x24d56  ldnull
0x24d57  stloc.s  5
0x24d59  ldarg.s  4
0x24d5b  callvirt instance valuetype Microsoft.SharePoint.Client.Rest.EdmParserNodeType Microsoft.SharePoint.Client.Rest.EdmParserNode::get_NodeType()
0x24d60  ldc.i4.1
0x24d61  bne.un   loc_24FCC
0x24d66  ldarg.1
0x24d67  brfalse.s loc_24D8D
0x24d69  ldarg.s  5
0x24d6b  brfalse.s loc_24D8D
0x24d6d  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x24d72  ldarg.0
0x24d73  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x24d78  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_Query(class Microsoft.SharePoint.Client.RESTfulQuery value)
0x24d7d  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x24d82  ldarg.0
0x24d83  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x24d88  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_RelativeQuery(class Microsoft.SharePoint.Client.RESTfulQuery value)
0x24d8d  ldarg.s  4
0x24d8f  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24d94  ldstr    aApi// "$api"
0x24d99  ldc.i4.5
0x24d9a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24d9f  brfalse.s loc_24DDE
0x24da1  ldarg.0
0x24da2  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CheckApiMetadataEnabled()
0x24da7  newobj   instance void ObjectWithPathName::.ctor()
0x24dac  stloc.s  7
0x24dae  ldloc.s  7
0x24db0  ldstr    aApi_0// "Api"
0x24db5  stfld    string ObjectWithPathName::PathName
0x24dba  ldloc.s  7
0x24dbc  ldarg.0
0x24dbd  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24dc2  call     class Microsoft.SharePoint.Client.ApiMetadataBuilder Microsoft.SharePoint.Client.ApiMetadataBuilder::GetInstance(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x24dc7  ldloc.s  4
0x24dc9  callvirt instance class Microsoft.SharePoint.Client.TypeInformation Microsoft.SharePoint.Client.ApiMetadataBuilder::GetTypeInformation(class Microsoft.SharePoint.Client.ServerStub serverStub)
0x24dce  stfld    object ObjectWithPathName::Value
0x24dd3  ldloc.s  7
0x24dd5  ldc.i4.0
0x24dd6  stfld    valuetype ObjectResultType ObjectWithPathName::ResultType
0x24ddb  ldloc.s  7
0x24ddd  ret
0x24dde  ldloc.s  4
0x24de0  ldarg.s  4
0x24de2  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24de7  ldarg.0
0x24de8  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24ded  ldloca.s 0
0x24def  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryGetPropertyInfo(string name, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] class Microsoft.SharePoint.Client.PropertyInformation& property)
0x24df4  brfalse.s loc_24E31
0x24df6  newobj   instance void ObjectWithPathName::.ctor()
0x24dfb  stloc.s  8
0x24dfd  ldloc.s  8
0x24dff  ldloc.0
0x24e00  callvirt instance string Microsoft.SharePoint.Client.PropertyInformation::get_Name()
0x24e05  stfld    string ObjectWithPathName::PathName
0x24e0a  ldloc.s  8
0x24e0c  ldloc.s  4
0x24e0e  ldarg.3
0x24e0f  ldarg.s  4
0x24e11  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24e16  ldarg.0
0x24e17  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24e1c  callvirt instance object Microsoft.SharePoint.Client.ServerStub::GetPropertyWithMonitoredScope(object target, string propertyName, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x24e21  stfld    object ObjectWithPathName::Value
0x24e26  ldloc.s  8
0x24e28  ldc.i4.2
0x24e29  stfld    valuetype ObjectResultType ObjectWithPathName::ResultType
0x24e2e  ldloc.s  8
0x24e30  ret
0x24e31  ldarg.0
0x24e32  ldloc.s  4
0x24e34  ldarg.s  4
0x24e36  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24e3b  ldarg.s  6
0x24e3d  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryGetMethodInfo(class Microsoft.SharePoint.Client.ServerStub serverStub, string name, [out] class Microsoft.SharePoint.Client.MethodInformation& method)
0x24e42  brfalse.s loc_24E59
0x24e44  ldarg.0
0x24e45  ldarg.1
0x24e46  ldarg.3
0x24e47  ldloc.s  4
0x24e49  ldarg.s  4
0x24e4b  ldarg.s  5
0x24e4d  ldarg.s  6
0x24e4f  ldind.ref
0x24e50  ldc.i4.0
0x24e51  ldc.i4.0
0x24e52  ldc.i4.1
0x24e53  call     instance class ObjectWithPathName Microsoft.SharePoint.Client.Rest.RestRequestProcessor::InvokeMethod(bool mainRequestPath, object value, class Microsoft.SharePoint.Client.ServerStub serverProxy, class Microsoft.SharePoint.Client.Rest.EdmParserNode node, bool resourceEndpoint, class Microsoft.SharePoint.Client.MethodInformation methodInfo, bool isExtensionMethod, bool isIndexerMethod, bool useArgumentNode)
0x24e58  ret
0x24e59  ldloc.s  4
0x24e5b  ldarg.3
0x24e5c  ldarg.s  4
0x24e5e  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24e63  ldarg.0
0x24e64  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x24e69  ldloca.s 6
0x24e6b  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryGetObjectFromUrlPathSegmentWithMonitoredScope(object value, string pathSegment, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] object& result)
0x24e70  brfalse.s loc_24E9B
0x24e72  newobj   instance void ObjectWithPathName::.ctor()
0x24e77  stloc.s  9
0x24e79  ldloc.s  9
0x24e7b  ldarg.s  4
0x24e7d  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24e82  stfld    string ObjectWithPathName::PathName
0x24e87  ldloc.s  9
0x24e89  ldloc.s  6
0x24e8b  stfld    object ObjectWithPathName::Value
0x24e90  ldloc.s  9
0x24e92  ldc.i4.2
0x24e93  stfld    valuetype ObjectResultType ObjectWithPathName::ResultType
0x24e98  ldloc.s  9
0x24e9a  ret
0x24e9b  ldarg.0
0x24e9c  ldloc.s  4
0x24e9e  ldarg.s  4
0x24ea0  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24ea5  ldloca.s 5
0x24ea7  ldarg.s  6
0x24ea9  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryGetStaticExtensionMethod(class Microsoft.SharePoint.Client.ServerStub parameterServerStub, string methodName, [out] class Microsoft.SharePoint.Client.ServerStub& staticMethodServerProxy, [out] class Microsoft.SharePoint.Client.MethodInformation& methodInfo)
0x24eae  brfalse.s loc_24EC5
0x24eb0  ldarg.0
0x24eb1  ldarg.1
0x24eb2  ldarg.3
0x24eb3  ldloc.s  5
0x24eb5  ldarg.s  4
0x24eb7  ldarg.s  5
0x24eb9  ldarg.s  6
0x24ebb  ldind.ref
0x24ebc  ldc.i4.1
0x24ebd  ldc.i4.0
0x24ebe  ldc.i4.1
0x24ebf  call     instance class ObjectWithPathName Microsoft.SharePoint.Client.Rest.RestRequestProcessor::InvokeMethod(bool mainRequestPath, object value, class Microsoft.SharePoint.Client.ServerStub serverProxy, class Microsoft.SharePoint.Client.Rest.EdmParserNode node, bool resourceEndpoint, class Microsoft.SharePoint.Client.MethodInformation methodInfo, bool isExtensionMethod, bool isIndexerMethod, bool useArgumentNode)
0x24ec4  ret
0x24ec5  ldarg.s  5
0x24ec7  brfalse  loc_24FBE
0x24ecc  ldloc.s  4
0x24ece  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x24ed3  brfalse  loc_24FBE
0x24ed8  ldarg.s  4
0x24eda  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24edf  ldarg.0
0x24ee0  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24ee5  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStubForEdmTypeName(string edmTypeName, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x24eea  brfalse  loc_24FBE
0x24eef  ldarg.s  4
0x24ef1  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24ef6  ldarg.0
0x24ef7  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24efc  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStubForEdmTypeName(string edmTypeName, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x24f01  stloc.s  0xA
0x24f03  ldloc.s  4
0x24f05  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x24f0a  ldloc.s  0xA
0x24f0c  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x24f11  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x24f16  brtrue.s loc_24F88
0x24f18  ldarg.0
0x24f19  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24f1e  ldc.i4   0x1C5101
0x24f23  ldc.i4.1
0x24f24  ldstr    aTheType0ForEdm// "The type {0} for edm type {1} is not a "...
0x24f29  ldc.i4.3
0x24f2a  newarr   [mscorlib]System.Object
0x24f2f  stloc.s  0x14
0x24f31  ldloc.s  0x14
0x24f33  ldc.i4.0
0x24f34  ldloc.s  0xA
0x24f36  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x24f3b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x24f40  stelem.ref
0x24f41  ldloc.s  0x14
0x24f43  ldc.i4.1
0x24f44  ldarg.s  4
0x24f46  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24f4b  stelem.ref
0x24f4c  ldloc.s  0x14
0x24f4e  ldc.i4.2
0x24f4f  ldloc.s  4
0x24f51  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x24f56  callvirt instance string [mscorlib]System.Type::get_FullName()
0x24f5b  stelem.ref
0x24f5c  ldloc.s  0x14
0x24f5e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x24f63  ldstr    aRestInvalidtyp// "REST_InvalidTypeOf"
0x24f68  ldc.i4.1
0x24f69  newarr   [mscorlib]System.Object
0x24f6e  stloc.s  0x15
0x24f70  ldloc.s  0x15
0x24f72  ldc.i4.0
0x24f73  ldarg.s  4
0x24f75  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x24f7a  stelem.ref
0x24f7b  ldloc.s  0x15
0x24f7d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x24f82  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x24f87  throw
0x24f88  newobj   instance void ObjectWithPathName::.ctor()
  ... truncated ...
```
