# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::DeletePage

- ea: `0x1920`
- end: `0x1be6`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::DeletePage`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb50`

## callees

- `0x20`
- `0x1920`

## string_xrefs

- `0x1920`: `SiteDesigner_SiteIODeletePage`
- `0x19ad`: `/DeletePageRequest/@shouldDeleteLastPage`
- `0x19c0`: `/DeletePageRequest/Page/@url`
- `0x1b60`: `DeletePageResponse`

## pseudocode

```c

```

## disassembly

```asm
0x1920  ldstr    aSitedesignerSi_1// "SiteDesigner_SiteIODeletePage"
0x1925  ldnull
0x1926  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x192b  ldc.i4.m1
0x192c  stloc.0
0x192d  ldarg.0
0x192e  brtrue.s loc_1936
0x1930  ldsfld   string [mscorlib]System.String::Empty
0x1935  ret
0x1936  ldarg.0
0x1937  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x193c  ldc.i4   0x7FFFFFFF
0x1941  conv.i8
0x1942  ble.s    loc_194A
0x1944  ldsfld   string [mscorlib]System.String::Empty
0x1949  ret
0x194a  ldarg.0
0x194b  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1950  conv.i4
0x1951  stloc.1
0x1952  ldloc.1
0x1953  newarr   [mscorlib]System.Byte
0x1958  stloc.2
0x1959  ldarg.0
0x195a  ldloc.2
0x195b  ldc.i4.0
0x195c  ldloc.1
0x195d  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x1962  pop
0x1963  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1968  ldloc.2
0x1969  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x196e  stloc.3
0x196f  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1974  stloc.s  4
0x1976  ldloc.3
0x1977  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x197c  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x1981  stloc.s  5
0x1983  ldloc.s  5
0x1985  ldc.i4.0
0x1986  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x198b  ldloc.s  4
0x198d  ldloc.s  5
0x198f  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x1994  leave.s  loc_19A2
0x1996  ldloc.s  5
0x1998  brfalse.s loc_19A1
0x199a  ldloc.s  5
0x199c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a1  endfinally
0x19a2  ldloc.s  4
0x19a4  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x19a9  stloc.s  6
0x19ab  ldloc.s  6
0x19ad  ldstr    aDeletepagerequ// "/DeletePageRequest/@shouldDeleteLastPag"...
0x19b2  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x19b7  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x19bc  stloc.s  7
0x19be  ldloc.s  6
0x19c0  ldstr    aDeletepagerequ_0// "/DeletePageRequest/Page/@url"
0x19c5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x19ca  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x19cf  stloc.s  8
0x19d1  ldsfld   string [mscorlib]System.String::Empty
0x19d6  stloc.s  9
0x19d8  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::get_PublicSitePathValue()
0x19dd  ldstr    aDefaultAspx_0// "/default.aspx"
0x19e2  call     string [mscorlib]System.String::Concat(string, string)
0x19e7  ldloc.s  8
0x19e9  ldc.i4.1
0x19ea  newarr   [mscorlib]System.Char
0x19ef  stloc.s  0x1A
0x19f1  ldloc.s  0x1A
0x19f3  ldc.i4.0
0x19f4  ldc.i4.s 0x2F
0x19f6  stelem.i2
0x19f7  ldloc.s  0x1A
0x19f9  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0x19fe  ldc.i4.5
0x19ff  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1a04  brfalse  loc_1B4F
0x1a09  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x1a0e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x1a13  stloc.s  0xA
0x1a15  ldloc.s  0xA
0x1a17  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x1a1c  stloc.s  0xB
0x1a1e  ldloc.s  0xB
0x1a20  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1a25  stloc.s  0xC
0x1a27  ldloc.s  0xB
0x1a29  ldloc.s  8
0x1a2b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x1a30  stloc.s  0xD
0x1a32  ldloc.s  0xD
0x1a34  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x1a39  brfalse  loc_1B48
0x1a3e  call     string[] Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Common::get_SystemFilesList()
0x1a43  ldloc.s  0xD
0x1a45  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x1a4a  call     T0x2B000001
0x1a4f  ldc.i4.0
0x1a50  blt.s    loc_1A59
0x1a52  ldc.i4.2
0x1a53  stloc.0
0x1a54  br       loc_1B48
0x1a59  ldloc.s  0xD
0x1a5b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ParentFolder()
0x1a60  stloc.s  0xF
0x1a62  ldloc.s  0xF
0x1a64  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ServerRelativeUrl()
0x1a69  ldloc.s  0xB
0x1a6b  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetServerRelativePath(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1a70  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::get_PublicSitePathValue()
0x1a75  call     string [mscorlib]System.String::Concat(string, string)
0x1a7a  ldc.i4.3
0x1a7b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1a80  brtrue.s loc_1A89
0x1a82  ldc.i4.m1
0x1a83  stloc.0
0x1a84  br       loc_1B48
0x1a89  ldloc.s  0xC
0x1a8b  ldc.i4.0
0x1a8c  ldc.i4.0
0x1a8d  ldloca.s 0xE
0x1a8f  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::GetOrderedArray(valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileOrderBy, valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.SortOrder, class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile[]&)
0x1a94  ldc.i4.0
0x1a95  stloc.s  0x10
0x1a97  ldsfld   string [mscorlib]System.String::Empty
0x1a9c  stloc.s  0x11
0x1a9e  ldsfld   string [mscorlib]System.String::Empty
0x1aa3  stloc.s  0x12
0x1aa5  ldc.i4.0
0x1aa6  stloc.s  0x13
0x1aa8  ldc.i4.0
0x1aa9  stloc.s  0x14
0x1aab  br.s     loc_1B12
0x1aad  ldloc.s  0xE
0x1aaf  ldloc.s  0x14
0x1ab1  ldelem.ref
0x1ab2  stloc.s  0x15
0x1ab4  ldloc.s  0x15
0x1ab6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x1abb  ldstr    aAspx// ".aspx"
0x1ac0  ldc.i4.3
0x1ac1  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1ac6  brfalse.s loc_1B0C
0x1ac8  ldloc.s  0x10
0x1aca  ldc.i4.1
0x1acb  add
0x1acc  stloc.s  0x10
0x1ace  ldloc.s  0x13
0x1ad0  brfalse.s loc_1AE6
0x1ad2  ldloc.s  0x12
0x1ad4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ad9  brfalse.s loc_1AE6
0x1adb  ldloc.s  0x15
0x1add  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x1ae2  stloc.s  0x12
0x1ae4  br.s     loc_1B1A
0x1ae6  ldloc.s  0x15
0x1ae8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x1aed  ldloc.s  0xD
0x1aef  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x1af4  ldc.i4.3
0x1af5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1afa  brfalse.s loc_1AFF
0x1afc  ldc.i4.1
0x1afd  stloc.s  0x13
0x1aff  ldloc.s  0x13
0x1b01  brtrue.s loc_1B0C
0x1b03  ldloc.s  0x15
0x1b05  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x1b0a  stloc.s  0x11
0x1b0c  ldloc.s  0x14
0x1b0e  ldc.i4.1
0x1b0f  add
0x1b10  stloc.s  0x14
0x1b12  ldloc.s  0x14
0x1b14  ldloc.s  0xE
0x1b16  ldlen
0x1b17  conv.i4
0x1b18  blt.s    loc_1AAD
0x1b1a  ldloc.s  7
0x1b1c  brtrue.s loc_1B27
0x1b1e  ldloc.s  0x10
0x1b20  ldc.i4.1
0x1b21  bgt.s    loc_1B27
0x1b23  ldc.i4.1
0x1b24  stloc.0
0x1b25  br.s     loc_1B48
0x1b27  ldloc.s  0x12
0x1b29  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b2e  brtrue.s loc_1B34
0x1b30  ldloc.s  0x12
0x1b32  br.s     loc_1B36
0x1b34  ldloc.s  0x11
0x1b36  stloc.s  9
0x1b38  ldloc.s  0xC
0x1b3a  ldloc.s  0xD
0x1b3c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x1b41  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::DeleteFile(string)
0x1b46  ldc.i4.0
0x1b47  stloc.0
0x1b48  leave.s  loc_1B51
0x1b4a  pop
0x1b4b  ldc.i4.m1
0x1b4c  stloc.0
0x1b4d  leave.s  loc_1B51
0x1b4f  ldc.i4.2
0x1b50  stloc.0
0x1b51  ldloc.0
0x1b52  ldc.i4.0
0x1b53  ceq
0x1b55  stloc.s  0x16
0x1b57  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1b5c  stloc.s  0x17
0x1b5e  ldloc.s  0x17
0x1b60  ldstr    aDeletepageresp// "DeletePageResponse"
0x1b65  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1b6a  stloc.s  0x18
0x1b6c  ldloc.s  0x18
0x1b6e  ldstr    aSuccess_0// "success"
0x1b73  ldloca.s 0x16
0x1b75  call     instance string [mscorlib]System.Boolean::ToString()
0x1b7a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1b7f  ldloc.s  9
0x1b81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b86  brtrue.s loc_1B96
0x1b88  ldloc.s  0x18
0x1b8a  ldstr    aDisplaynext// "displayNext"
0x1b8f  ldloc.s  9
0x1b91  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1b96  ldloc.s  0x17
0x1b98  ldloc.s  0x18
0x1b9a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1b9f  pop
0x1ba0  ldloc.s  0x17
0x1ba2  ldstr    aPage// "Page"
0x1ba7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1bac  stloc.s  0x19
0x1bae  ldloc.s  0x19
0x1bb0  ldstr    aUrl_0// "url"
0x1bb5  ldloc.s  8
0x1bb7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1bbc  ldloc.s  0x19
0x1bbe  ldstr    aResult// "result"
0x1bc3  ldloca.s 0
0x1bc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bca  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1bcf  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1bd4  ldloc.s  0x18
0x1bd6  ldloc.s  0x19
0x1bd8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1bdd  pop
0x1bde  ldloc.s  0x17
0x1be0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x1be5  ret
```
