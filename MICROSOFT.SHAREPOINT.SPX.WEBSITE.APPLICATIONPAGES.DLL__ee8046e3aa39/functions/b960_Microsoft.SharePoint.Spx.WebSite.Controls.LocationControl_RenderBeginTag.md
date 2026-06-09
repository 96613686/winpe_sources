# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderBeginTag

- ea: `0xb960`
- end: `0xb9af`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderBeginTag`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0xb960`

## string_xrefs

- `0xb963`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xb960  ldarg.1
0xb961  brtrue.s loc_B96E
0xb963  ldstr    aWriter// "writer"
0xb968  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb96d  throw
0xb96e  ldarg.0
0xb96f  ldarg.1
0xb970  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xb975  ldarg.0
0xb976  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0xb97b  brtrue.s loc_B9AE
0xb97d  ldarg.0
0xb97e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xb983  brfalse.s loc_B9AE
0xb985  ldarg.0
0xb986  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xb98b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb990  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0xb995  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0xb99a  ldstr    aFirefox// "Firefox"
0xb99f  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb9a4  brfalse.s loc_B9AE
0xb9a6  ldarg.1
0xb9a7  ldc.i4.s 0x19
0xb9a9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xb9ae  ret
```
