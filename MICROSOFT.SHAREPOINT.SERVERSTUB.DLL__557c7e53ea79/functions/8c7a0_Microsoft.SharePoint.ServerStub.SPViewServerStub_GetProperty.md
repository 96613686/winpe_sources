# Microsoft.SharePoint.ServerStub.SPViewServerStub::GetProperty

- ea: `0x8c7a0`
- end: `0x8ceac`
- name: `Microsoft.SharePoint.ServerStub.SPViewServerStub::GetProperty`
- size: `1804`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8c7a0`

## string_xrefs

- `0x8c98e`: `ServerRelativePath`
- `0x8cdb5`: `ServerRelativePath`
- `0x8c8be`: `JSLink`
- `0x8cc53`: `JSLink`
- `0x8c87d`: `HtmlSchemaXml`
- `0x8cbea`: `HtmlSchemaXml`
- `0x8c8cb`: `ListViewXml`
- `0x8cc66`: `ListViewXml`
- `0x8c95a`: `ReadOnlyView`
- `0x8cd55`: `ReadOnlyView`
- `0x8c9c2`: `Threaded`
- `0x8ce06`: `Threaded`
- `0x8c9e9`: `ToolbarTemplateName`
- `0x8ce44`: `ToolbarTemplateName`

## pseudocode

```c

```

## disassembly

```asm
0x8c7a0  ldarg.2
0x8c7a1  brtrue.s loc_8C7AE
0x8c7a3  ldstr    aPropname// "propName"
0x8c7a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c7ad  throw
0x8c7ae  ldarg.3
0x8c7af  brtrue.s loc_8C7BC
0x8c7b1  ldstr    aProxycontext// "proxyContext"
0x8c7b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c7bb  throw
0x8c7bc  ldarg.1
0x8c7bd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPView
0x8c7c2  stloc.0
0x8c7c3  ldloc.0
0x8c7c4  brtrue.s loc_8C7D1
0x8c7c6  ldstr    aTarget// "target"
0x8c7cb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c7d0  throw
0x8c7d1  ldarg.0
0x8c7d2  ldarg.2
0x8c7d3  ldarg.3
0x8c7d4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c7d9  starg.s  2
0x8c7db  ldarg.2
0x8c7dc  dup
0x8c7dd  stloc.1
0x8c7de  brfalse  loc_8CEA2
0x8c7e3  volatile.
0x8c7e5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001787-1
0x8c7ea  brtrue   loc_8CA30
0x8c7ef  ldc.i4.s 0x2C
0x8c7f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8c7f6  dup
0x8c7f7  ldstr    aAggregations// "Aggregations"
0x8c7fc  ldc.i4.0
0x8c7fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c802  dup
0x8c803  ldstr    aAggregationsst// "AggregationsStatus"
0x8c808  ldc.i4.1
0x8c809  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c80e  dup
0x8c80f  ldstr    aBaseviewid_0// "BaseViewId"
0x8c814  ldc.i4.2
0x8c815  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c81a  dup
0x8c81b  ldstr    aColumnwidth// "ColumnWidth"
0x8c820  ldc.i4.3
0x8c821  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c826  dup
0x8c827  ldstr    aContenttypeid_0// "ContentTypeId"
0x8c82c  ldc.i4.4
0x8c82d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c832  dup
0x8c833  ldstr    aCustomformatte// "CustomFormatter"
0x8c838  ldc.i4.5
0x8c839  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c83e  dup
0x8c83f  ldstr    aDefaultview// "DefaultView"
0x8c844  ldc.i4.6
0x8c845  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c84a  dup
0x8c84b  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8c850  ldc.i4.7
0x8c851  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c856  dup
0x8c857  ldstr    aEditormodified// "EditorModified"
0x8c85c  ldc.i4.8
0x8c85d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c862  dup
0x8c863  ldstr    aFormats// "Formats"
0x8c868  ldc.i4.s 9
0x8c86a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c86f  dup
0x8c870  ldstr    aHidden// "Hidden"
0x8c875  ldc.i4.s 0xA
0x8c877  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c87c  dup
0x8c87d  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8c882  ldc.i4.s 0xB
0x8c884  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c889  dup
0x8c88a  ldstr    aId_0// "Id"
0x8c88f  ldc.i4.s 0xC
0x8c891  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c896  dup
0x8c897  ldstr    aImageurl// "ImageUrl"
0x8c89c  ldc.i4.s 0xD
0x8c89e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8a3  dup
0x8c8a4  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8c8a9  ldc.i4.s 0xE
0x8c8ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8b0  dup
0x8c8b1  ldstr    aViewjoins// "ViewJoins"
0x8c8b6  ldc.i4.s 0xF
0x8c8b8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8bd  dup
0x8c8be  ldstr    aJslink// "JSLink"
0x8c8c3  ldc.i4.s 0x10
0x8c8c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8ca  dup
0x8c8cb  ldstr    aListviewxml// "ListViewXml"
0x8c8d0  ldc.i4.s 0x11
0x8c8d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8d7  dup
0x8c8d8  ldstr    aMethod// "Method"
0x8c8dd  ldc.i4.s 0x12
0x8c8df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8e4  dup
0x8c8e5  ldstr    aMobiledefaultv// "MobileDefaultView"
0x8c8ea  ldc.i4.s 0x13
0x8c8ec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8f1  dup
0x8c8f2  ldstr    aMobileview// "MobileView"
0x8c8f7  ldc.i4.s 0x14
0x8c8f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c8fe  dup
0x8c8ff  ldstr    aModerationtype// "ModerationType"
0x8c904  ldc.i4.s 0x15
0x8c906  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c90b  dup
0x8c90c  ldstr    aOrderedview// "OrderedView"
0x8c911  ldc.i4.s 0x16
0x8c913  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c918  dup
0x8c919  ldstr    aPaged// "Paged"
0x8c91e  ldc.i4.s 0x17
0x8c920  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c925  dup
0x8c926  ldstr    aPagerendertype// "PageRenderType"
0x8c92b  ldc.i4.s 0x18
0x8c92d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c932  dup
0x8c933  ldstr    aPersonalview// "PersonalView"
0x8c938  ldc.i4.s 0x19
0x8c93a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c93f  dup
0x8c940  ldstr    aViewprojectedf// "ViewProjectedFields"
0x8c945  ldc.i4.s 0x1A
0x8c947  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c94c  dup
0x8c94d  ldstr    aViewquery// "ViewQuery"
0x8c952  ldc.i4.s 0x1B
0x8c954  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c959  dup
0x8c95a  ldstr    aReadonlyview// "ReadOnlyView"
0x8c95f  ldc.i4.s 0x1C
0x8c961  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c966  dup
0x8c967  ldstr    aRequiresclient// "RequiresClientIntegration"
0x8c96c  ldc.i4.s 0x1D
0x8c96e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c973  dup
0x8c974  ldstr    aRowlimit// "RowLimit"
0x8c979  ldc.i4.s 0x1E
0x8c97b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c980  dup
0x8c981  ldstr    aScope// "Scope"
0x8c986  ldc.i4.s 0x1F
0x8c988  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c98d  dup
0x8c98e  ldstr    aServerrelative_0// "ServerRelativePath"
0x8c993  ldc.i4.s 0x20
0x8c995  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c99a  dup
0x8c99b  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x8c9a0  ldc.i4.s 0x21
0x8c9a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9a7  dup
0x8c9a8  ldstr    aStyleid// "StyleId"
0x8c9ad  ldc.i4.s 0x22
0x8c9af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9b4  dup
0x8c9b5  ldstr    aTabularview// "TabularView"
0x8c9ba  ldc.i4.s 0x23
0x8c9bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9c1  dup
0x8c9c2  ldstr    aThreaded// "Threaded"
0x8c9c7  ldc.i4.s 0x24
0x8c9c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9ce  dup
0x8c9cf  ldstr    aTitle// "Title"
0x8c9d4  ldc.i4.s 0x25
0x8c9d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9db  dup
0x8c9dc  ldstr    aToolbar// "Toolbar"
0x8c9e1  ldc.i4.s 0x26
0x8c9e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9e8  dup
0x8c9e9  ldstr    aToolbartemplat// "ToolbarTemplateName"
0x8c9ee  ldc.i4.s 0x27
0x8c9f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c9f5  dup
0x8c9f6  ldstr    aViewtype// "ViewType"
0x8c9fb  ldc.i4.s 0x28
0x8c9fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8ca02  dup
0x8ca03  ldstr    aViewdata// "ViewData"
0x8ca08  ldc.i4.s 0x29
0x8ca0a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8ca0f  dup
0x8ca10  ldstr    aViewfields// "ViewFields"
0x8ca15  ldc.i4.s 0x2A
0x8ca17  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8ca1c  dup
0x8ca1d  ldstr    aVisualizationi// "VisualizationInfo"
0x8ca22  ldc.i4.s 0x2B
0x8ca24  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8ca29  volatile.
0x8ca2b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001787-1
0x8ca30  volatile.
0x8ca32  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001787-1
0x8ca37  ldloc.1
0x8ca38  ldloca.s 2
0x8ca3a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8ca3f  brfalse  loc_8CEA2
0x8ca44  ldloc.2
0x8ca45  switch   loc_8CAFF, loc_8CB12, loc_8CB25, loc_8CB38, loc_8CB4B, loc_8CB63, loc_8CB76, loc_8CB8E, loc_8CBA6, loc_8CBBE, loc_8CBD1, loc_8CBE9, loc_8CBFC, loc_8CC14, loc_8CC27, loc_8CC3F, loc_8CC52, loc_8CC65, loc_8CC78, loc_8CC8B, loc_8CCA3, loc_8CCBB, loc_8CCCE, loc_8CCE6, loc_8CCFE, loc_8CD16, loc_8CD2E, loc_8CD41, loc_8CD54, loc_8CD6C, loc_8CD84, loc_8CD9C, loc_8CDB4, loc_8CDC7, loc_8CDDA, loc_8CDED, loc_8CE05, loc_8CE1D, loc_8CE30, loc_8CE43, loc_8CE56, loc_8CE69, loc_8CE7C, loc_8CE8F
0x8cafa  br       loc_8CEA2
0x8caff  ldarg.0
0x8cb00  ldstr    aAggregations// "Aggregations"
0x8cb05  ldarg.3
0x8cb06  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb0b  ldloc.0
0x8cb0c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Aggregations()
0x8cb11  ret
0x8cb12  ldarg.0
0x8cb13  ldstr    aAggregationsst// "AggregationsStatus"
0x8cb18  ldarg.3
0x8cb19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb1e  ldloc.0
0x8cb1f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_AggregationsStatus()
0x8cb24  ret
0x8cb25  ldarg.0
0x8cb26  ldstr    aBaseviewid_0// "BaseViewId"
0x8cb2b  ldarg.3
0x8cb2c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb31  ldloc.0
0x8cb32  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_BaseViewID()
0x8cb37  ret
0x8cb38  ldarg.0
0x8cb39  ldstr    aColumnwidth// "ColumnWidth"
0x8cb3e  ldarg.3
0x8cb3f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb44  ldloc.0
0x8cb45  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ColumnWidth()
0x8cb4a  ret
0x8cb4b  ldarg.0
0x8cb4c  ldstr    aContenttypeid_0// "ContentTypeId"
0x8cb51  ldarg.3
0x8cb52  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb57  ldloc.0
0x8cb58  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ContentTypeId()
0x8cb5d  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x8cb62  ret
0x8cb63  ldarg.0
0x8cb64  ldstr    aCustomformatte// "CustomFormatter"
0x8cb69  ldarg.3
0x8cb6a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb6f  ldloc.0
0x8cb70  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_CustomFormatter()
0x8cb75  ret
0x8cb76  ldarg.0
0x8cb77  ldstr    aDefaultview// "DefaultView"
0x8cb7c  ldarg.3
0x8cb7d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb82  ldloc.0
0x8cb83  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_DefaultView()
0x8cb88  box      [mscorlib]System.Boolean
0x8cb8d  ret
0x8cb8e  ldarg.0
0x8cb8f  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8cb94  ldarg.3
0x8cb95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cb9a  ldloc.0
0x8cb9b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_DefaultViewForContentType()
0x8cba0  box      [mscorlib]System.Boolean
0x8cba5  ret
0x8cba6  ldarg.0
0x8cba7  ldstr    aEditormodified// "EditorModified"
0x8cbac  ldarg.3
0x8cbad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cbb2  ldloc.0
0x8cbb3  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_EditorModified()
0x8cbb8  box      [mscorlib]System.Boolean
0x8cbbd  ret
0x8cbbe  ldarg.0
0x8cbbf  ldstr    aFormats// "Formats"
0x8cbc4  ldarg.3
0x8cbc5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cbca  ldloc.0
0x8cbcb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Formats()
0x8cbd0  ret
0x8cbd1  ldarg.0
0x8cbd2  ldstr    aHidden// "Hidden"
0x8cbd7  ldarg.3
0x8cbd8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cbdd  ldloc.0
0x8cbde  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Hidden()
0x8cbe3  box      [mscorlib]System.Boolean
  ... truncated ...
```
