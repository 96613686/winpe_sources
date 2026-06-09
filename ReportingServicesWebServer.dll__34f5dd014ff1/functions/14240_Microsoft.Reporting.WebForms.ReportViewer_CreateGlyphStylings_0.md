# Microsoft.Reporting.WebForms.ReportViewer::CreateGlyphStylings_0

- ea: `0x14240`
- end: `0x14495`
- name: `Microsoft.Reporting.WebForms.ReportViewer::CreateGlyphStylings_0`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x14230`

## callees

- `0x8f10`
- `0x12480`
- `0x12570`
- `0x125d0`
- `0x12630`
- `0x12690`
- `0x126f0`
- `0x12750`
- `0x127b0`
- `0x12810`
- `0x144a0`
- `0x144e0`
- `0x14560`

## string_xrefs

- `0x1424c`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.eot`
- `0x14257`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.woff`
- `0x14262`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.ttf`
- `0x1426d`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphssvg`

## pseudocode

```c

```

## disassembly

```asm
0x14240  ldstr    asc_47016// "#"
0x14245  ldarg.1
0x14246  call     string [mscorlib]System.String::Concat(string, string)
0x1424b  stloc.0
0x1424c  ldstr    aMicrosoftRepor_47// "Microsoft.Reporting.WebForms.Fonts.Repo"...
0x14251  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x14256  stloc.1
0x14257  ldstr    aMicrosoftRepor_48// "Microsoft.Reporting.WebForms.Fonts.Repo"...
0x1425c  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x14261  stloc.2
0x14262  ldstr    aMicrosoftRepor_49// "Microsoft.Reporting.WebForms.Fonts.Repo"...
0x14267  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x1426c  stloc.3
0x1426d  ldstr    aMicrosoftRepor_50// "Microsoft.Reporting.WebForms.Fonts.Repo"...
0x14272  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x14277  stloc.s  4
0x14279  ldarg.0
0x1427a  callvirt instance class [System.Web]System.Web.UI.WebControls.FontInfo [System.Web]System.Web.UI.WebControls.WebControl::get_Font()
0x1427f  ldstr    aSegoeUiHelveti// "\"Segoe UI\",\"Helvetica Neue\", Helvet"...
0x14284  call     string Microsoft.Reporting.WebForms.ReportViewer::GetFontValueOrDefault(class [System.Web]System.Web.UI.WebControls.FontInfo value, string defaultValue)
0x14289  stloc.s  5
0x1428b  ldarg.0
0x1428c  ldarg.0
0x1428d  callvirt instance class [System.Web]System.Web.UI.WebControls.FontInfo [System.Web]System.Web.UI.WebControls.WebControl::get_Font()
0x14292  ldstr    a10pt// "10pt"
0x14297  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetFontSizeOrDefault(class [System.Web]System.Web.UI.WebControls.FontInfo value, string defaultValue)
0x1429c  stloc.s  6
0x1429e  ldarg.0
0x1429f  ldarg.0
0x142a0  callvirt instance valuetype [System.Drawing]System.Drawing.Color [System.Web]System.Web.UI.WebControls.WebControl::get_BackColor()
0x142a5  ldstr    aFfffff// "#FFFFFF"
0x142aa  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x142af  stloc.s  7
0x142b1  ldarg.0
0x142b2  ldarg.0
0x142b3  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_HighlightBackgroundColor()
0x142b8  ldstr    aFfc20d// "#FFC20D"
0x142bd  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x142c2  stloc.s  8
0x142c4  ldarg.0
0x142c5  ldarg.0
0x142c6  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_PrimaryButtonBackgroundColor()
0x142cb  ldstr    aBb2124// "#BB2124"
0x142d0  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x142d5  stloc.s  9
0x142d7  ldarg.0
0x142d8  ldarg.0
0x142d9  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_PrimaryButtonForegroundColor()
0x142de  ldstr    aFfffff// "#FFFFFF"
0x142e3  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x142e8  stloc.s  0xA
0x142ea  ldarg.0
0x142eb  ldarg.0
0x142ec  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_PrimaryButtonHoverBackgroundColor()
0x142f1  ldstr    aD31115// "#D31115"
0x142f6  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x142fb  stloc.s  0xB
0x142fd  ldarg.0
0x142fe  ldarg.0
0x142ff  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_PrimaryButtonHoverForegroundColor()
0x14304  ldstr    aFfffff// "#FFFFFF"
0x14309  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x1430e  stloc.s  0xC
0x14310  ldarg.0
0x14311  ldarg.0
0x14312  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_SecondaryButtonBackgroundColor()
0x14317  ldstr    aC8c8c8// "#C8C8C8"
0x1431c  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x14321  stloc.s  0xD
0x14323  ldarg.0
0x14324  ldarg.0
0x14325  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_SecondaryButtonForegroundColor()
0x1432a  ldstr    a000000// "#000000"
0x1432f  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x14334  stloc.s  0xE
0x14336  ldarg.0
0x14337  ldarg.0
0x14338  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_SecondaryButtonHoverBackgroundColor()
0x1433d  ldstr    aE6e6e6// "#E6E6E6"
0x14342  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x14347  stloc.s  0xF
0x14349  ldarg.0
0x1434a  ldarg.0
0x1434b  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.ReportViewer::get_SecondaryButtonHoverForegroundColor()
0x14350  ldstr    a000000// "#000000"
0x14355  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetColorOrDefault(valuetype [System.Drawing]System.Drawing.Color color, string defaultColor)
0x1435a  stloc.s  0x10
0x1435c  ldc.i4.s 9
0x1435e  call     string [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.TemplateHelper::GetTemplate(valuetype [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.Template)
0x14363  ldstr    aReportviewerco_0// "@ReportViewerControlSelector"
0x14368  ldloc.0
0x14369  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1436e  ldstr    aEotfontsrc// "@EotFontSrc"
0x14373  ldloc.1
0x14374  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14379  ldstr    aWofffontsrc// "@WoffFontSrc"
0x1437e  ldloc.2
0x1437f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14384  ldstr    aTtffontsrc// "@TtfFontSrc"
0x14389  ldloc.3
0x1438a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1438f  ldstr    aSvgfontsrc// "@SvgFontSrc"
0x14394  ldloc.s  4
0x14396  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1439b  ldstr    aFontfamily// "@FontFamily"
0x143a0  ldloc.s  5
0x143a2  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143a7  ldstr    aFontsize// "@FontSize"
0x143ac  ldloc.s  6
0x143ae  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143b3  ldstr    aForegroundcolo// "@ForegroundColor"
0x143b8  ldstr    a000000// "#000000"
0x143bd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143c2  ldstr    aBackgroundcolo// "@BackgroundColor"
0x143c7  ldloc.s  7
0x143c9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143ce  ldstr    aDisabledforegr// "@DisabledForegroundColor"
0x143d3  ldstr    a7a7a7a// "#7A7A7A"
0x143d8  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143dd  ldstr    aHoverbackgroun// "@HoverBackgroundColor"
0x143e2  ldstr    aE6e6e6// "#E6E6E6"
0x143e7  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143ec  ldstr    aHoverforegroun// "@HoverForegroundColor"
0x143f1  ldstr    a000000// "#000000"
0x143f6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x143fb  ldstr    aHighlightbackg_0// "@HighlightBackgroundColor"
0x14400  ldloc.s  8
0x14402  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14407  ldstr    aBordercolor// "@BorderColor"
0x1440c  ldstr    aDddddd// "#DDDDDD"
0x14411  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14416  ldstr    aPrimarybuttonb_0// "@PrimaryButtonBackgroundColor"
0x1441b  ldloc.s  9
0x1441d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14422  ldstr    aPrimarybuttonf_0// "@PrimaryButtonForegroundColor"
0x14427  ldloc.s  0xA
0x14429  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1442e  ldstr    aPrimarybuttonh_1// "@PrimaryButtonHoverBackgroundColor"
0x14433  ldloc.s  0xB
0x14435  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1443a  ldstr    aPrimarybuttonh_2// "@PrimaryButtonHoverForegroundColor"
0x1443f  ldloc.s  0xC
0x14441  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14446  ldstr    aSecondarybutto_3// "@SecondaryButtonBackgroundColor"
0x1444b  ldloc.s  0xD
0x1444d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14452  ldstr    aSecondarybutto_4// "@SecondaryButtonForegroundColor"
0x14457  ldloc.s  0xE
0x14459  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1445e  ldstr    aSecondarybutto_5// "@SecondaryButtonHoverBackgroundColor"
0x14463  ldloc.s  0xF
0x14465  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1446a  ldstr    aSecondarybutto_6// "@SecondaryButtonHoverForegroundColor"
0x1446f  ldloc.s  0x10
0x14471  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x14476  stloc.s  0x11
0x14478  ldarg.0
0x14479  ldstr    aStyle// "<style>"
0x1447e  ldloc.s  0x11
0x14480  ldstr    aStyle_0// "</style>"
0x14485  call     string [mscorlib]System.String::Concat(string, string, string)
0x1448a  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x1448f  stfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.Reporting.WebForms.ReportViewer::m_styling
0x14494  ret
```
