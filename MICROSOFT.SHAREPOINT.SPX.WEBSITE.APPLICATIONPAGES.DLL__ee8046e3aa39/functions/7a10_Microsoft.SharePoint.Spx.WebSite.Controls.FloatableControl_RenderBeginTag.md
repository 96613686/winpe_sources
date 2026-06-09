# Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag

- ea: `0x7a10`
- end: `0x7b18`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderBeginTag`
- size: `264`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x80a0`
- `0x93d0`
- `0x9740`
- `0xb960`
- `0x13360`
- `0x153f0`

## callees

- `0x79f0`
- `0x7a10`

## string_xrefs

- `0x7a13`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x7a10  ldarg.1
0x7a11  brtrue.s loc_7A1E
0x7a13  ldstr    aWriter// "writer"
0x7a18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7a1d  throw
0x7a1e  ldarg.0
0x7a1f  ldarg.1
0x7a20  call     instance void [System.Web]System.Web.UI.WebControls.WebControl::RenderBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7a25  ldarg.0
0x7a26  callvirt instance valuetype [System.Web]System.Web.UI.HtmlTextWriterTag [System.Web]System.Web.UI.WebControls.WebControl::get_TagKey()
0x7a2b  ldc.i4.s 0x4C
0x7a2d  bne.un   loc_7B17
0x7a32  ldarg.0
0x7a33  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x7a38  brtrue   loc_7B17
0x7a3d  ldarg.0
0x7a3e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x7a43  brfalse  loc_7B17
0x7a48  ldarg.0
0x7a49  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x7a4e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7a53  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x7a58  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x7a5d  ldstr    aFirefox// "Firefox"
0x7a62  callvirt instance bool [mscorlib]System.String::Contains(string)
0x7a67  brfalse  loc_7B17
0x7a6c  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x7a71  stloc.0
0x7a72  ldloca.s 0
0x7a74  ldarg.0
0x7a75  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x7a7a  box      [System.Web]System.Web.UI.WebControls.Unit
0x7a7f  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7a85  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7a8a  brtrue   loc_7B17
0x7a8f  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x7a94  stloc.1
0x7a95  ldloca.s 1
0x7a97  ldarg.0
0x7a98  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x7a9d  box      [System.Web]System.Web.UI.WebControls.Unit
0x7aa2  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7aa8  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7aad  brtrue.s loc_7B17
0x7aaf  ldarg.1
0x7ab0  ldc.i4.s 0x1B
0x7ab2  ldarg.0
0x7ab3  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::get_Overflow()
0x7ab8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x7abd  ldarg.1
0x7abe  ldc.i4.s 0xB
0x7ac0  ldarg.0
0x7ac1  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x7ac6  stloc.2
0x7ac7  ldloca.s 2
0x7ac9  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7acf  callvirt instance string [mscorlib]System.Object::ToString()
0x7ad4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x7ad9  ldarg.1
0x7ada  ldc.i4.s 0xD
0x7adc  ldarg.0
0x7add  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x7ae2  stloc.3
0x7ae3  ldloca.s 3
0x7ae5  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x7aeb  callvirt instance string [mscorlib]System.Object::ToString()
0x7af0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x7af5  ldarg.1
0x7af6  ldc.i4.s 0x12
0x7af8  ldstr    aMozInlineBox// "-moz-inline-box"
0x7afd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x7b02  ldarg.1
0x7b03  ldc.i4.s 0x25
0x7b05  ldstr    aTextBottom// "text-bottom"
0x7b0a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x7b0f  ldarg.1
0x7b10  ldc.i4.s 0x4C
0x7b12  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x7b17  ret
```
