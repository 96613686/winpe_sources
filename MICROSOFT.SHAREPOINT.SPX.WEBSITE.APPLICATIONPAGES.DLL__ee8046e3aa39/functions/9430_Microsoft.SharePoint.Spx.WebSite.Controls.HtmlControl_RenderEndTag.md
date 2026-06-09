# Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::RenderEndTag

- ea: `0x9430`
- end: `0x94f8`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::RenderEndTag`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0x91f0`
- `0x9260`
- `0x9430`

## string_xrefs

- `0x9433`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x9430  ldarg.1
0x9431  brtrue.s loc_943E
0x9433  ldstr    aWriter// "writer"
0x9438  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x943d  throw
0x943e  ldarg.0
0x943f  ldarg.1
0x9440  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x9445  ldarg.0
0x9446  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x944b  brtrue   loc_94F7
0x9450  ldarg.1
0x9451  ldc.i4.s 0x23
0x9453  ldstr    aTextJavascript// "text/javascript"
0x9458  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x945d  ldarg.1
0x945e  ldc.i4.s 0x49
0x9460  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x9465  ldarg.1
0x9466  ldstr    aSettimeout// "setTimeout('"
0x946b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9470  ldarg.1
0x9471  ldc.i4.s 9
0x9473  newarr   [mscorlib]System.Object
0x9478  stloc.0
0x9479  ldloc.0
0x947a  ldc.i4.0
0x947b  ldstr    aHtmlcontroljsL// "HtmlControlJS.loadFrame('"
0x9480  stelem.ref
0x9481  ldloc.0
0x9482  ldc.i4.1
0x9483  ldarg.0
0x9484  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x9489  ldc.i4.0
0x948a  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x948f  stelem.ref
0x9490  ldloc.0
0x9491  ldc.i4.2
0x9492  ldstr    asc_25202// "', '"
0x9497  stelem.ref
0x9498  ldloc.0
0x9499  ldc.i4.3
0x949a  ldarg.0
0x949b  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::get_Content()
0x94a0  ldc.i4.0
0x94a1  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x94a6  stelem.ref
0x94a7  ldloc.0
0x94a8  ldc.i4.4
0x94a9  ldstr    asc_2520C// "',"
0x94ae  stelem.ref
0x94af  ldloc.0
0x94b0  ldc.i4.5
0x94b1  ldarg.0
0x94b2  call     instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.HtmlControl::get_CultureID()
0x94b7  box      [mscorlib]System.Int32
0x94bc  stelem.ref
0x94bd  ldloc.0
0x94be  ldc.i4.6
0x94bf  ldstr    asc_25212// ", '"
0x94c4  stelem.ref
0x94c5  ldloc.0
0x94c6  ldc.i4.7
0x94c7  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Constants::get_AssemblyFileVersion()
0x94cc  stelem.ref
0x94cd  ldloc.0
0x94ce  ldc.i4.8
0x94cf  ldstr    asc_2521A// "');"
0x94d4  stelem.ref
0x94d5  ldloc.0
0x94d6  call     string [mscorlib]System.String::Concat(object[])
0x94db  ldc.i4.0
0x94dc  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x94e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x94e6  ldarg.1
0x94e7  ldstr    a0_1// "', 0);"
0x94ec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x94f1  ldarg.1
0x94f2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x94f7  ret
```
