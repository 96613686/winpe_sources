# Microsoft.SharePoint.Spx.WebSite.Controls.LMTControl::RenderBeginTag

- ea: `0x9740`
- end: `0x97eb`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LMTControl::RenderBeginTag`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0x9740`

## string_xrefs

- `0x9743`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x9740  ldarg.1
0x9741  brtrue.s loc_974E
0x9743  ldstr    aWriter// "writer"
0x9748  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x974d  throw
0x974e  ldarg.0
0x974f  ldarg.1
0x9750  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x9755  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x975a  stloc.0
0x975b  ldloca.s 0
0x975d  ldarg.0
0x975e  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x9763  box      [System.Web]System.Web.UI.WebControls.Unit
0x9768  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x976e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9773  brtrue.s loc_97EA
0x9775  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x977a  stloc.1
0x977b  ldloca.s 1
0x977d  ldarg.0
0x977e  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x9783  box      [System.Web]System.Web.UI.WebControls.Unit
0x9788  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x978e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9793  brtrue.s loc_97EA
0x9795  ldarg.0
0x9796  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x979b  brtrue.s loc_97EA
0x979d  ldarg.0
0x979e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x97a3  brfalse.s loc_97EA
0x97a5  ldarg.0
0x97a6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x97ab  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x97b0  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x97b5  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x97ba  ldstr    aFirefox// "Firefox"
0x97bf  callvirt instance bool [mscorlib]System.String::Contains(string)
0x97c4  brfalse.s loc_97EA
0x97c6  ldarg.1
0x97c7  ldc.i4.s 0xD
0x97c9  ldarg.0
0x97ca  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x97cf  stloc.2
0x97d0  ldloca.s 2
0x97d2  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x97d8  callvirt instance string [mscorlib]System.Object::ToString()
0x97dd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x97e2  ldarg.1
0x97e3  ldc.i4.s 0x19
0x97e5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x97ea  ret
```
