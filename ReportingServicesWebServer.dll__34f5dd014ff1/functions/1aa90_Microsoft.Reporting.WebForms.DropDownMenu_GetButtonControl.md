# Microsoft.Reporting.WebForms.DropDownMenu::GetButtonControl

- ea: `0x1aa90`
- end: `0x1ad2f`
- name: `Microsoft.Reporting.WebForms.DropDownMenu::GetButtonControl`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1aa00`

## callees

- `0x1360`
- `0x40b0`
- `0x1aa90`

## string_xrefs

- `0x1aafe`: `ExportLink`

## pseudocode

```c

```

## disassembly

```asm
0x1aa90  newobj   instance void [System.Web]System.Web.UI.WebControls.Table::.ctor()
0x1aa95  stloc.0
0x1aa96  ldloc.0
0x1aa97  ldarg.0
0x1aa98  ldfld    string Microsoft.Reporting.WebForms.DropDownMenu::m_tooltip
0x1aa9d  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0x1aaa2  ldloc.0
0x1aaa3  ldstr    aButton_0// "Button"
0x1aaa8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1aaad  ldloc.0
0x1aaae  ldc.i4.0
0x1aaaf  callvirt instance void [System.Web]System.Web.UI.WebControls.Table::set_CellPadding(int32)
0x1aab4  ldloc.0
0x1aab5  ldc.i4.0
0x1aab6  callvirt instance void [System.Web]System.Web.UI.WebControls.Table::set_CellSpacing(int32)
0x1aabb  newobj   instance void [System.Web]System.Web.UI.WebControls.TableRow::.ctor()
0x1aac0  stloc.1
0x1aac1  newobj   instance void [System.Web]System.Web.UI.WebControls.TableCell::.ctor()
0x1aac6  stloc.2
0x1aac7  ldloc.0
0x1aac8  callvirt instance class [System.Web]System.Web.UI.WebControls.TableRowCollection [System.Web]System.Web.UI.WebControls.Table::get_Rows()
0x1aacd  ldloc.1
0x1aace  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableRowCollection::Add(class [System.Web]System.Web.UI.WebControls.TableRow)
0x1aad3  pop
0x1aad4  ldloc.1
0x1aad5  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0x1aada  ldloc.2
0x1aadb  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableCellCollection::Add(class [System.Web]System.Web.UI.WebControls.TableCell)
0x1aae0  pop
0x1aae1  newobj   instance void [System.Web]System.Web.UI.WebControls.HyperLink::.ctor()
0x1aae6  stloc.3
0x1aae7  ldloc.3
0x1aae8  ldloc.0
0x1aae9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1aaee  ldstr    aLink// "Link"
0x1aaf3  call     string [mscorlib]System.String::Concat(string, string)
0x1aaf8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1aafd  ldloc.3
0x1aafe  ldstr    aExportlink// "ExportLink"
0x1ab03  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x1ab08  ldloc.3
0x1ab09  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x1ab0e  ldstr    aTitle// "title"
0x1ab13  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1ab18  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ExportButtonToolTip()
0x1ab1d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ab22  ldloc.3
0x1ab23  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x1ab28  ldstr    aAlt// "alt"
0x1ab2d  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1ab32  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ExportButtonToolTip()
0x1ab37  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ab3c  ldloc.3
0x1ab3d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x1ab42  ldstr    aAriaLabel// "aria-label"
0x1ab47  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1ab4c  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ExportButtonToolTip()
0x1ab51  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ab56  ldloc.3
0x1ab57  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x1ab5c  ldstr    aRole// "role"
0x1ab61  ldstr    aButton// "button"
0x1ab66  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ab6b  ldloc.3
0x1ab6c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x1ab71  ldstr    aTabindex// "tabindex"
0x1ab76  ldstr    a1_0// "1"
0x1ab7b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ab80  ldloc.3
0x1ab81  ldstr    aJavascriptVoid_0// "javascript:void(0)"
0x1ab86  callvirt instance void [System.Web]System.Web.UI.WebControls.HyperLink::set_NavigateUrl(string)
0x1ab8b  ldloc.2
0x1ab8c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1ab91  ldloc.3
0x1ab92  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1ab97  ldarg.1
0x1ab98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ab9d  brfalse  loc_1AC2B
0x1aba2  newobj   instance void [System.Web]System.Web.UI.WebControls.Image::.ctor()
0x1aba7  stloc.s  4
0x1aba9  ldloc.s  4
0x1abab  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1abb0  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ExportButtonToolTip()
0x1abb5  callvirt instance void [System.Web]System.Web.UI.WebControls.Image::set_AlternateText(string)
0x1abba  ldloc.s  4
0x1abbc  ldarg.0
0x1abbd  ldfld    bool Microsoft.Reporting.WebForms.DropDownMenu::ShowEnabled
0x1abc2  brtrue.s loc_1ABD1
0x1abc4  ldarg.0
0x1abc5  ldfld    class Microsoft.Reporting.WebForms.ButtonImageInfo Microsoft.Reporting.WebForms.DropDownMenu::m_buttonImageInfo
0x1abca  ldfld    string Microsoft.Reporting.WebForms.ButtonImageInfo::DisabledUrl
0x1abcf  br.s     loc_1ABDC
0x1abd1  ldarg.0
0x1abd2  ldfld    class Microsoft.Reporting.WebForms.ButtonImageInfo Microsoft.Reporting.WebForms.DropDownMenu::m_buttonImageInfo
0x1abd7  ldfld    string Microsoft.Reporting.WebForms.ButtonImageInfo::EnabledUrl
0x1abdc  callvirt instance void [System.Web]System.Web.UI.WebControls.Image::set_ImageUrl(string)
0x1abe1  ldloc.s  4
0x1abe3  ldloc.0
0x1abe4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1abe9  ldstr    aImg// "Img"
0x1abee  call     string [mscorlib]System.String::Concat(string, string)
0x1abf3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1abf8  ldloc.s  4
0x1abfa  ldc.i4.s 0x20
0x1abfc  call     valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::op_Implicit(int32)
0x1ac01  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Width(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x1ac06  ldloc.s  4
0x1ac08  ldc.i4.s 0x20
0x1ac0a  call     valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::op_Implicit(int32)
0x1ac0f  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Height(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x1ac14  ldloc.s  4
0x1ac16  ldc.i4.1
0x1ac17  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_BorderStyle(valuetype [System.Web]System.Web.UI.WebControls.BorderStyle)
0x1ac1c  ldloc.3
0x1ac1d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1ac22  ldloc.s  4
0x1ac24  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1ac29  br.s     loc_1AC60
0x1ac2b  ldc.i4.s 0x4C
0x1ac2d  newobj   instance void [System.Web]System.Web.UI.WebControls.WebControl::.ctor(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1ac32  stloc.s  5
0x1ac34  ldloc.s  5
0x1ac36  ldarg.1
0x1ac37  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x1ac3c  ldloc.s  5
0x1ac3e  ldloc.0
0x1ac3f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1ac44  ldstr    aImg// "Img"
0x1ac49  call     string [mscorlib]System.String::Concat(string, string)
0x1ac4e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1ac53  ldloc.3
0x1ac54  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1ac59  ldloc.s  5
0x1ac5b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1ac60  ldarg.1
0x1ac61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ac66  brfalse  loc_1ACF4
0x1ac6b  newobj   instance void [System.Web]System.Web.UI.WebControls.Image::.ctor()
0x1ac70  stloc.s  6
0x1ac72  ldloc.s  6
0x1ac74  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1ac79  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ExportButtonToolTip()
0x1ac7e  callvirt instance void [System.Web]System.Web.UI.WebControls.Image::set_AlternateText(string)
0x1ac83  ldloc.s  6
0x1ac85  ldloc.0
0x1ac86  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1ac8b  ldstr    aImgdown// "ImgDown"
0x1ac90  call     string [mscorlib]System.String::Concat(string, string)
0x1ac95  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1ac9a  ldloc.s  6
0x1ac9c  ldarg.0
0x1ac9d  ldfld    bool Microsoft.Reporting.WebForms.DropDownMenu::ShowEnabled
0x1aca2  brtrue.s loc_1ACB1
0x1aca4  ldarg.0
0x1aca5  ldfld    class Microsoft.Reporting.WebForms.ButtonImageInfo Microsoft.Reporting.WebForms.DropDownMenu::m_arrowImageInfo
0x1acaa  ldfld    string Microsoft.Reporting.WebForms.ButtonImageInfo::DisabledUrl
0x1acaf  br.s     loc_1ACBC
0x1acb1  ldarg.0
0x1acb2  ldfld    class Microsoft.Reporting.WebForms.ButtonImageInfo Microsoft.Reporting.WebForms.DropDownMenu::m_arrowImageInfo
0x1acb7  ldfld    string Microsoft.Reporting.WebForms.ButtonImageInfo::EnabledUrl
0x1acbc  callvirt instance void [System.Web]System.Web.UI.WebControls.Image::set_ImageUrl(string)
0x1acc1  ldloc.s  6
0x1acc3  ldc.i4.s 0xC
0x1acc5  call     valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::op_Implicit(int32)
0x1acca  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Width(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x1accf  ldloc.s  6
0x1acd1  ldc.i4.s 0x20
0x1acd3  call     valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::op_Implicit(int32)
0x1acd8  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Height(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x1acdd  ldloc.s  6
0x1acdf  ldc.i4.1
0x1ace0  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_BorderStyle(valuetype [System.Web]System.Web.UI.WebControls.BorderStyle)
0x1ace5  ldloc.3
0x1ace6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1aceb  ldloc.s  6
0x1aced  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1acf2  br.s     loc_1AD2D
0x1acf4  ldc.i4.s 0x4C
0x1acf6  newobj   instance void [System.Web]System.Web.UI.WebControls.WebControl::.ctor(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1acfb  stloc.s  7
0x1acfd  ldloc.s  7
0x1acff  ldstr    aGlyphuiGlyphui_11// "glyphui glyphui-downarrow"
0x1ad04  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x1ad09  ldloc.s  7
0x1ad0b  ldloc.0
0x1ad0c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1ad11  ldstr    aImgdown// "ImgDown"
0x1ad16  call     string [mscorlib]System.String::Concat(string, string)
0x1ad1b  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1ad20  ldloc.3
0x1ad21  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1ad26  ldloc.s  7
0x1ad28  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1ad2d  ldloc.0
0x1ad2e  ret
```
