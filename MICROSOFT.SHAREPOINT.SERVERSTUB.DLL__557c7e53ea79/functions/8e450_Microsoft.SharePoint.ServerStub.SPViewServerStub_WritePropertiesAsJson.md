# Microsoft.SharePoint.ServerStub.SPViewServerStub::WritePropertiesAsJson

- ea: `0x8e450`
- end: `0x8ede9`
- name: `Microsoft.SharePoint.ServerStub.SPViewServerStub::WritePropertiesAsJson`
- size: `2457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8e450`

## string_xrefs

- `0x8eb6b`: `ServerRelativePath`
- `0x8eb77`: `ServerRelativePath`
- `0x8eb82`: `ServerRelativePath`
- `0x8eb9a`: `ServerRelativePath`
- `0x8e805`: `JSLink`
- `0x8e811`: `JSLink`
- `0x8e81c`: `JSLink`
- `0x8e834`: `JSLink`
- `0x8e6e3`: `HtmlSchemaXml`
- `0x8e6ef`: `HtmlSchemaXml`
- `0x8e6fa`: `HtmlSchemaXml`
- `0x8e712`: `HtmlSchemaXml`
- `0x8e83f`: `ListViewXml`
- `0x8e84b`: `ListViewXml`
- `0x8e856`: `ListViewXml`
- `0x8e86e`: `ListViewXml`
- `0x8ea83`: `ReadOnlyView`
- `0x8ea8f`: `ReadOnlyView`
- `0x8ea9a`: `ReadOnlyView`
- `0x8eab2`: `ReadOnlyView`
- `0x8ec53`: `Threaded`
- `0x8ec5f`: `Threaded`
- `0x8ec6a`: `Threaded`
- `0x8ec82`: `Threaded`
- `0x8ed01`: `ToolbarTemplateName`
- `0x8ed0d`: `ToolbarTemplateName`
- `0x8ed18`: `ToolbarTemplateName`
- `0x8ed30`: `ToolbarTemplateName`

## pseudocode

```c

```

## disassembly

```asm
0x8e450  ldarg.2
0x8e451  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPView
0x8e456  stloc.0
0x8e457  ldloc.0
0x8e458  brtrue.s loc_8E45B
0x8e45a  ret
0x8e45b  ldarg.0
0x8e45c  ldarg.1
0x8e45d  ldarg.2
0x8e45e  ldarg.3
0x8e45f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e464  ldarg.0
0x8e465  ldstr    aAggregations// "Aggregations"
0x8e46a  ldarg.3
0x8e46b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e470  ldarg.1
0x8e471  ldstr    aAggregations// "Aggregations"
0x8e476  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e47b  ldarg.3
0x8e47c  ldstr    aAggregations// "Aggregations"
0x8e481  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e486  ldarg.1
0x8e487  ldloc.0
0x8e488  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Aggregations()
0x8e48d  ldarg.3
0x8e48e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e493  ldarg.3
0x8e494  ldstr    aAggregations// "Aggregations"
0x8e499  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e49e  ldarg.0
0x8e49f  ldstr    aAggregationsst// "AggregationsStatus"
0x8e4a4  ldarg.3
0x8e4a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e4aa  ldarg.1
0x8e4ab  ldstr    aAggregationsst// "AggregationsStatus"
0x8e4b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e4b5  ldarg.3
0x8e4b6  ldstr    aAggregationsst// "AggregationsStatus"
0x8e4bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e4c0  ldarg.1
0x8e4c1  ldloc.0
0x8e4c2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_AggregationsStatus()
0x8e4c7  ldarg.3
0x8e4c8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e4cd  ldarg.3
0x8e4ce  ldstr    aAggregationsst// "AggregationsStatus"
0x8e4d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e4d8  ldarg.0
0x8e4d9  ldstr    aBaseviewid_0// "BaseViewId"
0x8e4de  ldarg.3
0x8e4df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e4e4  ldarg.1
0x8e4e5  ldstr    aBaseviewid_0// "BaseViewId"
0x8e4ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e4ef  ldarg.3
0x8e4f0  ldstr    aBaseviewid_0// "BaseViewId"
0x8e4f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e4fa  ldarg.1
0x8e4fb  ldloc.0
0x8e4fc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_BaseViewID()
0x8e501  ldarg.3
0x8e502  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e507  ldarg.3
0x8e508  ldstr    aBaseviewid_0// "BaseViewId"
0x8e50d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e512  ldarg.0
0x8e513  ldstr    aColumnwidth// "ColumnWidth"
0x8e518  ldarg.3
0x8e519  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e51e  ldarg.1
0x8e51f  ldstr    aColumnwidth// "ColumnWidth"
0x8e524  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e529  ldarg.3
0x8e52a  ldstr    aColumnwidth// "ColumnWidth"
0x8e52f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e534  ldarg.1
0x8e535  ldloc.0
0x8e536  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ColumnWidth()
0x8e53b  ldarg.3
0x8e53c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e541  ldarg.3
0x8e542  ldstr    aColumnwidth// "ColumnWidth"
0x8e547  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e54c  ldarg.0
0x8e54d  ldstr    aContenttypeid_0// "ContentTypeId"
0x8e552  ldarg.3
0x8e553  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e558  ldarg.1
0x8e559  ldstr    aContenttypeid_0// "ContentTypeId"
0x8e55e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e563  ldarg.3
0x8e564  ldstr    aContenttypeid_0// "ContentTypeId"
0x8e569  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e56e  ldarg.1
0x8e56f  ldloc.0
0x8e570  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ContentTypeId()
0x8e575  ldarg.3
0x8e576  call     T0x2B000156
0x8e57b  ldarg.3
0x8e57c  ldstr    aContenttypeid_0// "ContentTypeId"
0x8e581  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e586  ldarg.0
0x8e587  ldstr    aCustomformatte// "CustomFormatter"
0x8e58c  ldarg.3
0x8e58d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e592  ldarg.1
0x8e593  ldstr    aCustomformatte// "CustomFormatter"
0x8e598  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e59d  ldarg.3
0x8e59e  ldstr    aCustomformatte// "CustomFormatter"
0x8e5a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e5a8  ldarg.1
0x8e5a9  ldloc.0
0x8e5aa  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_CustomFormatter()
0x8e5af  ldarg.3
0x8e5b0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e5b5  ldarg.3
0x8e5b6  ldstr    aCustomformatte// "CustomFormatter"
0x8e5bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e5c0  ldarg.0
0x8e5c1  ldstr    aDefaultview// "DefaultView"
0x8e5c6  ldarg.3
0x8e5c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e5cc  ldarg.1
0x8e5cd  ldstr    aDefaultview// "DefaultView"
0x8e5d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e5d7  ldarg.3
0x8e5d8  ldstr    aDefaultview// "DefaultView"
0x8e5dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e5e2  ldarg.1
0x8e5e3  ldloc.0
0x8e5e4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_DefaultView()
0x8e5e9  ldarg.3
0x8e5ea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e5ef  ldarg.3
0x8e5f0  ldstr    aDefaultview// "DefaultView"
0x8e5f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e5fa  ldarg.0
0x8e5fb  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8e600  ldarg.3
0x8e601  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e606  ldarg.1
0x8e607  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8e60c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e611  ldarg.3
0x8e612  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8e617  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e61c  ldarg.1
0x8e61d  ldloc.0
0x8e61e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_DefaultViewForContentType()
0x8e623  ldarg.3
0x8e624  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e629  ldarg.3
0x8e62a  ldstr    aDefaultviewfor// "DefaultViewForContentType"
0x8e62f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e634  ldarg.0
0x8e635  ldstr    aEditormodified// "EditorModified"
0x8e63a  ldarg.3
0x8e63b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e640  ldarg.1
0x8e641  ldstr    aEditormodified// "EditorModified"
0x8e646  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e64b  ldarg.3
0x8e64c  ldstr    aEditormodified// "EditorModified"
0x8e651  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e656  ldarg.1
0x8e657  ldloc.0
0x8e658  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_EditorModified()
0x8e65d  ldarg.3
0x8e65e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e663  ldarg.3
0x8e664  ldstr    aEditormodified// "EditorModified"
0x8e669  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e66e  ldarg.0
0x8e66f  ldstr    aFormats// "Formats"
0x8e674  ldarg.3
0x8e675  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e67a  ldarg.1
0x8e67b  ldstr    aFormats// "Formats"
0x8e680  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e685  ldarg.3
0x8e686  ldstr    aFormats// "Formats"
0x8e68b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e690  ldarg.1
0x8e691  ldloc.0
0x8e692  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Formats()
0x8e697  ldarg.3
0x8e698  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e69d  ldarg.3
0x8e69e  ldstr    aFormats// "Formats"
0x8e6a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e6a8  ldarg.0
0x8e6a9  ldstr    aHidden// "Hidden"
0x8e6ae  ldarg.3
0x8e6af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e6b4  ldarg.1
0x8e6b5  ldstr    aHidden// "Hidden"
0x8e6ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e6bf  ldarg.3
0x8e6c0  ldstr    aHidden// "Hidden"
0x8e6c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e6ca  ldarg.1
0x8e6cb  ldloc.0
0x8e6cc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Hidden()
0x8e6d1  ldarg.3
0x8e6d2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e6d7  ldarg.3
0x8e6d8  ldstr    aHidden// "Hidden"
0x8e6dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e6e2  ldarg.0
0x8e6e3  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8e6e8  ldarg.3
0x8e6e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e6ee  ldarg.1
0x8e6ef  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8e6f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e6f9  ldarg.3
0x8e6fa  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8e6ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e704  ldarg.1
0x8e705  ldloc.0
0x8e706  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_HtmlSchemaXml()
0x8e70b  ldarg.3
0x8e70c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e711  ldarg.3
0x8e712  ldstr    aHtmlschemaxml// "HtmlSchemaXml"
0x8e717  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e71c  ldarg.0
0x8e71d  ldstr    aId_0// "Id"
0x8e722  ldarg.3
0x8e723  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e728  ldarg.1
0x8e729  ldstr    aId_0// "Id"
0x8e72e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e733  ldarg.3
0x8e734  ldstr    aId_0// "Id"
0x8e739  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e73e  ldarg.1
0x8e73f  ldloc.0
0x8e740  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ID()
0x8e745  ldarg.3
0x8e746  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e74b  ldarg.3
0x8e74c  ldstr    aId_0// "Id"
0x8e751  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e756  ldarg.0
0x8e757  ldstr    aImageurl// "ImageUrl"
0x8e75c  ldarg.3
0x8e75d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e762  ldarg.1
0x8e763  ldstr    aImageurl// "ImageUrl"
0x8e768  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e76d  ldarg.3
0x8e76e  ldstr    aImageurl// "ImageUrl"
0x8e773  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e778  ldarg.1
0x8e779  ldloc.0
0x8e77a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_ImageUrl()
0x8e77f  ldarg.3
0x8e780  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e785  ldarg.3
0x8e786  ldstr    aImageurl// "ImageUrl"
0x8e78b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e790  ldarg.0
0x8e791  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8e796  ldarg.3
0x8e797  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e79c  ldarg.1
0x8e79d  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8e7a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e7a7  ldarg.3
0x8e7a8  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8e7ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e7b2  ldarg.1
0x8e7b3  ldloc.0
0x8e7b4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_IncludeRootFolder()
0x8e7b9  ldarg.3
0x8e7ba  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e7bf  ldarg.3
0x8e7c0  ldstr    aIncluderootfol// "IncludeRootFolder"
0x8e7c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e7ca  ldarg.0
0x8e7cb  ldstr    aViewjoins// "ViewJoins"
0x8e7d0  ldarg.3
0x8e7d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e7d6  ldarg.1
0x8e7d7  ldstr    aViewjoins// "ViewJoins"
0x8e7dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e7e1  ldarg.3
0x8e7e2  ldstr    aViewjoins// "ViewJoins"
0x8e7e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e7ec  ldarg.1
0x8e7ed  ldloc.0
0x8e7ee  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPView::get_Joins()
0x8e7f3  ldarg.3
0x8e7f4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e7f9  ldarg.3
0x8e7fa  ldstr    aViewjoins// "ViewJoins"
0x8e7ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e804  ldarg.0
  ... truncated ...
```
