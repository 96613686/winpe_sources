# Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::RenderBeginTag

- ea: `0x80a0`
- end: `0x812b`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::RenderBeginTag`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0x80a0`

## string_xrefs

- `0x80a3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.1
0x80a1  brtrue.s loc_80AE
0x80a3  ldstr    aWriter// "writer"
0x80a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80ad  throw
0x80ae  ldarg.0
0x80af  ldarg.1
0x80b0  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x80b5  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x80ba  stloc.0
0x80bb  ldloca.s 0
0x80bd  ldarg.0
0x80be  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x80c3  box      [System.Web]System.Web.UI.WebControls.Unit
0x80c8  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x80ce  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x80d3  brtrue.s loc_812A
0x80d5  ldarg.0
0x80d6  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x80db  brtrue.s loc_812A
0x80dd  ldarg.0
0x80de  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x80e3  brfalse.s loc_812A
0x80e5  ldarg.0
0x80e6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x80eb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x80f0  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x80f5  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x80fa  ldstr    aFirefox// "Firefox"
0x80ff  callvirt instance bool [mscorlib]System.String::Contains(string)
0x8104  brfalse.s loc_812A
0x8106  ldarg.1
0x8107  ldc.i4.s 0xD
0x8109  ldarg.0
0x810a  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x810f  stloc.1
0x8110  ldloca.s 1
0x8112  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x8118  callvirt instance string [mscorlib]System.Object::ToString()
0x811d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8122  ldarg.1
0x8123  ldc.i4.s 0x19
0x8125  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x812a  ret
```
