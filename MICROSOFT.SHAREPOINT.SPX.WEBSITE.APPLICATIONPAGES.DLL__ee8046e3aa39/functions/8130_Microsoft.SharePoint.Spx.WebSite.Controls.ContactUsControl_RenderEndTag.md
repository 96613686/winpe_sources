# Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::RenderEndTag

- ea: `0x8130`
- end: `0x819d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::RenderEndTag`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0x8130`

## string_xrefs

- `0x8133`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x8130  ldarg.1
0x8131  brtrue.s loc_813E
0x8133  ldstr    aWriter// "writer"
0x8138  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x813d  throw
0x813e  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x8143  stloc.0
0x8144  ldloca.s 0
0x8146  ldarg.0
0x8147  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x814c  box      [System.Web]System.Web.UI.WebControls.Unit
0x8151  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x8157  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x815c  brtrue.s loc_8195
0x815e  ldarg.0
0x815f  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x8164  brtrue.s loc_8195
0x8166  ldarg.0
0x8167  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x816c  brfalse.s loc_8195
0x816e  ldarg.0
0x816f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8174  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8179  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x817e  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x8183  ldstr    aFirefox// "Firefox"
0x8188  callvirt instance bool [mscorlib]System.String::Contains(string)
0x818d  brfalse.s loc_8195
0x818f  ldarg.1
0x8190  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x8195  ldarg.0
0x8196  ldarg.1
0x8197  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x819c  ret
```
