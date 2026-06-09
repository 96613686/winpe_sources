# Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderBeginTag

- ea: `0x13360`
- end: `0x133eb`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderBeginTag`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0x13360`

## string_xrefs

- `0x13363`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x13360  ldarg.1
0x13361  brtrue.s loc_1336E
0x13363  ldstr    aWriter// "writer"
0x13368  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1336d  throw
0x1336e  ldarg.0
0x1336f  ldarg.1
0x13370  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x13375  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x1337a  stloc.0
0x1337b  ldloca.s 0
0x1337d  ldarg.0
0x1337e  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x13383  box      [System.Web]System.Web.UI.WebControls.Unit
0x13388  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x1338e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13393  brtrue.s loc_133EA
0x13395  ldarg.0
0x13396  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x1339b  brtrue.s loc_133EA
0x1339d  ldarg.0
0x1339e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x133a3  brfalse.s loc_133EA
0x133a5  ldarg.0
0x133a6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x133ab  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x133b0  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x133b5  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x133ba  ldstr    aFirefox// "Firefox"
0x133bf  callvirt instance bool [mscorlib]System.String::Contains(string)
0x133c4  brfalse.s loc_133EA
0x133c6  ldarg.1
0x133c7  ldc.i4.s 0xD
0x133c9  ldarg.0
0x133ca  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x133cf  stloc.1
0x133d0  ldloca.s 1
0x133d2  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x133d8  callvirt instance string [mscorlib]System.Object::ToString()
0x133dd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x133e2  ldarg.1
0x133e3  ldc.i4.s 0x19
0x133e5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x133ea  ret
```
