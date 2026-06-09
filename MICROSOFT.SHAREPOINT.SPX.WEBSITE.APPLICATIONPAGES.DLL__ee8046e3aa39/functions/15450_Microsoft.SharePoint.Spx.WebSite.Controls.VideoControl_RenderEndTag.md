# Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::RenderEndTag

- ea: `0x15450`
- end: `0x15518`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::RenderEndTag`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0x15220`
- `0x15290`
- `0x15450`

## string_xrefs

- `0x15453`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x15450  ldarg.1
0x15451  brtrue.s loc_1545E
0x15453  ldstr    aWriter// "writer"
0x15458  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1545d  throw
0x1545e  ldarg.0
0x1545f  ldarg.1
0x15460  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x15465  ldarg.0
0x15466  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x1546b  brtrue   loc_15517
0x15470  ldarg.1
0x15471  ldc.i4.s 0x23
0x15473  ldstr    aTextJavascript// "text/javascript"
0x15478  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x1547d  ldarg.1
0x1547e  ldc.i4.s 0x49
0x15480  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x15485  ldarg.1
0x15486  ldstr    aSettimeout// "setTimeout('"
0x1548b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15490  ldarg.1
0x15491  ldc.i4.s 9
0x15493  newarr   [mscorlib]System.Object
0x15498  stloc.0
0x15499  ldloc.0
0x1549a  ldc.i4.0
0x1549b  ldstr    aVideocontroljs// "VideoControlJS.loadFrame('"
0x154a0  stelem.ref
0x154a1  ldloc.0
0x154a2  ldc.i4.1
0x154a3  ldarg.0
0x154a4  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x154a9  ldc.i4.0
0x154aa  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x154af  stelem.ref
0x154b0  ldloc.0
0x154b1  ldc.i4.2
0x154b2  ldstr    asc_25202// "', '"
0x154b7  stelem.ref
0x154b8  ldloc.0
0x154b9  ldc.i4.3
0x154ba  ldarg.0
0x154bb  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::get_Content()
0x154c0  ldc.i4.0
0x154c1  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x154c6  stelem.ref
0x154c7  ldloc.0
0x154c8  ldc.i4.4
0x154c9  ldstr    asc_2520C// "',"
0x154ce  stelem.ref
0x154cf  ldloc.0
0x154d0  ldc.i4.5
0x154d1  ldarg.0
0x154d2  call     instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.VideoControl::get_CultureID()
0x154d7  box      [mscorlib]System.Int32
0x154dc  stelem.ref
0x154dd  ldloc.0
0x154de  ldc.i4.6
0x154df  ldstr    asc_25212// ", '"
0x154e4  stelem.ref
0x154e5  ldloc.0
0x154e6  ldc.i4.7
0x154e7  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Constants::get_AssemblyFileVersion()
0x154ec  stelem.ref
0x154ed  ldloc.0
0x154ee  ldc.i4.8
0x154ef  ldstr    asc_2521A// "');"
0x154f4  stelem.ref
0x154f5  ldloc.0
0x154f6  call     string [mscorlib]System.String::Concat(object[])
0x154fb  ldc.i4.0
0x154fc  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x15501  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15506  ldarg.1
0x15507  ldstr    a0_1// "', 0);"
0x1550c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15511  ldarg.1
0x15512  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x15517  ret
```
