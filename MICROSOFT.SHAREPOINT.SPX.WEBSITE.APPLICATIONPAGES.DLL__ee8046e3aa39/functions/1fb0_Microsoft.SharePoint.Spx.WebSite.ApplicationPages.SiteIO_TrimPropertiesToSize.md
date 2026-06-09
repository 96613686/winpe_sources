# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::TrimPropertiesToSize

- ea: `0x1fb0`
- end: `0x215a`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::TrimPropertiesToSize`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e30`

## callees

- `0x770`
- `0x1fb0`

## string_xrefs

- `0x1fb5`: `footerlinks`
- `0x203c`: `footerlink-name`
- `0x204d`: `footerlink-link`
- `0x205b`: `//Link`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  ldc.i4.1
0x1fb1  stloc.0
0x1fb2  ldc.i4.0
0x1fb3  stloc.1
0x1fb4  ldarg.0
0x1fb5  ldstr    aFooterlinks// "footerlinks"
0x1fba  ldc.i4.5
0x1fbb  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1fc0  brtrue.s loc_1FD5
0x1fc2  ldsfld   class Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::Instance
0x1fc7  ldarg.0
0x1fc8  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::GetPropertyLimit(string propertyName)
0x1fcd  stloc.1
0x1fce  ldloc.1
0x1fcf  brtrue.s loc_1FD3
0x1fd1  ldarg.1
0x1fd2  ret
0x1fd3  ldc.i4.0
0x1fd4  stloc.0
0x1fd5  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1fda  stloc.2
0x1fdb  ldloc.2
0x1fdc  ldnull
0x1fdd  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x1fe2  ldloc.2
0x1fe3  ldstr    aPropertyProper// "<Property></Property>"
0x1fe8  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x1fed  ldloc.2
0x1fee  ldstr    aProperty// "/Property"
0x1ff3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1ff8  stloc.3
0x1ff9  ldnull
0x1ffa  stloc.s  4
0x1ffc  ldloc.3
0x1ffd  ldloc.0
0x1ffe  brtrue.s loc_2003
0x2000  ldarg.1
0x2001  br.s     loc_2009
0x2003  ldarg.1
0x2004  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::HtmlDecode(string)
0x2009  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x200e  ldloc.3
0x200f  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x2014  brfalse.s loc_202E
0x2016  ldloc.3
0x2017  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x201c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x2021  ldc.i4.3
0x2022  beq.s    loc_202E
0x2024  ldloc.3
0x2025  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x202a  stloc.s  4
0x202c  br.s     loc_2031
0x202e  ldloc.3
0x202f  stloc.s  4
0x2031  ldloc.0
0x2032  brfalse  loc_211A
0x2037  ldsfld   class Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::Instance
0x203c  ldstr    aFooterlinkName// "footerlink-name"
0x2041  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::GetPropertyLimit(string propertyName)
0x2046  stloc.s  5
0x2048  ldsfld   class Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::Instance
0x204d  ldstr    aFooterlinkLink// "footerlink-link"
0x2052  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::GetPropertyLimit(string propertyName)
0x2057  stloc.s  6
0x2059  ldloc.s  4
0x205b  ldstr    aLink// "//Link"
0x2060  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2065  stloc.s  7
0x2067  ldloc.s  7
0x2069  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x206e  stloc.s  0xB
0x2070  br       loc_20F7
0x2075  ldloc.s  0xB
0x2077  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x207c  castclass [System.Xml]System.Xml.XmlNode
0x2081  stloc.s  8
0x2083  ldloc.s  5
0x2085  ldc.i4.0
0x2086  ble.s    loc_20BD
0x2088  ldloc.s  8
0x208a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x208f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2094  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2099  ldloc.s  5
0x209b  ble.s    loc_20BD
0x209d  ldloc.s  8
0x209f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x20a4  ldloc.s  8
0x20a6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x20ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x20b0  ldc.i4.0
0x20b1  ldloc.s  5
0x20b3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x20b8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x20bd  ldloc.s  6
0x20bf  ldc.i4.0
0x20c0  ble.s    loc_20F7
0x20c2  ldloc.s  8
0x20c4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_LastChild()
0x20c9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x20ce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20d3  ldloc.s  6
0x20d5  ble.s    loc_20F7
0x20d7  ldloc.s  8
0x20d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_LastChild()
0x20de  ldloc.s  8
0x20e0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_LastChild()
0x20e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x20ea  ldc.i4.0
0x20eb  ldloc.s  6
0x20ed  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x20f2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x20f7  ldloc.s  0xB
0x20f9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20fe  brtrue   loc_2075
0x2103  leave.s  loc_2147
0x2105  ldloc.s  0xB
0x2107  isinst   [mscorlib]System.IDisposable
0x210c  stloc.s  0xC
0x210e  ldloc.s  0xC
0x2110  brfalse.s loc_2119
0x2112  ldloc.s  0xC
0x2114  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2119  endfinally
0x211a  ldloc.s  4
0x211c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2121  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::HtmlDecode(string)
0x2126  stloc.s  9
0x2128  ldloc.s  9
0x212a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x212f  ldloc.1
0x2130  ble.s    loc_2147
0x2132  ldloc.s  4
0x2134  ldloc.s  9
0x2136  ldc.i4.0
0x2137  ldloc.1
0x2138  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x213d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::HtmlEncode(string)
0x2142  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x2147  ldloc.3
0x2148  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x214d  stloc.s  0xA
0x214f  leave.s  loc_2157
0x2151  pop
0x2152  ldarg.1
0x2153  stloc.s  0xA
0x2155  leave.s  loc_2157
0x2157  ldloc.s  0xA
0x2159  ret
```
