# Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::RenderBeginTag

- ea: `0x153f0`
- end: `0x15441`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::RenderBeginTag`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a10`
- `0x7bc0`
- `0x153f0`

## string_xrefs

- `0x153f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x153f0  ldarg.1
0x153f1  brtrue.s loc_153FE
0x153f3  ldstr    aWriter// "writer"
0x153f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x153fd  throw
0x153fe  ldarg.0
0x153ff  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x15404  brtrue.s loc_15431
0x15406  ldarg.1
0x15407  ldc.i4.s 0x3D
0x15409  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1540e  ldarg.1
0x1540f  ldstr    aVideocontrolNo// "VideoControl.NoScriptMsg"
0x15414  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x15419  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x1541e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15423  ldarg.1
0x15424  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x15429  ldarg.0
0x1542a  ldarg.1
0x1542b  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x15430  ret
0x15431  ldarg.0
0x15432  ldarg.1
0x15433  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::AddAttributesToRender(class [System.Web]System.Web.UI.HtmlTextWriter)
0x15438  ldarg.1
0x15439  ldc.i4.s 0x19
0x1543b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x15440  ret
```
