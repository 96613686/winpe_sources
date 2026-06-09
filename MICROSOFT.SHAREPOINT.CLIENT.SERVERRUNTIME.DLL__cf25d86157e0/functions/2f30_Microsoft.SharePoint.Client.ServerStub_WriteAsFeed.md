# Microsoft.SharePoint.Client.ServerStub::WriteAsFeed

- ea: `0x2f30`
- end: `0x312f`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteAsFeed`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x2d70`

## callees

- `0x1f10`
- `0x2930`
- `0x2cd0`
- `0x2d70`
- `0x2f30`
- `0x15030`
- `0x152f0`
- `0x16920`
- `0x180b0`
- `0x184e0`
- `0x1d450`
- `0x1d670`
- `0x21610`
- `0x217d0`
- `0x217e0`
- `0x217f0`
- `0x21800`
- `0x21810`
- `0x21820`
- `0x21840`
- `0x29960`
- `0x29980`
- `0x299a0`

## string_xrefs

- `0x3059`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.0
0x2f31  ldarg.1
0x2f32  ldarg.3
0x2f33  callvirt instance class Microsoft.SharePoint.Client.RESTfulQueryResult Microsoft.SharePoint.Client.ServerStub::GetRESTfulQueryResult(object target, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x2f38  stloc.1
0x2f39  ldloc.1
0x2f3a  brtrue.s loc_2F6B
0x2f3c  ldarg.0
0x2f3d  ldarg.1
0x2f3e  ldarg.3
0x2f3f  callvirt instance void Microsoft.SharePoint.Client.ServerStub::OnRESTfulQuerying(object obj, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x2f44  ldarg.1
0x2f45  isinst   [mscorlib]System.Collections.IEnumerable
0x2f4a  stloc.0
0x2f4b  ldloc.0
0x2f4c  brfalse.s loc_2F6D
0x2f4e  ldarg.3
0x2f4f  callvirt instance class Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression Microsoft.SharePoint.Client.RESTfulQuery::get_QueryableExpression()
0x2f54  stloc.2
0x2f55  ldloc.2
0x2f56  brtrue.s loc_2F5E
0x2f58  newobj   instance void Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression::.ctor()
0x2f5d  stloc.2
0x2f5e  ldarg.0
0x2f5f  ldloc.0
0x2f60  ldloc.2
0x2f61  ldarg.s  4
0x2f63  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.SharePoint.Client.ServerStub::Process(class [mscorlib]System.Collections.IEnumerable objEnum, class Microsoft.SharePoint.Client.ClientQueryableExpression expression, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2f68  stloc.0
0x2f69  br.s     loc_2F6D
0x2f6b  ldloc.1
0x2f6c  stloc.0
0x2f6d  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::.ctor()
0x2f72  stloc.3
0x2f73  ldloc.3
0x2f74  call     string Microsoft.SharePoint.Client.Utility::GetUniqueODataId()
0x2f79  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Id(string)
0x2f7e  ldarg.s  4
0x2f80  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x2f85  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x2f8a  brfalse.s loc_2F96
0x2f8c  ldarg.3
0x2f8d  ldloc.3
0x2f8e  ldarg.1
0x2f8f  ldarg.s  4
0x2f91  call     void Microsoft.SharePoint.Client.Rest.JsonLightUtility::LightupJsonLightWriter(class Microsoft.SharePoint.Client.RESTfulQuery query, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed feed, object entity, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2f96  ldloc.0
0x2f97  brfalse  loc_3040
0x2f9c  ldarg.3
0x2f9d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2fa2  stloc.s  0xB
0x2fa4  ldloca.s 0xB
0x2fa6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2fab  brfalse  loc_3040
0x2fb0  ldarg.3
0x2fb1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x2fb6  stloc.s  0xC
0x2fb8  ldloca.s 0xC
0x2fba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2fbf  brfalse.s loc_3040
0x2fc1  ldloc.1
0x2fc2  brfalse.s loc_2FF1
0x2fc4  ldloc.1
0x2fc5  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Client.RESTfulQueryResult::get_InlineCount()
0x2fca  stloc.s  0xD
0x2fcc  ldloca.s 0xD
0x2fce  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x2fd3  brfalse.s loc_2FF1
0x2fd5  ldloc.3
0x2fd6  ldloc.1
0x2fd7  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Client.RESTfulQueryResult::get_InlineCount()
0x2fdc  stloc.s  0xE
0x2fde  ldloca.s 0xE
0x2fe0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x2fe5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x2fea  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Count(valuetype [mscorlib]System.Nullable`1<int64>)
0x2fef  br.s     loc_3040
0x2ff1  ldc.i4.0
0x2ff2  conv.i8
0x2ff3  stloc.s  4
0x2ff5  ldloc.0
0x2ff6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2ffb  stloc.s  0xF
0x2ffd  br.s     loc_3013
0x2fff  ldloc.s  0xF
0x3001  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3006  stloc.s  5
0x3008  ldloc.s  5
0x300a  brfalse.s loc_3013
0x300c  ldloc.s  4
0x300e  ldc.i4.1
0x300f  conv.i8
0x3010  add
0x3011  stloc.s  4
0x3013  ldloc.s  0xF
0x3015  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x301a  brtrue.s loc_2FFF
0x301c  leave.s  loc_3033
0x301e  ldloc.s  0xF
0x3020  isinst   [mscorlib]System.IDisposable
0x3025  stloc.s  0x10
0x3027  ldloc.s  0x10
0x3029  brfalse.s loc_3032
0x302b  ldloc.s  0x10
0x302d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3032  endfinally
0x3033  ldloc.3
0x3034  ldloc.s  4
0x3036  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x303b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Count(valuetype [mscorlib]System.Nullable`1<int64>)
0x3040  ldloc.1
0x3041  brfalse.s loc_307E
0x3043  ldloc.1
0x3044  callvirt instance string Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextPageSkipToken()
0x3049  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x304e  brtrue.s loc_307E
0x3050  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x3055  stloc.s  6
0x3057  ldloc.s  6
0x3059  ldstr    aSkiptoken// "$skiptoken"
0x305e  ldloc.1
0x305f  callvirt instance string Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextPageSkipToken()
0x3064  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x3069  ldarg.s  4
0x306b  ldloc.s  6
0x306d  call     class [System]System.Uri Microsoft.SharePoint.Client.Utility::GetCurrentRestUri(class Microsoft.SharePoint.Client.ProxyContext proxyContext, class [System]System.Collections.Specialized.NameValueCollection overrideQueryStrings)
0x3072  stloc.s  7
0x3074  ldloc.3
0x3075  ldloc.s  7
0x3077  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_NextPageLink(class [System]System.Uri)
0x307c  br.s     loc_309B
0x307e  ldloc.1
0x307f  brfalse.s loc_309B
0x3081  ldloc.1
0x3082  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextLink()
0x3087  ldnull
0x3088  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x308d  brfalse.s loc_309B
0x308f  ldloc.3
0x3090  ldloc.1
0x3091  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextLink()
0x3096  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_NextPageLink(class [System]System.Uri)
0x309b  ldarg.2
0x309c  ldloc.3
0x309d  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed)
0x30a2  ldloc.0
0x30a3  brfalse  loc_3128
0x30a8  newobj   instance void Microsoft.SharePoint.Client.RESTfulQuery::.ctor()
0x30ad  stloc.s  8
0x30af  ldloc.s  8
0x30b1  ldarg.3
0x30b2  callvirt instance class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RESTfulQuery::get_Expand()
0x30b7  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Expand(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x30bc  ldloc.s  8
0x30be  ldarg.3
0x30bf  callvirt instance class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RESTfulQuery::get_Select()
0x30c4  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Select(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x30c9  ldloc.0
0x30ca  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x30cf  stloc.s  0x11
0x30d1  br.s     loc_3108
0x30d3  ldloc.s  0x11
0x30d5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x30da  stloc.s  9
0x30dc  ldloc.s  9
0x30de  brfalse.s loc_3108
0x30e0  ldloc.s  9
0x30e2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x30e7  ldarg.s  4
0x30e9  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x30ee  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x30f3  stloc.s  0xA
0x30f5  ldloc.s  0xA
0x30f7  brfalse.s loc_3108
0x30f9  ldloc.s  0xA
0x30fb  ldloc.s  9
0x30fd  ldnull
0x30fe  ldarg.2
0x30ff  ldloc.s  8
0x3101  ldarg.s  4
0x3103  callvirt instance void Microsoft.SharePoint.Client.ServerStub::Write(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3108  ldloc.s  0x11
0x310a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x310f  brtrue.s loc_30D3
0x3111  leave.s  loc_3128
0x3113  ldloc.s  0x11
0x3115  isinst   [mscorlib]System.IDisposable
0x311a  stloc.s  0x12
0x311c  ldloc.s  0x12
0x311e  brfalse.s loc_3127
0x3120  ldloc.s  0x12
0x3122  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3127  endfinally
0x3128  ldarg.2
0x3129  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x312e  ret
```
