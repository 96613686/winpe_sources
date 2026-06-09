# Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::RenderContents

- ea: `0x14970`
- end: `0x14f80`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::RenderContents`
- size: `1552`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7bc0`
- `0x147c0`
- `0x148a0`
- `0x148e0`
- `0x14970`
- `0x14f80`
- `0x15000`
- `0x15080`
- `0x150c0`

## string_xrefs

- `0x14af6`: `Rendering Stock Quotes Failed XML=`
- `0x14f52`: `Rendering Stock Quotes Failed XML=`

## pseudocode

```c

```

## disassembly

```asm
0x14970  ldarg.0
0x14971  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::get_Symbols()
0x14976  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::get_Count()
0x1497b  brtrue.s loc_1498E
0x1497d  ldarg.1
0x1497e  ldstr    aStocklistconro// "StockListConrol.ErrMsg.NoSymbolsSpecifi"...
0x14983  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14988  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x1498d  ret
0x1498e  ldarg.0
0x1498f  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::get_CultureName()
0x14994  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::GetCultureInfo(string)
0x14999  stloc.0
0x1499a  ldc.i4.1
0x1499b  stloc.1
0x1499c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x149a1  stloc.2
0x149a2  ldc.i4.0
0x149a3  stloc.3
0x149a4  br.s     loc_149F3
0x149a6  ldarg.0
0x149a7  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::get_Symbols()
0x149ac  ldloc.3
0x149ad  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItem Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::get_Item(int32 index)
0x149b2  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.StockListItem::get_Symbol()
0x149b7  ldstr    aJp// "jp:"
0x149bc  ldc.i4.5
0x149bd  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x149c2  brtrue.s loc_149EF
0x149c4  ldloc.1
0x149c5  brfalse.s loc_149CB
0x149c7  ldc.i4.0
0x149c8  stloc.1
0x149c9  br.s     loc_149D7
0x149cb  ldloc.2
0x149cc  ldstr    asc_2030E// ","
0x149d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x149d6  pop
0x149d7  ldloc.2
0x149d8  ldarg.0
0x149d9  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::get_Symbols()
0x149de  ldloc.3
0x149df  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItem Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::get_Item(int32 index)
0x149e4  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.StockListItem::get_Symbol()
0x149e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x149ee  pop
0x149ef  ldloc.3
0x149f0  ldc.i4.1
0x149f1  add
0x149f2  stloc.3
0x149f3  ldloc.3
0x149f4  ldarg.0
0x149f5  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::get_Symbols()
0x149fa  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::get_Count()
0x149ff  blt.s    loc_149A6
0x14a01  ldnull
0x14a02  stloc.s  4
0x14a04  ldloc.2
0x14a05  callvirt instance string [mscorlib]System.Object::ToString()
0x14a0a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.MsnStockService::GetStockQuotesXml(string symbols)
0x14a0f  stloc.s  4
0x14a11  leave.s  loc_14A51
0x14a13  stloc.s  5
0x14a15  ldc.i4   0x6736396C
0x14a1a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x14a1f  ldc.i4.s 0x32
0x14a21  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::classId
0x14a26  ldstr    aRendercontents// "RenderContents"
0x14a2b  ldstr    aGettingStockQu// "Getting Stock Quotes Failed. "
0x14a30  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x14a35  ldc.i4.1
0x14a36  newarr   [mscorlib]System.Object
0x14a3b  stloc.s  0x16
0x14a3d  ldloc.s  0x16
0x14a3f  ldc.i4.0
0x14a40  ldloc.s  5
0x14a42  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x14a47  stelem.ref
0x14a48  ldloc.s  0x16
0x14a4a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x14a4f  leave.s  loc_14A51
0x14a51  ldloc.s  4
0x14a53  brtrue.s loc_14A6A
0x14a55  ldarg.1
0x14a56  ldstr    aStocklistconro_0// "StockListConrol.ErrMsg.FailedToGetQuote"...
0x14a5b  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14a60  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14a65  br       loc_14F38
0x14a6a  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x14a6f  stloc.s  6
0x14a71  ldloc.s  6
0x14a73  ldnull
0x14a74  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x14a79  ldloc.s  4
0x14a7b  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x14a80  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x14a85  stloc.s  7
0x14a87  ldloc.s  6
0x14a89  ldloc.s  7
0x14a8b  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x14a90  leave.s  loc_14A9E
0x14a92  ldloc.s  7
0x14a94  brfalse.s loc_14A9D
0x14a96  ldloc.s  7
0x14a98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14a9d  endfinally
0x14a9e  ldloc.s  6
0x14aa0  ldstr    aDescendantQuot// "descendant::quotesdata"
0x14aa5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x14aaa  stloc.s  8
0x14aac  ldloc.s  8
0x14aae  brtrue.s loc_14AC5
0x14ab0  ldarg.1
0x14ab1  ldstr    aStocklistconro_0// "StockListConrol.ErrMsg.FailedToGetQuote"...
0x14ab6  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14abb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14ac0  br       loc_14F38
0x14ac5  ldloc.s  8
0x14ac7  ldstr    aDescendantTick// "descendant::ticker"
0x14acc  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x14ad1  stloc.s  9
0x14ad3  ldloc.s  9
0x14ad5  brfalse.s loc_14AE0
0x14ad7  ldloc.s  9
0x14ad9  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x14ade  brtrue.s loc_14B34
0x14ae0  ldc.i4   0x6736396D
0x14ae5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x14aea  ldc.i4.s 0x32
0x14aec  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::classId
0x14af1  ldstr    aRendercontents// "RenderContents"
0x14af6  ldstr    aRenderingStock// "Rendering Stock Quotes Failed XML="
0x14afb  ldloc.s  4
0x14afd  call     string [mscorlib]System.String::Concat(string, string)
0x14b02  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x14b07  ldc.i4.1
0x14b08  newarr   [mscorlib]System.Object
0x14b0d  stloc.s  0x17
0x14b0f  ldloc.s  0x17
0x14b11  ldc.i4.0
0x14b12  ldsfld   string [mscorlib]System.String::Empty
0x14b17  stelem.ref
0x14b18  ldloc.s  0x17
0x14b1a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x14b1f  ldarg.1
0x14b20  ldstr    aStocklistconro_0// "StockListConrol.ErrMsg.FailedToGetQuote"...
0x14b25  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14b2a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14b2f  br       loc_14F38
0x14b34  ldarg.1
0x14b35  ldc.i4.s 0x20
0x14b37  ldstr    a4px// "4px"
0x14b3c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14b41  ldarg.1
0x14b42  ldc.i4.s 0x21
0x14b44  ldstr    a4px// "4px"
0x14b49  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14b4e  ldarg.1
0x14b4f  ldc.i4.s 0x52
0x14b51  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14b56  ldarg.1
0x14b57  ldc.i4.s 0x5A
0x14b59  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14b5e  ldarg.1
0x14b5f  ldc.i4.s 0x24
0x14b61  ldstr    aLeft// "left"
0x14b66  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14b6b  ldarg.1
0x14b6c  ldc.i4.s 0x32
0x14b6e  ldstr    aCol// "col"
0x14b73  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14b78  ldarg.1
0x14b79  ldc.i4.s 0x57
0x14b7b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14b80  ldarg.1
0x14b81  ldstr    aStocklistcontr_0// "StockListControl.Title.Symbol"
0x14b86  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14b8b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14b90  ldarg.1
0x14b91  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14b96  ldarg.1
0x14b97  ldc.i4.s 0x24
0x14b99  ldstr    aRight// "right"
0x14b9e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14ba3  ldarg.1
0x14ba4  ldc.i4.s 0x32
0x14ba6  ldstr    aCol// "col"
0x14bab  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14bb0  ldarg.1
0x14bb1  ldc.i4.s 0x57
0x14bb3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14bb8  ldarg.1
0x14bb9  ldstr    aStocklistcontr_1// "StockListControl.Title.Price"
0x14bbe  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14bc3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14bc8  ldarg.1
0x14bc9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14bce  ldarg.1
0x14bcf  ldc.i4.s 0x24
0x14bd1  ldstr    aRight// "right"
0x14bd6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14bdb  ldarg.1
0x14bdc  ldc.i4.s 0x32
0x14bde  ldstr    aCol// "col"
0x14be3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14be8  ldarg.1
0x14be9  ldc.i4.s 0x57
0x14beb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14bf0  ldarg.1
0x14bf1  ldstr    aStocklistcontr_2// "StockListControl.Title.Change"
0x14bf6  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14bfb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14c00  ldarg.1
0x14c01  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14c06  ldarg.1
0x14c07  ldc.i4.s 0x24
0x14c09  ldstr    aRight// "right"
0x14c0e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14c13  ldarg.1
0x14c14  ldc.i4.s 0x32
0x14c16  ldstr    aCol// "col"
0x14c1b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14c20  ldarg.1
0x14c21  ldc.i4.s 0x57
0x14c23  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14c28  ldarg.1
0x14c29  ldstr    aStocklistcontr_3// "StockListControl.Title.PercentChange"
0x14c2e  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14c33  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x14c38  ldarg.1
0x14c39  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14c3e  ldarg.1
0x14c3f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14c44  ldc.i4.0
0x14c45  stloc.s  0xA
0x14c47  br       loc_14EAF
0x14c4c  ldloc.s  9
0x14c4e  ldloc.s  0xA
0x14c50  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x14c55  stloc.s  0xB
0x14c57  ldloc.s  0xB
0x14c59  ldstr    aSymbol// "symbol"
0x14c5e  call     string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x14c63  stloc.s  0xC
0x14c65  ldloc.s  0xB
0x14c67  ldstr    aLast// "last"
0x14c6c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x14c71  stloc.s  0xD
0x14c73  ldloc.s  0xB
0x14c75  ldstr    aChange// "change"
0x14c7a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x14c7f  stloc.s  0xE
0x14c81  ldloc.s  0xB
0x14c83  ldstr    aPercentchange// "percentchange"
0x14c88  call     string Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x14c8d  stloc.s  0xF
0x14c8f  ldstr    aStocklistconto// "StockListContorl.Style.NeutralChange"
0x14c94  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14c99  stloc.s  0x10
0x14c9b  ldloc.s  0xE
0x14c9d  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.StockListControl::xmlNumberFormatCI
0x14ca2  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x14ca7  stloc.s  0x11
0x14ca9  ldloc.s  0x11
0x14cab  ldc.r8   0.0
0x14cb4  ble.un.s loc_14CC4
0x14cb6  ldstr    aStocklistconto_0// "StockListContorl.Style.PositiveChange"
0x14cbb  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14cc0  stloc.s  0x10
0x14cc2  br.s     loc_14CDD
0x14cc4  ldloc.s  0x11
0x14cc6  ldc.r8   0.0
0x14ccf  bge.un.s loc_14CDD
0x14cd1  ldstr    aStocklistconto_1// "StockListContorl.Style.NegitiveChange"
0x14cd6  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14cdb  stloc.s  0x10
0x14cdd  leave.s  loc_14CE2
0x14cdf  pop
0x14ce0  leave.s  loc_14CE2
0x14ce2  ldarg.1
0x14ce3  ldc.i4.s 0x5A
0x14ce5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14cea  ldarg.1
0x14ceb  ldc.i4.s 0x24
0x14ced  ldstr    aLeft// "left"
0x14cf2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14cf7  ldarg.1
0x14cf8  ldc.i4.s 0x54
0x14cfa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14cff  ldloc.s  0xC
0x14d01  brfalse.s loc_14D4A
0x14d03  ldarg.1
0x14d04  ldc.i4.s 0x21
0x14d06  ldstr    aBlank// "_blank"
0x14d0b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14d10  ldarg.1
0x14d11  ldc.i4.s 0x10
0x14d13  ldstr    aStocklistcontr_4// "StockListControl.Money.URL"
0x14d18  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x14d1d  ldstr    a0_0// "{0}"
  ... truncated ...
```
