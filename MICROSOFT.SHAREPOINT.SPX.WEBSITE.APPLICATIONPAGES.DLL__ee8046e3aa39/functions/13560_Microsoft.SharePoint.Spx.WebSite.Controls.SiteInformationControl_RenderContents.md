# Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderContents

- ea: `0x13560`
- end: `0x13600`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderContents`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x132b0`
- `0x13560`

## string_xrefs

- `0x13563`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x13560  ldarg.1
0x13561  brtrue.s loc_1356E
0x13563  ldstr    aWriter// "writer"
0x13568  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1356d  throw
0x1356e  ldarg.0
0x1356f  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::get_InfoType()
0x13574  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13579  brtrue   loc_135FF
0x1357e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x13583  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x13588  stloc.0
0x13589  ldloc.0
0x1358a  ldarg.0
0x1358b  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::get_InfoType()
0x13590  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x13595  stloc.1
0x13596  ldarg.1
0x13597  ldc.i4.s 0x4C
0x13599  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1359e  ldloc.1
0x1359f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x135a4  brtrue.s loc_135F4
0x135a6  ldstr    aText// "<Text>"
0x135ab  ldloc.1
0x135ac  ldstr    aText_0// "</Text>"
0x135b1  call     string [mscorlib]System.String::Concat(string, string, string)
0x135b6  stloc.1
0x135b7  ldloc.1
0x135b8  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x135bd  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x135c2  stloc.2
0x135c3  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x135c8  stloc.3
0x135c9  ldloc.3
0x135ca  ldnull
0x135cb  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x135d0  ldloc.3
0x135d1  ldloc.2
0x135d2  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x135d7  ldarg.1
0x135d8  ldloc.3
0x135d9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x135de  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0x135e3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x135e8  leave.s  loc_135F4
0x135ea  ldloc.2
0x135eb  brfalse.s loc_135F3
0x135ed  ldloc.2
0x135ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x135f3  endfinally
0x135f4  ldarg.1
0x135f5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x135fa  leave.s  loc_135FF
0x135fc  pop
0x135fd  leave.s  loc_135FF
0x135ff  ret
```
