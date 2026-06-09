# Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsFeed

- ea: `0x1f560`
- end: `0x1f7bc`
- name: `Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsFeed`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x1f3a0`

## callees

- `0x1f10`
- `0x2930`
- `0x2cd0`
- `0x15030`
- `0x152f0`
- `0x16920`
- `0x180b0`
- `0x184e0`
- `0x1d450`
- `0x1d670`
- `0x1f3a0`
- `0x1f560`
- `0x1fc70`
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
- `0x299c0`

## string_xrefs

- `0x1f689`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x1f560  ldarg.1
0x1f561  ldarg.0
0x1f562  ldarg.3
0x1f563  callvirt instance class Microsoft.SharePoint.Client.RESTfulQueryResult Microsoft.SharePoint.Client.ServerStub::GetRESTfulQueryResult(object target, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x1f568  stloc.1
0x1f569  ldloc.1
0x1f56a  brtrue.s loc_1F59B
0x1f56c  ldarg.1
0x1f56d  ldarg.0
0x1f56e  ldarg.3
0x1f56f  callvirt instance void Microsoft.SharePoint.Client.ServerStub::OnRESTfulQuerying(object obj, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x1f574  ldarg.0
0x1f575  isinst   [mscorlib]System.Collections.IEnumerable
0x1f57a  stloc.0
0x1f57b  ldloc.0
0x1f57c  brfalse.s loc_1F59D
0x1f57e  ldarg.3
0x1f57f  callvirt instance class Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression Microsoft.SharePoint.Client.RESTfulQuery::get_QueryableExpression()
0x1f584  stloc.2
0x1f585  ldloc.2
0x1f586  brtrue.s loc_1F58E
0x1f588  newobj   instance void Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression::.ctor()
0x1f58d  stloc.2
0x1f58e  ldarg.1
0x1f58f  ldloc.0
0x1f590  ldloc.2
0x1f591  ldarg.s  4
0x1f593  callvirt instance class [mscorlib]System.Collections.IEnumerable Microsoft.SharePoint.Client.ServerStub::Process(class [mscorlib]System.Collections.IEnumerable objEnum, class Microsoft.SharePoint.Client.ClientQueryableExpression expression, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f598  stloc.0
0x1f599  br.s     loc_1F59D
0x1f59b  ldloc.1
0x1f59c  stloc.0
0x1f59d  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::.ctor()
0x1f5a2  stloc.3
0x1f5a3  ldloc.3
0x1f5a4  call     string Microsoft.SharePoint.Client.Utility::GetUniqueODataId()
0x1f5a9  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Id(string)
0x1f5ae  ldarg.s  4
0x1f5b0  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x1f5b5  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x1f5ba  brfalse.s loc_1F5C6
0x1f5bc  ldarg.3
0x1f5bd  ldloc.3
0x1f5be  ldarg.0
0x1f5bf  ldarg.s  4
0x1f5c1  call     void Microsoft.SharePoint.Client.Rest.JsonLightUtility::LightupJsonLightWriter(class Microsoft.SharePoint.Client.RESTfulQuery query, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed feed, object entity, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f5c6  ldloc.0
0x1f5c7  brfalse  loc_1F670
0x1f5cc  ldarg.3
0x1f5cd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f5d2  stloc.s  0xC
0x1f5d4  ldloca.s 0xC
0x1f5d6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1f5db  brfalse  loc_1F670
0x1f5e0  ldarg.3
0x1f5e1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RESTfulQuery::get_InlineCount()
0x1f5e6  stloc.s  0xD
0x1f5e8  ldloca.s 0xD
0x1f5ea  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1f5ef  brfalse.s loc_1F670
0x1f5f1  ldloc.1
0x1f5f2  brfalse.s loc_1F621
0x1f5f4  ldloc.1
0x1f5f5  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Client.RESTfulQueryResult::get_InlineCount()
0x1f5fa  stloc.s  0xE
0x1f5fc  ldloca.s 0xE
0x1f5fe  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x1f603  brfalse.s loc_1F621
0x1f605  ldloc.3
0x1f606  ldloc.1
0x1f607  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Client.RESTfulQueryResult::get_InlineCount()
0x1f60c  stloc.s  0xF
0x1f60e  ldloca.s 0xF
0x1f610  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x1f615  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x1f61a  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Count(valuetype [mscorlib]System.Nullable`1<int64>)
0x1f61f  br.s     loc_1F670
0x1f621  ldc.i4.0
0x1f622  conv.i8
0x1f623  stloc.s  4
0x1f625  ldloc.0
0x1f626  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1f62b  stloc.s  0x10
0x1f62d  br.s     loc_1F643
0x1f62f  ldloc.s  0x10
0x1f631  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f636  stloc.s  5
0x1f638  ldloc.s  5
0x1f63a  brfalse.s loc_1F643
0x1f63c  ldloc.s  4
0x1f63e  ldc.i4.1
0x1f63f  conv.i8
0x1f640  add
0x1f641  stloc.s  4
0x1f643  ldloc.s  0x10
0x1f645  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f64a  brtrue.s loc_1F62F
0x1f64c  leave.s  loc_1F663
0x1f64e  ldloc.s  0x10
0x1f650  isinst   [mscorlib]System.IDisposable
0x1f655  stloc.s  0x11
0x1f657  ldloc.s  0x11
0x1f659  brfalse.s loc_1F662
0x1f65b  ldloc.s  0x11
0x1f65d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f662  endfinally
0x1f663  ldloc.3
0x1f664  ldloc.s  4
0x1f666  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x1f66b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_Count(valuetype [mscorlib]System.Nullable`1<int64>)
0x1f670  ldloc.1
0x1f671  brfalse.s loc_1F6AE
0x1f673  ldloc.1
0x1f674  callvirt instance string Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextPageSkipToken()
0x1f679  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f67e  brtrue.s loc_1F6AE
0x1f680  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x1f685  stloc.s  6
0x1f687  ldloc.s  6
0x1f689  ldstr    aSkiptoken// "$skiptoken"
0x1f68e  ldloc.1
0x1f68f  callvirt instance string Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextPageSkipToken()
0x1f694  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1f699  ldarg.s  4
0x1f69b  ldloc.s  6
0x1f69d  call     class [System]System.Uri Microsoft.SharePoint.Client.Utility::GetCurrentRestUri(class Microsoft.SharePoint.Client.ProxyContext proxyContext, class [System]System.Collections.Specialized.NameValueCollection overrideQueryStrings)
0x1f6a2  stloc.s  7
0x1f6a4  ldloc.3
0x1f6a5  ldloc.s  7
0x1f6a7  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_NextPageLink(class [System]System.Uri)
0x1f6ac  br.s     loc_1F6CB
0x1f6ae  ldloc.1
0x1f6af  brfalse.s loc_1F6CB
0x1f6b1  ldloc.1
0x1f6b2  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextLink()
0x1f6b7  ldnull
0x1f6b8  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1f6bd  brfalse.s loc_1F6CB
0x1f6bf  ldloc.3
0x1f6c0  ldloc.1
0x1f6c1  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_NextLink()
0x1f6c6  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_NextPageLink(class [System]System.Uri)
0x1f6cb  ldloc.1
0x1f6cc  brfalse.s loc_1F6E8
0x1f6ce  ldloc.1
0x1f6cf  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_DeltaLink()
0x1f6d4  ldnull
0x1f6d5  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1f6da  brfalse.s loc_1F6E8
0x1f6dc  ldloc.3
0x1f6dd  ldloc.1
0x1f6de  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulQueryResult::get_DeltaLink()
0x1f6e3  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::set_DeltaLink(class [System]System.Uri)
0x1f6e8  ldarg.0
0x1f6e9  ldarg.1
0x1f6ea  ldarg.s  4
0x1f6ec  ldnull
0x1f6ed  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::GetODataInstanceAnnotations(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [opt] class [mscorlib]System.Func`2<string, bool> shouldReturnAnnotation)
0x1f6f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::GetEnumerator()
0x1f6f7  stloc.s  0x12
0x1f6f9  br.s     loc_1F711
0x1f6fb  ldloc.s  0x12
0x1f6fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::get_Current()
0x1f702  stloc.s  8
0x1f704  ldloc.3
0x1f705  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed::get_InstanceAnnotations()
0x1f70a  ldloc.s  8
0x1f70c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x1f711  ldloc.s  0x12
0x1f713  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f718  brtrue.s loc_1F6FB
0x1f71a  leave.s  loc_1F728
0x1f71c  ldloc.s  0x12
0x1f71e  brfalse.s loc_1F727
0x1f720  ldloc.s  0x12
0x1f722  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f727  endfinally
0x1f728  ldarg.2
0x1f729  ldloc.3
0x1f72a  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed)
0x1f72f  ldloc.0
0x1f730  brfalse  loc_1F7B5
0x1f735  newobj   instance void Microsoft.SharePoint.Client.RESTfulQuery::.ctor()
0x1f73a  stloc.s  9
0x1f73c  ldloc.s  9
0x1f73e  ldarg.3
0x1f73f  callvirt instance class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RESTfulQuery::get_Expand()
0x1f744  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Expand(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x1f749  ldloc.s  9
0x1f74b  ldarg.3
0x1f74c  callvirt instance class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RESTfulQuery::get_Select()
0x1f751  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Select(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x1f756  ldloc.0
0x1f757  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1f75c  stloc.s  0x13
0x1f75e  br.s     loc_1F795
0x1f760  ldloc.s  0x13
0x1f762  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f767  stloc.s  0xA
0x1f769  ldloc.s  0xA
0x1f76b  brfalse.s loc_1F795
0x1f76d  ldloc.s  0xA
0x1f76f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1f774  ldarg.s  4
0x1f776  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f77b  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x1f780  stloc.s  0xB
0x1f782  ldloc.s  0xB
0x1f784  brfalse.s loc_1F795
0x1f786  ldloc.s  0xA
0x1f788  ldloc.s  0xB
0x1f78a  ldnull
0x1f78b  ldarg.2
0x1f78c  ldloc.s  9
0x1f78e  ldarg.s  4
0x1f790  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::Write(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f795  ldloc.s  0x13
0x1f797  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f79c  brtrue.s loc_1F760
0x1f79e  leave.s  loc_1F7B5
0x1f7a0  ldloc.s  0x13
0x1f7a2  isinst   [mscorlib]System.IDisposable
0x1f7a7  stloc.s  0x14
0x1f7a9  ldloc.s  0x14
0x1f7ab  brfalse.s loc_1F7B4
0x1f7ad  ldloc.s  0x14
0x1f7af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f7b4  endfinally
0x1f7b5  ldarg.2
0x1f7b6  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x1f7bb  ret
```
