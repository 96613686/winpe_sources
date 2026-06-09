# Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag

- ea: `0x7b20`
- end: `0x7bb7`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8130`
- `0x9430`
- `0x97f0`
- `0xb910`
- `0x133f0`
- `0x15450`

## callees

- `0x7b20`

## string_xrefs

- `0x7b23`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x7b20  ldarg.1
0x7b21  brtrue.s loc_7B2E
0x7b23  ldstr    aWriter// "writer"
0x7b28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7b2d  throw
0x7b2e  ldarg.0
0x7b2f  callvirt instance valuetype [System.Web]System.Web.UI.HtmlTextWriterTag [System.Web]System.Web.UI.WebControls.WebControl::get_TagKey()
0x7b34  ldc.i4.s 0x4C
0x7b36  bne.un.s loc_7BAF
0x7b38  ldarg.0
0x7b39  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x7b3e  brtrue.s loc_7BAF
0x7b40  ldarg.0
0x7b41  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x7b46  brfalse.s loc_7BAF
0x7b48  ldarg.0
0x7b49  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x7b4e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7b53  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x7b58  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x7b5d  ldstr    aFirefox// "Firefox"
0x7b62  callvirt instance bool [mscorlib]System.String::Contains(string)
0x7b67  brfalse.s loc_7BAF
0x7b69  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x7b6e  stloc.0
0x7b6f  ldloca.s 0
0x7b71  ldarg.0
0x7b72  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x7b77  box      [System.Web]System.Web.UI.WebControls.Unit
0x7b7c  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7b82  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7b87  brtrue.s loc_7BAF
0x7b89  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x7b8e  stloc.1
0x7b8f  ldloca.s 1
0x7b91  ldarg.0
0x7b92  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x7b97  box      [System.Web]System.Web.UI.WebControls.Unit
0x7b9c  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7ba2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7ba7  brtrue.s loc_7BAF
0x7ba9  ldarg.1
0x7baa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x7baf  ldarg.0
0x7bb0  ldarg.1
0x7bb1  call     instance void [System.Web]System.Web.UI.WebControls.WebControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7bb6  ret
```
