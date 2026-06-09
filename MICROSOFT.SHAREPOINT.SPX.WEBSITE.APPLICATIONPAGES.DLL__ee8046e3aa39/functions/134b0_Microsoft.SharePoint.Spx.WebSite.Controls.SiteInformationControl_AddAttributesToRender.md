# Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::AddAttributesToRender

- ea: `0x134b0`
- end: `0x13552`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::AddAttributesToRender`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7bd0`
- `0x134b0`

## string_xrefs

- `0x134b3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x134b0  ldarg.1
0x134b1  brtrue.s loc_134BE
0x134b3  ldstr    aWriter// "writer"
0x134b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x134bd  throw
0x134be  ldarg.0
0x134bf  ldarg.1
0x134c0  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::AddAttributesToRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x134c5  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x134ca  stloc.0
0x134cb  ldloca.s 0
0x134cd  ldarg.0
0x134ce  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x134d3  box      [System.Web]System.Web.UI.WebControls.Unit
0x134d8  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x134de  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x134e3  brtrue.s loc_13551
0x134e5  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x134ea  stloc.1
0x134eb  ldloca.s 1
0x134ed  ldarg.0
0x134ee  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x134f3  box      [System.Web]System.Web.UI.WebControls.Unit
0x134f8  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x134fe  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13503  brtrue.s loc_13551
0x13505  ldarg.0
0x13506  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x1350b  brtrue.s loc_13544
0x1350d  ldarg.0
0x1350e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13513  brfalse.s loc_13544
0x13515  ldarg.0
0x13516  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1351b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13520  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x13525  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x1352a  ldstr    aFirefox// "Firefox"
0x1352f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x13534  brfalse.s loc_13544
0x13536  ldarg.1
0x13537  ldc.i4.s 0x12
0x13539  ldstr    aMozInlineBox// "-moz-inline-box"
0x1353e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13543  ret
0x13544  ldarg.1
0x13545  ldc.i4.s 0x12
0x13547  ldstr    aInlineBlock// "inline-block"
0x1354c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x13551  ret
```
