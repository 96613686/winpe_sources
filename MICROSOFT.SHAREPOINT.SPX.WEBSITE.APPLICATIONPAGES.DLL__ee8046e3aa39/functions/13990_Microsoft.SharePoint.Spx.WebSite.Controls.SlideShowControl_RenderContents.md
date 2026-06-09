# Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::RenderContents

- ea: `0x13990`
- end: `0x14449`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::RenderContents`
- size: `2745`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x7bc0`
- `0x136e0`
- `0x13720`
- `0x137a0`
- `0x137e0`
- `0x13880`
- `0x13990`
- `0x14560`
- `0x14590`
- `0x14610`
- `0x14650`
- `0x14790`

## string_xrefs

- `0x143a0`: `<div style='height: {0}px; width: {1}px'>\n   <object data='data:application/x-silverlight,' type='application/x-silverlight-2' width='100%' height='100%'>\n       <param name='source' value='{2}'/>\n       <param name='minRuntimeVersion' value='{3}' />\n       <param name='autoUpgrade' value='true' />\n       <param name='initParams' value='{4}' />\n       <a href='https://go.microsoft.com/fwlink/?LinkID=124807' style='text-decoration: none;'>\n           <img src='https://go.microsoft.com/fwli`

## pseudocode

```c

```

## disassembly

```asm
0x13990  ldarg.1
0x13991  ldc.i4.s 0x11
0x13993  ldarg.0
0x13994  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13999  ldstr    aContainer// "_Container"
0x1399e  call     string [mscorlib]System.String::Concat(string, string)
0x139a3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x139a8  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x139ad  stloc.s  0xE
0x139af  ldloca.s 0xE
0x139b1  ldarg.0
0x139b2  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x139b7  box      [System.Web]System.Web.UI.WebControls.Unit
0x139bc  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x139c2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x139c7  brfalse.s loc_139D8
0x139c9  ldarg.1
0x139ca  ldc.i4.s 0xD
0x139cc  ldstr    a100// "100%"
0x139d1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x139d6  br.s     loc_13A26
0x139d8  ldarg.0
0x139d9  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x139de  brtrue.s loc_13A26
0x139e0  ldarg.0
0x139e1  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x139e6  brfalse.s loc_13A26
0x139e8  ldarg.0
0x139e9  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x139ee  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139f3  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x139f8  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x139fd  ldstr    aFirefox// "Firefox"
0x13a02  callvirt instance bool [mscorlib]System.String::Contains(string)
0x13a07  brfalse.s loc_13A26
0x13a09  ldarg.1
0x13a0a  ldc.i4.s 0xD
0x13a0c  ldarg.0
0x13a0d  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x13a12  stloc.s  0xF
0x13a14  ldloca.s 0xF
0x13a16  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x13a1c  callvirt instance string [mscorlib]System.Object::ToString()
0x13a21  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13a26  ldarg.1
0x13a27  ldc.i4.s 0x19
0x13a29  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13a2e  ldc.i4.0
0x13a2f  stloc.0
0x13a30  ldarg.0
0x13a31  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13a36  brtrue.s loc_13A95
0x13a38  ldarg.0
0x13a39  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13a3e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13a43  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13a48  ldarg.0
0x13a49  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13a4e  ldstr    aStartindex// "_StartIndex"
0x13a53  call     string [mscorlib]System.String::Concat(string, string)
0x13a58  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13a5d  stloc.1
0x13a5e  ldloc.1
0x13a5f  brfalse.s loc_13A95
0x13a61  ldloc.1
0x13a62  callvirt instance string [mscorlib]System.String::Trim()
0x13a67  stloc.1
0x13a68  ldloc.1
0x13a69  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a6e  brfalse.s loc_13A81
0x13a70  ldloc.1
0x13a71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a76  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x13a7b  stloc.0
0x13a7c  leave.s  loc_13A81
0x13a7e  pop
0x13a7f  leave.s  loc_13A81
0x13a81  ldloc.0
0x13a82  ldarg.0
0x13a83  call     instance class Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::get_Images()
0x13a88  callvirt instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList::get_Count()
0x13a8d  bgt.s    loc_13A93
0x13a8f  ldloc.0
0x13a90  ldc.i4.0
0x13a91  bge.s    loc_13A95
0x13a93  ldc.i4.0
0x13a94  stloc.0
0x13a95  leave.s  loc_13A9A
0x13a97  pop
0x13a98  leave.s  loc_13A9A
0x13a9a  ldarg.0
0x13a9b  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::get_Title()
0x13aa0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13aa5  brfalse.s loc_13AF3
0x13aa7  ldarg.1
0x13aa8  ldc.i4.s 0xD
0x13aaa  ldstr    a100// "100%"
0x13aaf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13ab4  ldarg.1
0x13ab5  ldc.i4.s 0x24
0x13ab7  ldstr    aCenter// "center"
0x13abc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13ac1  ldarg.1
0x13ac2  ldc.i4.s 0x11
0x13ac4  ldarg.0
0x13ac5  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13aca  ldstr    aTitle_1// "_Title"
0x13acf  call     string [mscorlib]System.String::Concat(string, string)
0x13ad4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13ad9  ldarg.1
0x13ada  ldc.i4.s 0x19
0x13adc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13ae1  ldarg.1
0x13ae2  ldarg.0
0x13ae3  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::get_Title()
0x13ae8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x13aed  ldarg.1
0x13aee  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13af3  ldarg.1
0x13af4  ldc.i4.s 0xD
0x13af6  ldstr    a100// "100%"
0x13afb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13b00  ldarg.1
0x13b01  ldc.i4.s 0x24
0x13b03  ldstr    aCenter// "center"
0x13b08  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13b0d  ldarg.1
0x13b0e  ldc.i4.s 0x11
0x13b10  ldarg.0
0x13b11  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13b16  ldstr    aImage// "_Image"
0x13b1b  call     string [mscorlib]System.String::Concat(string, string)
0x13b20  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13b25  ldarg.1
0x13b26  ldc.i4.s 0x19
0x13b28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13b2d  ldarg.0
0x13b2e  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13b33  brfalse.s loc_13B58
0x13b35  ldarg.1
0x13b36  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0x13b3b  ldarg.1
0x13b3c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0x13b41  ldarg.1
0x13b42  ldstr    aSlideshowcontr// "SlideShowControl.Msg.DesignTime"
0x13b47  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x13b4c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x13b51  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13b56  br.s     loc_13B87
0x13b58  ldarg.1
0x13b59  ldc.i4.s 0x3D
0x13b5b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13b60  ldarg.1
0x13b61  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0x13b66  ldarg.1
0x13b67  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0x13b6c  ldarg.1
0x13b6d  ldstr    aSlideshowcontr_0// "SlideShowControl.Msg.JavaScript_Require"...
0x13b72  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x13b77  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x13b7c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13b81  ldarg.1
0x13b82  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13b87  ldarg.1
0x13b88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13b8d  ldarg.1
0x13b8e  ldc.i4.s 0xD
0x13b90  ldstr    a100// "100%"
0x13b95  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13b9a  ldarg.1
0x13b9b  ldc.i4.s 0x24
0x13b9d  ldstr    aCenter// "center"
0x13ba2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13ba7  ldarg.1
0x13ba8  ldc.i4.s 0x1B
0x13baa  ldstr    aHidden// "hidden"
0x13baf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13bb4  ldarg.1
0x13bb5  ldc.i4.s 0x11
0x13bb7  ldarg.0
0x13bb8  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13bbd  ldstr    aCap// "_Cap"
0x13bc2  call     string [mscorlib]System.String::Concat(string, string)
0x13bc7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13bcc  ldarg.1
0x13bcd  ldc.i4.s 0x19
0x13bcf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13bd4  ldarg.1
0x13bd5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13bda  ldarg.0
0x13bdb  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowControl::get_ShowControls()
0x13be0  brfalse  loc_140A2
0x13be5  ldarg.1
0x13be6  ldc.i4.s 0xD
0x13be8  ldstr    a100// "100%"
0x13bed  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13bf2  ldarg.1
0x13bf3  ldc.i4.s 0x11
0x13bf5  ldarg.0
0x13bf6  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13bfb  ldstr    aControls// "_Controls"
0x13c00  call     string [mscorlib]System.String::Concat(string, string)
0x13c05  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c0a  ldarg.1
0x13c0b  ldc.i4.s 0x19
0x13c0d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13c12  ldarg.1
0x13c13  ldc.i4.s 0x26
0x13c15  ldstr    a100// "100%"
0x13c1a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c1f  ldarg.1
0x13c20  ldc.i4.s 0x52
0x13c22  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13c27  ldarg.1
0x13c28  ldc.i4.s 0x5A
0x13c2a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13c2f  ldarg.1
0x13c30  ldc.i4.s 0x15
0x13c32  ldnull
0x13c33  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c38  ldarg.1
0x13c39  ldc.i4.s 0x24
0x13c3b  ldstr    aLeft// "left"
0x13c40  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13c45  ldarg.1
0x13c46  ldc.i4.s 0x54
0x13c48  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13c4d  ldarg.1
0x13c4e  ldc.i4.s 0xA
0x13c50  ldstr    aClip22x19Slide// "clip22x19 slideshow_button"
0x13c55  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c5a  ldarg.1
0x13c5b  ldc.i4.s 0x4C
0x13c5d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13c62  ldarg.1
0x13c63  ldc.i4.s 0x22
0x13c65  ldstr    asc_21500// ""
0x13c6a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c6f  ldarg.1
0x13c70  ldc.i4.s 0x10
0x13c72  ldstr    aJavascriptVoid// "javascript:void(0)"
0x13c77  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c7c  ldarg.0
0x13c7d  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13c82  brtrue.s loc_13C9C
0x13c84  ldarg.1
0x13c85  ldc.i4.s 0x17
0x13c87  ldarg.0
0x13c88  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13c8d  ldstr    aPausePlay// ".pause_play();"
0x13c92  call     string [mscorlib]System.String::Concat(string, string)
0x13c97  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13c9c  ldarg.1
0x13c9d  ldc.i4.1
0x13c9e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13ca3  ldarg.1
0x13ca4  ldc.i4.s 0x11
0x13ca6  ldarg.0
0x13ca7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x13cac  ldstr    aPauseplaybutto// "_PausePlayButton"
0x13cb1  call     string [mscorlib]System.String::Concat(string, string)
0x13cb6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13cbb  ldc.i4.2
0x13cbc  ldstr    asc_20240// "/"
0x13cc1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x13cc6  ldstr    aLcidWhImagesSp_0// "/#LCID#/wh/images/spxpubc2.png"
0x13ccb  call     string [mscorlib]System.String::Concat(string, string, string)
0x13cd0  ldc.i4.1
0x13cd1  ldc.i4.0
0x13cd2  call     class [System]System.Uri [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.ResourceUtility::GetResourceUrl(valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.ResourceType, string, bool, bool)
0x13cd7  callvirt instance string [mscorlib]System.Object::ToString()
0x13cdc  stloc.2
0x13cdd  ldarg.1
0x13cde  ldc.i4.s 0x1E
0x13ce0  ldloc.2
0x13ce1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13ce6  ldarg.1
0x13ce7  ldc.i4.s 0xA
0x13ce9  ldstr    aSpxpubc2Button// "spxpubc2_button_pause"
0x13cee  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13cf3  ldarg.1
0x13cf4  ldc.i4.2
0x13cf5  ldstr    aSlideshowcontr_1// "SlideShowControl.ImgBtn.Pause.ToolTip"
0x13cfa  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x13cff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13d04  ldarg.1
0x13d05  ldc.i4.s 0x22
0x13d07  ldstr    aSlideshowcontr_1// "SlideShowControl.ImgBtn.Pause.ToolTip"
0x13d0c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x13d11  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x13d16  ldarg.1
0x13d17  ldc.i4.s 0x2E
0x13d19  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x13d1e  ldarg.1
0x13d1f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13d24  ldarg.1
0x13d25  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13d2a  ldarg.1
0x13d2b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13d30  ldarg.1
  ... truncated ...
```
