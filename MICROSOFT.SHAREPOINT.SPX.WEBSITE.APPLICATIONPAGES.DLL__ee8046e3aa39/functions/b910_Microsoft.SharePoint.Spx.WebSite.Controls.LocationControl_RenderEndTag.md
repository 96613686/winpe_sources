# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderEndTag

- ea: `0xb910`
- end: `0xb95d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderEndTag`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0xb910`

## string_xrefs

- `0xb913`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xb910  ldarg.1
0xb911  brtrue.s loc_B91E
0xb913  ldstr    aWriter// "writer"
0xb918  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb91d  throw
0xb91e  ldarg.0
0xb91f  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0xb924  brtrue.s loc_B955
0xb926  ldarg.0
0xb927  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xb92c  brfalse.s loc_B955
0xb92e  ldarg.0
0xb92f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xb934  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb939  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0xb93e  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0xb943  ldstr    aFirefox// "Firefox"
0xb948  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb94d  brfalse.s loc_B955
0xb94f  ldarg.1
0xb950  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xb955  ldarg.0
0xb956  ldarg.1
0xb957  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xb95c  ret
```
