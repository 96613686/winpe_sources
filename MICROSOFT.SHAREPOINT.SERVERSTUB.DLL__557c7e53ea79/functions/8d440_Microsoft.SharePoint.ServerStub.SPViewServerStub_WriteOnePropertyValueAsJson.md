# Microsoft.SharePoint.ServerStub.SPViewServerStub::WriteOnePropertyValueAsJson

- ea: `0x8d440`
- end: `0x8e447`
- name: `Microsoft.SharePoint.ServerStub.SPViewServerStub::WriteOnePropertyValueAsJson`
- size: `4103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8d440`

## string_xrefs

- `0x8d60f`: `ServerRelativePath`
- `0x8e0e9`: `ServerRelativePath`
- `0x8d53f`: `JSLink`
- `0x8dc49`: `JSLink`
- `0x8d4fe`: `HtmlSchemaXml`
- `0x8dad7`: `HtmlSchemaXml`
- `0x8d54c`: `ListViewXml`
- `0x8dc93`: `ListViewXml`
- `0x8d5db`: `ReadOnlyView`
- `0x8dfc1`: `ReadOnlyView`
- `0x8d643`: `Threaded`
- `0x8e211`: `Threaded`
- `0x8d66a`: `ToolbarTemplateName`
- `0x8e2ef`: `ToolbarTemplateName`

## pseudocode

```c

```

## disassembly

```asm
0x8d440  ldc.i4.0
0x8d441  stloc.0
0x8d442  ldarg.2
0x8d443  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPView
0x8d448  stloc.1
0x8d449  ldloc.1
0x8d44a  brtrue.s loc_8D457
0x8d44c  ldstr    aTarget// "target"
0x8d451  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8d456  throw
0x8d457  ldarg.3
0x8d458  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x8d45d  dup
0x8d45e  stloc.2
0x8d45f  brfalse  loc_8E439
0x8d464  volatile.
0x8d466  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600178b-1
0x8d46b  brtrue   loc_8D6B1
0x8d470  ldc.i4.s 0x2C
0x8d472  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8d477  dup
0x8d478  ldstr    aAggregations// "Aggregations"
0x8d47d  ldc.i4.0
0x8d47e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d483  dup
0x8d484  ldstr    aAggregationsst// "AggregationsStatus"
0x8d489  ldc.i4.1
0x8d48a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d48f  dup
0x8d490  ldstr    aBaseviewid_0// "BaseViewId"
0x8d495  ldc.i4.2
0x8d496  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d49b  dup
0x8d49c  ldstr    aColumnwidth// "ColumnWidth"
0x8d4a1  ldc.i4.3
0x8d4a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4a7  dup
0x8d4a8  ldstr    aContenttypeid_0// "ContentTypeId"
0x8d4ad  ldc.i4.4
0x8d4ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4b3  dup
0x8d4b4  ldstr    aCustomformatte// "CustomFormatter"
0x8d4b9  ldc.i4.5
0x8d4ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4bf  dup
0x8d4c0  ldstr    aDefaultview// "DefaultView"
0x8d4c5  ldc.i4.6
0x8d4c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4cb  dup
0x8d4cc  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8d4d1  ldc.i4.7
0x8d4d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4d7  dup
0x8d4d8  ldstr    aEditormodified// "EditorModified"
0x8d4dd  ldc.i4.8
0x8d4de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4e3  dup
0x8d4e4  ldstr    aFormats// "Formats"
0x8d4e9  ldc.i4.s 9
0x8d4eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4f0  dup
0x8d4f1  ldstr    aHidden// "Hidden"
0x8d4f6  ldc.i4.s 0xA
0x8d4f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d4fd  dup
0x8d4fe  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8d503  ldc.i4.s 0xB
0x8d505  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d50a  dup
0x8d50b  ldstr    aId_0// "Id"
0x8d510  ldc.i4.s 0xC
0x8d512  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d517  dup
0x8d518  ldstr    aImageurl// "ImageUrl"
0x8d51d  ldc.i4.s 0xD
0x8d51f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d524  dup
0x8d525  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8d52a  ldc.i4.s 0xE
0x8d52c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d531  dup
0x8d532  ldstr    aViewjoins// "ViewJoins"
0x8d537  ldc.i4.s 0xF
0x8d539  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d53e  dup
0x8d53f  ldstr    aJslink// "JSLink"
0x8d544  ldc.i4.s 0x10
0x8d546  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d54b  dup
0x8d54c  ldstr    aListviewxml// "ListViewXml"
0x8d551  ldc.i4.s 0x11
0x8d553  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d558  dup
0x8d559  ldstr    aMethod// "Method"
0x8d55e  ldc.i4.s 0x12
0x8d560  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d565  dup
0x8d566  ldstr    aMobiledefaultv// "MobileDefaultView"
0x8d56b  ldc.i4.s 0x13
0x8d56d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d572  dup
0x8d573  ldstr    aMobileview// "MobileView"
0x8d578  ldc.i4.s 0x14
0x8d57a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d57f  dup
0x8d580  ldstr    aModerationtype// "ModerationType"
0x8d585  ldc.i4.s 0x15
0x8d587  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d58c  dup
0x8d58d  ldstr    aOrderedview// "OrderedView"
0x8d592  ldc.i4.s 0x16
0x8d594  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d599  dup
0x8d59a  ldstr    aPaged// "Paged"
0x8d59f  ldc.i4.s 0x17
0x8d5a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5a6  dup
0x8d5a7  ldstr    aPagerendertype// "PageRenderType"
0x8d5ac  ldc.i4.s 0x18
0x8d5ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5b3  dup
0x8d5b4  ldstr    aPersonalview// "PersonalView"
0x8d5b9  ldc.i4.s 0x19
0x8d5bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5c0  dup
0x8d5c1  ldstr    aViewprojectedf// "ViewProjectedFields"
0x8d5c6  ldc.i4.s 0x1A
0x8d5c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5cd  dup
0x8d5ce  ldstr    aViewquery// "ViewQuery"
0x8d5d3  ldc.i4.s 0x1B
0x8d5d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5da  dup
0x8d5db  ldstr    aReadonlyview// "ReadOnlyView"
0x8d5e0  ldc.i4.s 0x1C
0x8d5e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5e7  dup
0x8d5e8  ldstr    aRequiresclient// "RequiresClientIntegration"
0x8d5ed  ldc.i4.s 0x1D
0x8d5ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d5f4  dup
0x8d5f5  ldstr    aRowlimit// "RowLimit"
0x8d5fa  ldc.i4.s 0x1E
0x8d5fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d601  dup
0x8d602  ldstr    aScope// "Scope"
0x8d607  ldc.i4.s 0x1F
0x8d609  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d60e  dup
0x8d60f  ldstr    aServerrelative_0// "ServerRelativePath"
0x8d614  ldc.i4.s 0x20
0x8d616  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d61b  dup
0x8d61c  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x8d621  ldc.i4.s 0x21
0x8d623  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d628  dup
0x8d629  ldstr    aStyleid// "StyleId"
0x8d62e  ldc.i4.s 0x22
0x8d630  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d635  dup
0x8d636  ldstr    aTabularview// "TabularView"
0x8d63b  ldc.i4.s 0x23
0x8d63d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d642  dup
0x8d643  ldstr    aThreaded// "Threaded"
0x8d648  ldc.i4.s 0x24
0x8d64a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d64f  dup
0x8d650  ldstr    aTitle// "Title"
0x8d655  ldc.i4.s 0x25
0x8d657  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d65c  dup
0x8d65d  ldstr    aToolbar// "Toolbar"
0x8d662  ldc.i4.s 0x26
0x8d664  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d669  dup
0x8d66a  ldstr    aToolbartemplat// "ToolbarTemplateName"
0x8d66f  ldc.i4.s 0x27
0x8d671  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d676  dup
0x8d677  ldstr    aViewtype// "ViewType"
0x8d67c  ldc.i4.s 0x28
0x8d67e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d683  dup
0x8d684  ldstr    aViewdata// "ViewData"
0x8d689  ldc.i4.s 0x29
0x8d68b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d690  dup
0x8d691  ldstr    aViewfields// "ViewFields"
0x8d696  ldc.i4.s 0x2A
0x8d698  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d69d  dup
0x8d69e  ldstr    aVisualizationi// "VisualizationInfo"
0x8d6a3  ldc.i4.s 0x2B
0x8d6a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8d6aa  volatile.
0x8d6ac  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600178b-1
0x8d6b1  volatile.
0x8d6b3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600178b-1
0x8d6b8  ldloc.2
0x8d6b9  ldloca.s 3
0x8d6bb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8d6c0  brfalse  loc_8E439
0x8d6c5  ldloc.3
0x8d6c6  switch   loc_8D780, loc_8D7CA, loc_8D814, loc_8D85E, loc_8D8A8, loc_8D8F2, loc_8D93C, loc_8D986, loc_8D9D0, loc_8DA1A, loc_8DA64, loc_8DAAE, loc_8DAF8, loc_8DB42, loc_8DB8C, loc_8DBD6, loc_8DC20, loc_8DC6A, loc_8DCB4, loc_8DCFE, loc_8DD48, loc_8DD92, loc_8DDDC, loc_8DE26, loc_8DE70, loc_8DEBA, loc_8DF04, loc_8DF4E, loc_8DF98, loc_8DFE2, loc_8E02C, loc_8E076, loc_8E0C0, loc_8E10A, loc_8E154, loc_8E19E, loc_8E1E8, loc_8E232, loc_8E27C, loc_8E2C6, loc_8E310, loc_8E35A, loc_8E3A4, loc_8E3F2
0x8d77b  br       loc_8E439
0x8d780  ldarg.3
0x8d781  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d786  stloc.s  4
0x8d788  ldloca.s 4
0x8d78a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d78f  brfalse.s loc_8D7A8
0x8d791  ldarg.3
0x8d792  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d797  stloc.s  5
0x8d799  ldloca.s 5
0x8d79b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d7a0  brtrue.s loc_8D7A8
0x8d7a2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d7a7  throw
0x8d7a8  ldarg.0
0x8d7a9  ldstr    aAggregations// "Aggregations"
0x8d7ae  ldarg.s  4
0x8d7b0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d7b5  ldc.i4.1
0x8d7b6  stloc.0
0x8d7b7  ldarg.1
0x8d7b8  ldloc.1
0x8d7b9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Aggregations()
0x8d7be  ldarg.s  4
0x8d7c0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d7c5  br       loc_8E445
0x8d7ca  ldarg.3
0x8d7cb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d7d0  stloc.s  6
0x8d7d2  ldloca.s 6
0x8d7d4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d7d9  brfalse.s loc_8D7F2
0x8d7db  ldarg.3
0x8d7dc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d7e1  stloc.s  7
0x8d7e3  ldloca.s 7
0x8d7e5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d7ea  brtrue.s loc_8D7F2
0x8d7ec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d7f1  throw
0x8d7f2  ldarg.0
0x8d7f3  ldstr    aAggregationsst// "AggregationsStatus"
0x8d7f8  ldarg.s  4
0x8d7fa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d7ff  ldc.i4.1
0x8d800  stloc.0
0x8d801  ldarg.1
0x8d802  ldloc.1
0x8d803  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_AggregationsStatus()
0x8d808  ldarg.s  4
0x8d80a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d80f  br       loc_8E445
0x8d814  ldarg.3
0x8d815  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d81a  stloc.s  8
0x8d81c  ldloca.s 8
0x8d81e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d823  brfalse.s loc_8D83C
0x8d825  ldarg.3
0x8d826  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d82b  stloc.s  9
0x8d82d  ldloca.s 9
0x8d82f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d834  brtrue.s loc_8D83C
0x8d836  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d83b  throw
0x8d83c  ldarg.0
0x8d83d  ldstr    aBaseviewid_0// "BaseViewId"
0x8d842  ldarg.s  4
0x8d844  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d849  ldc.i4.1
0x8d84a  stloc.0
0x8d84b  ldarg.1
0x8d84c  ldloc.1
0x8d84d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_BaseViewID()
0x8d852  ldarg.s  4
0x8d854  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d859  br       loc_8E445
0x8d85e  ldarg.3
0x8d85f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d864  stloc.s  0xA
0x8d866  ldloca.s 0xA
0x8d868  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d86d  brfalse.s loc_8D886
0x8d86f  ldarg.3
0x8d870  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d875  stloc.s  0xB
0x8d877  ldloca.s 0xB
0x8d879  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d87e  brtrue.s loc_8D886
0x8d880  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d885  throw
0x8d886  ldarg.0
  ... truncated ...
```
