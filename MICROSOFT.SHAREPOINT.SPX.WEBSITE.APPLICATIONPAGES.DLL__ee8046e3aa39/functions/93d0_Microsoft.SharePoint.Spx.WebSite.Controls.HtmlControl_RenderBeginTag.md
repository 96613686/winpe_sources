# Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::RenderBeginTag

- ea: `0x93d0`
- end: `0x9421`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::RenderBeginTag`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0x7bc0`
- `0x93d0`

## string_xrefs

- `0x93d3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x93d0  ldarg.1
0x93d1  brtrue.s loc_93DE
0x93d3  ldstr    aWriter// "writer"
0x93d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x93dd  throw
0x93de  ldarg.0
0x93df  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x93e4  brtrue.s loc_9411
0x93e6  ldarg.1
0x93e7  ldc.i4.s 0x3D
0x93e9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x93ee  ldarg.1
0x93ef  ldstr    aHtmlcontrolNos// "HtmlControl.NoScriptMsg"
0x93f4  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x93f9  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x93fe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9403  ldarg.1
0x9404  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x9409  ldarg.0
0x940a  ldarg.1
0x940b  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x9410  ret
0x9411  ldarg.0
0x9412  ldarg.1
0x9413  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::AddAttributesToRender(class [System.Web]System.Web.UI.HtmlTextWriter)
0x9418  ldarg.1
0x9419  ldc.i4.s 0x19
0x941b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x9420  ret
```
