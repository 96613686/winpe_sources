# Microsoft.ReportingServices.Library.StreamRequestHandler::RenderFolder

- ea: `0x6c400`
- end: `0x6c915`
- name: `Microsoft.ReportingServices.Library.StreamRequestHandler::RenderFolder`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6b810`

## callees

- `0x1a4e0`
- `0x21580`
- `0x215a0`
- `0x215b0`
- `0x65ca0`
- `0x65cc0`
- `0x65d00`
- `0x65d20`
- `0x65d80`
- `0x6ad90`
- `0x6adc0`
- `0x6add0`
- `0x6aea0`
- `0x6aeb0`
- `0x6aef0`
- `0x6af00`
- `0x6af60`
- `0x6afa0`
- `0x6c400`

## string_xrefs

- `0x6c6fe`: `GetComponentDefinition`
- `0x6c522`: `Command`
- `0x6c818`: `Command`
- `0x6c69d`: `       &lt;link&gt;`

## pseudocode

```c

```

## disassembly

```asm
0x6c400  ldstr    aStreamrequesth_9// "StreamRequestHandler.RenderFolder"
0x6c405  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x6c40a  stloc.0
0x6c40b  ldarg.0
0x6c40c  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c411  ldstr    aTextHtml// "text/html"
0x6c416  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::set_MimeType(string value)
0x6c41b  ldarg.0
0x6c41c  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c421  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x6c426  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding value)
0x6c42b  ldarg.0
0x6c42c  callvirt instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_ServerDisplayPath()
0x6c431  ldstr    asc_B9DAC// " - "
0x6c436  ldarg.0
0x6c437  call     instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x6c43c  call     string [mscorlib]System.String::Concat(string, string, string)
0x6c441  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x6c446  ldstr    asc_B9DB4// "  "
0x6c44b  ldstr    aNbsp// " &nbsp;"
0x6c450  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x6c455  stloc.1
0x6c456  ldarg.0
0x6c457  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c45c  ldstr    aHtmlHead// "<html>\r\n  <head>\r\n"
0x6c461  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c466  ldarg.0
0x6c467  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c46c  ldstr    aMetaCharsetUtf// "    <meta charset=\"utf-8\">\r\n"
0x6c471  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c476  ldarg.0
0x6c477  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c47c  ldstr    aMetaNameGenera// "    <meta name=\"Generator\" content=\""
0x6c481  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c486  ldarg.0
0x6c487  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c48c  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x6c491  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductNameAndVersion()
0x6c496  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x6c49b  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4a0  ldarg.0
0x6c4a1  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4a6  ldstr    aTitle// "\">\r\n    <title>"
0x6c4ab  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4b0  ldarg.0
0x6c4b1  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4b6  ldloc.1
0x6c4b7  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4bc  ldarg.0
0x6c4bd  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4c2  ldstr    aTitleHeadBodyH// "</title>\r\n  </head>\r\n  <body><H1>"
0x6c4c7  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4cc  ldarg.0
0x6c4cd  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4d2  ldloc.1
0x6c4d3  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4d8  ldarg.0
0x6c4d9  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4de  ldstr    aH1HrPre// "</H1><hr>\r\n\r\n<pre>"
0x6c4e3  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c4e8  ldarg.0
0x6c4e9  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.StreamRequestHandler::GetParentFullPath()
0x6c4ee  stloc.2
0x6c4ef  ldloc.2
0x6c4f0  brfalse  loc_6C57D
0x6c4f5  ldarg.0
0x6c4f6  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c4fb  ldstr    aAHref// "<A HREF=\""
0x6c500  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c505  ldarg.0
0x6c506  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6c50b  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator)
0x6c510  dup
0x6c511  ldloc.2
0x6c512  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath)
0x6c517  pop
0x6c518  ldc.i4.1
0x6c519  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext, bool)
0x6c51e  stloc.s  4
0x6c520  ldloc.s  4
0x6c522  ldstr    aCommand_1// "Command"
0x6c527  ldstr    aListchildren// "ListChildren"
0x6c52c  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string, string)
0x6c531  ldarg.0
0x6c532  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c537  ldloc.s  4
0x6c539  callvirt instance string [mscorlib]System.Object::ToString()
0x6c53e  call     string [System.Web]System.Web.HttpUtility::HtmlAttributeEncode(string)
0x6c543  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c548  ldarg.0
0x6c549  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c54e  ldstr    asc_B9F12// "\">["
0x6c553  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c558  ldarg.0
0x6c559  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c55e  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_ParentDirectoryLink()
0x6c563  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x6c568  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c56d  ldarg.0
0x6c56e  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c573  ldstr    aA// "]</A>\r\n"
0x6c578  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c57d  ldarg.0
0x6c57e  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6c583  callvirt instance class Microsoft.ReportingServices.Library.ListChildrenAction Microsoft.ReportingServices.Library.RSService::get_ListChildrenAction()
0x6c588  dup
0x6c589  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ListChildrenActionParameters>::get_ActionParameters()
0x6c58e  ldarg.0
0x6c58f  call     instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x6c594  callvirt instance void Microsoft.ReportingServices.Library.ListChildrenActionParameters::set_ItemPath(string value)
0x6c599  dup
0x6c59a  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ListChildrenActionParameters>::get_ActionParameters()
0x6c59f  ldc.i4.0
0x6c5a0  callvirt instance void Microsoft.ReportingServices.Library.ListChildrenActionParameters::set_Recursive(bool value)
0x6c5a5  dup
0x6c5a6  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ListChildrenActionParameters>::Execute()
0x6c5ab  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ListChildrenActionParameters>::get_ActionParameters()
0x6c5b0  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemList Microsoft.ReportingServices.Library.ListChildrenActionParameters::get_Children()
0x6c5b5  stloc.3
0x6c5b6  ldc.i4.0
0x6c5b7  stloc.s  5
0x6c5b9  br       loc_6C899
0x6c5be  ldloc.3
0x6c5bf  ldloc.s  5
0x6c5c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.CatalogItemDescriptor>::get_Item(!!T0)
0x6c5c6  stloc.s  6
0x6c5c8  ldloc.s  6
0x6c5ca  callvirt instance string Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Name()
0x6c5cf  stloc.s  7
0x6c5d1  ldloc.s  6
0x6c5d3  callvirt instance int32 Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Size()
0x6c5d8  ldc.i4.0
0x6c5d9  bge.s    loc_6C5DE
0x6c5db  ldc.i4.0
0x6c5dc  br.s     loc_6C5E5
0x6c5de  ldloc.s  6
0x6c5e0  callvirt instance int32 Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Size()
0x6c5e5  stloc.s  8
0x6c5e7  ldloc.s  6
0x6c5e9  callvirt instance valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0x6c5ee  stloc.s  9
0x6c5f0  ldsfld   string [mscorlib]System.String::Empty
0x6c5f5  stloc.s  0xA
0x6c5f7  ldnull
0x6c5f8  stloc.s  0xB
0x6c5fa  ldloc.s  9
0x6c5fc  ldc.i4.1
0x6c5fd  sub
0x6c5fe  switch   loc_6C640, loc_6C653, loc_6C678, loc_6C69D, loc_6C6B0, loc_6C6C3, loc_6C640, loc_6C707, loc_6C6E5, loc_6C653, loc_6C729, loc_6C732, loc_6C73B, loc_6C744
0x6c63b  br       loc_6C74D
0x6c640  ldstr    aLtDirGt// "        &lt;dir&gt;"
0x6c645  stloc.s  0xA
0x6c647  ldstr    aListchildren// "ListChildren"
0x6c64c  stloc.s  0xB
0x6c64e  br       loc_6C758
0x6c653  ldloca.s 8
0x6c655  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c65a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6c65f  stloc.s  0xA
0x6c661  ldloc.s  0xA
0x6c663  ldc.i4.s 0xD
0x6c665  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c66a  stloc.s  0xA
0x6c66c  ldstr    aRender// "Render"
0x6c671  stloc.s  0xB
0x6c673  br       loc_6C758
0x6c678  ldloca.s 8
0x6c67a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c67f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6c684  stloc.s  0xA
0x6c686  ldloc.s  0xA
0x6c688  ldc.i4.s 0xD
0x6c68a  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c68f  stloc.s  0xA
0x6c691  ldstr    aGetresourcecon_0// "GetResourceContents"
0x6c696  stloc.s  0xB
0x6c698  br       loc_6C758
0x6c69d  ldstr    aLtLinkGt// "       &lt;link&gt;"
0x6c6a2  stloc.s  0xA
0x6c6a4  ldstr    aRender// "Render"
0x6c6a9  stloc.s  0xB
0x6c6ab  br       loc_6C758
0x6c6b0  ldstr    aLtDsGt// "         &lt;ds&gt;"
0x6c6b5  stloc.s  0xA
0x6c6b7  ldstr    aGetdatasourcec_0// "GetDataSourceContents"
0x6c6bc  stloc.s  0xB
0x6c6be  br       loc_6C758
0x6c6c3  ldloca.s 8
0x6c6c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c6ca  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6c6cf  stloc.s  0xA
0x6c6d1  ldloc.s  0xA
0x6c6d3  ldc.i4.s 0xD
0x6c6d5  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c6da  stloc.s  0xA
0x6c6dc  ldstr    aGetmodeldefini_0// "GetModelDefinition"
0x6c6e1  stloc.s  0xB
0x6c6e3  br.s     loc_6C758
0x6c6e5  ldloca.s 8
0x6c6e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c6ec  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6c6f1  stloc.s  0xA
0x6c6f3  ldloc.s  0xA
0x6c6f5  ldc.i4.s 0xD
0x6c6f7  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c6fc  stloc.s  0xA
0x6c6fe  ldstr    aGetcomponentde// "GetComponentDefinition"
0x6c703  stloc.s  0xB
0x6c705  br.s     loc_6C758
0x6c707  ldloca.s 8
0x6c709  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c70e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6c713  stloc.s  0xA
0x6c715  ldloc.s  0xA
0x6c717  ldc.i4.s 0xD
0x6c719  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c71e  stloc.s  0xA
0x6c720  ldstr    aGetdatasetdefi_0// "GetDataSetDefinition"
0x6c725  stloc.s  0xB
0x6c727  br.s     loc_6C758
0x6c729  ldstr    aLtKpiGt// "        &lt;kpi&gt;"
0x6c72e  stloc.s  0xA
0x6c730  br.s     loc_6C758
0x6c732  ldstr    aLtMrGt// "         &lt;mr&gt;"
0x6c737  stloc.s  0xA
0x6c739  br.s     loc_6C758
0x6c73b  ldstr    aLtPbixGt// "       &lt;pbix&gt;"
0x6c740  stloc.s  0xA
0x6c742  br.s     loc_6C758
0x6c744  ldstr    aLtExcelGt// "      &lt;excel&gt;"
0x6c749  stloc.s  0xA
0x6c74b  br.s     loc_6C758
0x6c74d  ldstr    aUnexpectedItem_0// "Unexpected item type"
0x6c752  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x6c757  throw
0x6c758  ldsfld   string [mscorlib]System.String::Empty
0x6c75d  stloc.s  0xC
0x6c75f  ldloc.s  6
0x6c761  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreationDate()
0x6c766  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x6c76b  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6c770  brfalse.s loc_6C78E
0x6c772  ldloc.s  6
0x6c774  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreationDate()
0x6c779  stloc.s  0xD
0x6c77b  ldloca.s 0xD
0x6c77d  ldstr    aF// "f"
0x6c782  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0x6c787  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x6c78c  stloc.s  0xC
0x6c78e  ldloc.s  0xC
0x6c790  ldc.i4.s 0x26
0x6c792  callvirt instance string [mscorlib]System.String::PadLeft(int32)
0x6c797  stloc.s  0xC
0x6c799  ldarg.0
0x6c79a  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c79f  ldloc.s  0xC
0x6c7a1  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c7a6  ldarg.0
0x6c7a7  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c7ac  ldloc.s  0xA
0x6c7ae  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c7b3  ldloc.s  7
0x6c7b5  brfalse  loc_6C883
0x6c7ba  ldloc.s  7
0x6c7bc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6c7c1  brfalse  loc_6C883
0x6c7c6  ldarg.0
0x6c7c7  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c7cc  ldstr    aAHref_0// " <A HREF=\""
0x6c7d1  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::Write(string s)
0x6c7d6  ldstr    asc_BA086// "?"
0x6c7db  ldloc.s  6
0x6c7dd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Path()
0x6c7e2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6c7e7  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string)
0x6c7ec  call     string [mscorlib]System.String::Concat(string, string)
0x6c7f1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x6c7f6  stloc.s  0xE
0x6c7f8  ldloc.s  0xB
0x6c7fa  brfalse.s loc_6C83A
0x6c7fc  ldloc.s  0xE
0x6c7fe  ldstr    asc_98B9C// "&"
0x6c803  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c808  pop
0x6c809  ldloc.s  0xE
0x6c80b  ldstr    aRs// "rs:"
0x6c810  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c815  pop
0x6c816  ldloc.s  0xE
0x6c818  ldstr    aCommand_1// "Command"
0x6c81d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c822  pop
0x6c823  ldloc.s  0xE
0x6c825  ldstr    asc_BA092// "="
0x6c82a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c82f  pop
0x6c830  ldloc.s  0xE
0x6c832  ldloc.s  0xB
0x6c834  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
  ... truncated ...
```
