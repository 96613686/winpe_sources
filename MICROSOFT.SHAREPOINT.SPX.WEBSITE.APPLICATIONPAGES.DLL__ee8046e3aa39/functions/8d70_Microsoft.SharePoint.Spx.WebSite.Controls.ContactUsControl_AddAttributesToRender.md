# Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::AddAttributesToRender

- ea: `0x8d70`
- end: `0x8e1a`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::AddAttributesToRender`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7bd0`
- `0x8d70`

## string_xrefs

- `0x8d73`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x8d70  ldarg.1
0x8d71  brtrue.s loc_8D7E
0x8d73  ldstr    aWriter// "writer"
0x8d78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8d7d  throw
0x8d7e  ldarg.0
0x8d7f  ldarg.1
0x8d80  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::AddAttributesToRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x8d85  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x8d8a  stloc.0
0x8d8b  ldloca.s 0
0x8d8d  ldarg.0
0x8d8e  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x8d93  box      [System.Web]System.Web.UI.WebControls.Unit
0x8d98  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x8d9e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x8da3  brfalse.s loc_8DC0
0x8da5  ldarg.1
0x8da6  ldc.i4.s 0xD
0x8da8  ldstr    a100// "100%"
0x8dad  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8db2  ldarg.1
0x8db3  ldc.i4.s 0x12
0x8db5  ldstr    aBlock// "block"
0x8dba  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8dbf  ret
0x8dc0  ldarg.0
0x8dc1  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x8dc6  brtrue.s loc_8E0C
0x8dc8  ldarg.0
0x8dc9  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8dce  brfalse.s loc_8E0C
0x8dd0  ldarg.0
0x8dd1  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8dd6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8ddb  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x8de0  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x8de5  ldstr    aFirefox// "Firefox"
0x8dea  callvirt instance bool [mscorlib]System.String::Contains(string)
0x8def  brfalse.s loc_8E0C
0x8df1  ldarg.1
0x8df2  ldc.i4.s 0x12
0x8df4  ldstr    aMozInlineBox// "-moz-inline-box"
0x8df9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8dfe  ldarg.1
0x8dff  ldc.i4.s 0x25
0x8e01  ldstr    aTextBottom// "text-bottom"
0x8e06  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8e0b  ret
0x8e0c  ldarg.1
0x8e0d  ldc.i4.s 0x12
0x8e0f  ldstr    aInlineBlock// "inline-block"
0x8e14  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8e19  ret
```
