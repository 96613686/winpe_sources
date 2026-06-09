# Microsoft.Reporting.WebForms.ReportViewer::RenderTopLevelUpdatePanelContents

- ea: `0x14710`
- end: `0x14cb0`
- name: `Microsoft.Reporting.WebForms.ReportViewer::RenderTopLevelUpdatePanelContents`
- size: `1440`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14630`

## callees

- `0x6de0`
- `0xa360`
- `0x120a0`
- `0x12180`
- `0x12220`
- `0x12540`
- `0x12c70`
- `0x14710`
- `0x15790`
- `0x15950`
- `0x15b90`
- `0x15bb0`
- `0x17a10`
- `0x1b340`

## pseudocode

```c

```

## disassembly

```asm
0x14710  ldarg.0
0x14711  call     instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x14716  castclass Microsoft.Reporting.WebForms.ReportViewerStyle
0x1471b  ldarg.0
0x1471c  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_SizeToReportContent()
0x14721  ldc.i4.0
0x14722  ceq
0x14724  stfld    bool Microsoft.Reporting.WebForms.ReportViewerStyle::ObeySizeProperties
0x14729  ldarg.1
0x1472a  ldc.i4.s 0xA
0x1472c  ldstr    aMsrsRvc// "MSRS-RVC"
0x14731  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14736  ldarg.0
0x14737  ldarg.1
0x14738  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::AddAttributesToRender(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1473d  ldarg.0
0x1473e  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x14743  ldarg.1
0x14744  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::RenderCloseDropDownAttributes(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x14749  ldarg.1
0x1474a  ldc.i4.s 0x19
0x1474c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14751  ldarg.0
0x14752  ldfld    class Microsoft.Reporting.WebForms.HttpHandlerMissingErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_httpHandlerMissingError
0x14757  ldarg.1
0x14758  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1475d  ldarg.0
0x1475e  ldfld    class Microsoft.Reporting.WebForms.NotSupportedBrowserErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_browserNotSupportedErrorMessage
0x14763  ldarg.1
0x14764  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x14769  ldarg.0
0x1476a  ldfld    class Microsoft.Reporting.WebForms.ReportViewerClientScript Microsoft.Reporting.WebForms.ReportViewer::m_clientScript
0x1476f  ldarg.1
0x14770  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x14775  ldarg.0
0x14776  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportViewer::m_direction
0x1477b  ldarg.1
0x1477c  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x14781  ldarg.0
0x14782  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportViewer::m_browserMode
0x14787  ldarg.1
0x14788  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1478d  ldarg.0
0x1478e  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x14793  brtrue.s loc_147A1
0x14795  ldarg.0
0x14796  ldfld    class Microsoft.Reporting.WebForms.AsyncWaitControl Microsoft.Reporting.WebForms.ReportViewer::m_asyncWaitControl
0x1479b  ldarg.1
0x1479c  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x147a1  ldarg.1
0x147a2  ldc.i4.7
0x147a3  ldstr    a0// "0"
0x147a8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x147ad  ldarg.1
0x147ae  ldc.i4.8
0x147af  ldstr    a0// "0"
0x147b4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x147b9  ldarg.1
0x147ba  ldc.i4.s 0x11
0x147bc  ldarg.0
0x147bd  call     instance string Microsoft.Reporting.WebForms.ReportViewer::get_FixedTableID()
0x147c2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x147c7  ldarg.0
0x147c8  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_SizeToReportContent()
0x147cd  brtrue.s loc_14821
0x147cf  ldarg.1
0x147d0  ldstr    aTableLayout// "table-layout"
0x147d5  ldstr    aFixed// "fixed"
0x147da  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(string, string)
0x147df  ldarg.0
0x147e0  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x147e5  stloc.3
0x147e6  ldloca.s 3
0x147e8  call     instance bool [System.Web]System.Web.UI.WebControls.Unit::get_IsEmpty()
0x147ed  brtrue.s loc_147FC
0x147ef  ldarg.1
0x147f0  ldc.i4.s 0xD
0x147f2  ldstr    a100// "100%"
0x147f7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x147fc  ldarg.0
0x147fd  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x14802  stloc.3
0x14803  ldloca.s 3
0x14805  call     instance bool [System.Web]System.Web.UI.WebControls.Unit::get_IsEmpty()
0x1480a  brtrue.s loc_14821
0x1480c  ldarg.0
0x1480d  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x14812  brtrue.s loc_14821
0x14814  ldarg.1
0x14815  ldc.i4.s 0xB
0x14817  ldstr    a100// "100%"
0x1481c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14821  ldarg.1
0x14822  ldc.i4.s 0x52
0x14824  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14829  ldarg.0
0x1482a  call     instance valuetype Microsoft.Reporting.WebForms.ReportAreaContent Microsoft.Reporting.WebForms.ReportViewer::get_ReportAreaContentType()
0x1482f  ldc.i4.1
0x14830  bne.un.s loc_1484A
0x14832  ldarg.0
0x14833  ldfld    class Microsoft.Reporting.WebForms.DocMapArea Microsoft.Reporting.WebForms.ReportViewer::m_docMapArea
0x14838  callvirt instance class Microsoft.Reporting.WebForms.DocumentMapNode Microsoft.Reporting.WebForms.DocMapArea::get_RootNode()
0x1483d  brfalse.s loc_1484A
0x1483f  ldarg.0
0x14840  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_DocumentMapCollapsed()
0x14845  ldc.i4.0
0x14846  ceq
0x14848  br.s     loc_1484B
0x1484a  ldc.i4.0
0x1484b  stloc.0
0x1484c  ldarg.0
0x1484d  ldfld    class Microsoft.Reporting.WebForms.ToolbarControl Microsoft.Reporting.WebForms.ReportViewer::m_toolbarArea
0x14852  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x14857  stloc.1
0x14858  ldarg.0
0x14859  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_PromptAreaCollapsed()
0x1485e  brtrue.s loc_1486D
0x14860  ldarg.0
0x14861  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x14866  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x1486b  br.s     loc_1486E
0x1486d  ldc.i4.0
0x1486e  stloc.2
0x1486f  ldarg.0
0x14870  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_SizeToReportContent()
0x14875  brtrue   loc_14957
0x1487a  ldloc.1
0x1487b  ldloc.2
0x1487c  or
0x1487d  brfalse.s loc_148CD
0x1487f  ldarg.0
0x14880  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x14885  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_ViewerAreaBackground()
0x1488a  brfalse.s loc_1489F
0x1488c  ldarg.1
0x1488d  ldc.i4.s 0xA
0x1488f  ldarg.0
0x14890  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x14895  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_ViewerAreaBackground()
0x1489a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x1489f  ldarg.0
0x148a0  call     instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x148a5  callvirt instance valuetype [System.Drawing]System.Drawing.Color [System.Web]System.Web.UI.WebControls.Style::get_BackColor()
0x148aa  ldsfld   valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::Empty
0x148af  call     bool [System.Drawing]System.Drawing.Color::op_Inequality(valuetype [System.Drawing]System.Drawing.Color, valuetype [System.Drawing]System.Drawing.Color)
0x148b4  brfalse.s loc_148CD
0x148b6  ldarg.1
0x148b7  ldc.i4.0
0x148b8  ldarg.0
0x148b9  call     instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x148be  callvirt instance valuetype [System.Drawing]System.Drawing.Color [System.Web]System.Web.UI.WebControls.Style::get_BackColor()
0x148c3  call     string [System.Drawing]System.Drawing.ColorTranslator::ToHtml(valuetype [System.Drawing]System.Drawing.Color)
0x148c8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x148cd  ldarg.1
0x148ce  ldc.i4.s 0x5A
0x148d0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x148d5  ldloc.0
0x148d6  brtrue.s loc_148E5
0x148d8  ldarg.1
0x148d9  ldc.i4.s 0x12
0x148db  ldstr    aNone// "none"
0x148e0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x148e5  ldarg.1
0x148e6  ldc.i4.s 0xD
0x148e8  ldarg.0
0x148e9  call     instance valuetype [System.Web]System.Web.UI.WebControls.Unit Microsoft.Reporting.WebForms.ReportViewer::get_DocumentMapWidth()
0x148ee  stloc.3
0x148ef  ldloca.s 3
0x148f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x148f6  call     instance string [System.Web]System.Web.UI.WebControls.Unit::ToString(class [mscorlib]System.Globalization.CultureInfo)
0x148fb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14900  ldarg.1
0x14901  ldc.i4.s 0x54
0x14903  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14908  ldarg.1
0x14909  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x1490e  ldarg.1
0x1490f  ldc.i4.s 0x12
0x14911  ldstr    aNone// "none"
0x14916  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x1491b  ldarg.1
0x1491c  ldc.i4.s 0xD
0x1491e  ldstr    a6px// "6px"
0x14923  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14928  ldarg.1
0x14929  ldc.i4.s 0x54
0x1492b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14930  ldarg.1
0x14931  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14936  ldarg.1
0x14937  ldc.i4.s 0xD
0x14939  ldstr    a100// "100%"
0x1493e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14943  ldarg.1
0x14944  ldc.i4.s 0x54
0x14946  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1494b  ldarg.1
0x1494c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14951  ldarg.1
0x14952  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14957  ldarg.0
0x14958  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x1495d  brtrue   loc_14A84
0x14962  ldloc.2
0x14963  brtrue.s loc_14972
0x14965  ldarg.1
0x14966  ldc.i4.s 0x12
0x14968  ldstr    aNone// "none"
0x1496d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14972  ldarg.1
0x14973  ldc.i4.s 0x11
0x14975  ldarg.0
0x14976  call     instance string Microsoft.Reporting.WebForms.ReportViewer::get_ParametersRowID()
0x1497b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14980  ldarg.1
0x14981  ldc.i4.s 0x5A
0x14983  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14988  ldarg.1
0x14989  ldc.i4.s 0xC
0x1498b  ldstr    a3// "3"
0x14990  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14995  ldarg.1
0x14996  ldc.i4.s 0x54
0x14998  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1499d  ldarg.0
0x1499e  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_SizeToReportContent()
0x149a3  brtrue.s loc_149E3
0x149a5  ldarg.0
0x149a6  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x149ab  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x149b0  ldc.i4.s 0xD
0x149b2  ldstr    a100// "100%"
0x149b7  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x149bc  ldarg.0
0x149bd  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x149c2  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x149c7  ldc.i4.s 0x1B
0x149c9  ldstr    aAuto// "auto"
0x149ce  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x149d3  ldarg.1
0x149d4  ldstr    aMaxHeight// "max-height"
0x149d9  ldstr    a40vh// "40vh"
0x149de  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(string, string)
0x149e3  ldarg.0
0x149e4  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x149e9  ldarg.1
0x149ea  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x149ef  ldarg.1
0x149f0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x149f5  ldarg.1
0x149f6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x149fb  ldarg.1
0x149fc  ldc.i4.s 0xB
0x149fe  ldstr    a6px// "6px"
0x14a03  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14a08  ldarg.1
0x14a09  ldc.i4.8
0x14a0a  ldstr    a2pt// "2pt"
0x14a0f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14a14  ldarg.0
0x14a15  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_ShouldRenderPromptAreaSplitter()
0x14a1a  brtrue.s loc_14A29
0x14a1c  ldarg.1
0x14a1d  ldc.i4.s 0x12
0x14a1f  ldstr    aNone// "none"
0x14a24  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14a29  ldarg.1
0x14a2a  ldc.i4.s 0x5A
0x14a2c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14a31  ldarg.1
0x14a32  ldc.i4.s 0xC
0x14a34  ldstr    a3// "3"
0x14a39  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x14a3e  ldarg.1
0x14a3f  ldc.i4.s 0x1E
0x14a41  ldstr    a0px// "0px"
0x14a46  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14a4b  ldarg.1
0x14a4c  ldc.i4.s 0x16
0x14a4e  ldstr    a0px// "0px"
0x14a53  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x14a58  ldarg.0
0x14a59  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x14a5e  ldarg.1
0x14a5f  callvirt instance void Microsoft.Reporting.WebForms.ReportSplitter::WriteTableCellCenteringStyles(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x14a64  ldarg.1
0x14a65  ldc.i4.s 0x54
0x14a67  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x14a6c  ldarg.0
0x14a6d  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x14a72  ldarg.1
0x14a73  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x14a78  ldarg.1
0x14a79  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14a7e  ldarg.1
0x14a7f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x14a84  ldloc.1
0x14a85  brtrue.s loc_14A94
0x14a87  ldarg.1
0x14a88  ldc.i4.s 0x12
  ... truncated ...
```
