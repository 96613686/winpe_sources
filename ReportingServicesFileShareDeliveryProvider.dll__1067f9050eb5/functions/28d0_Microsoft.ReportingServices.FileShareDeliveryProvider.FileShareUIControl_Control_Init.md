# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Control_Init

- ea: `0x28d0`
- end: `0x3353`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Control_Init`
- size: `2691`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1950`
- `0x1f30`
- `0x1f60`
- `0x2000`
- `0x2070`
- `0x20a0`
- `0x20e0`
- `0x2140`
- `0x2170`
- `0x21b0`
- `0x21d0`
- `0x2730`
- `0x2870`
- `0x28d0`
- `0x3360`
- `0x3390`
- `0x3a70`
- `0x3a80`
- `0x3a90`
- `0x3aa0`
- `0x3ad0`
- `0x3ae0`
- `0x3af0`
- `0x3b00`
- `0x3b10`
- `0x3b20`
- `0x3b60`
- `0x3c50`
- `0x3c60`
- `0x3ca0`
- `0x3cb0`
- `0x3cc0`
- `0x3cd0`
- `0x3ce0`
- `0x3cf0`
- `0x3fc0`
- `0x3ff0`
- `0x4060`
- `0x40d0`

## string_xrefs

- `0x32cb`: `Overwrite`
- `0x3325`: `Overwrite`
- `0x29e1`: `ItemPath`
- `0x2db8`: `combobox`

## pseudocode

```c

```

## disassembly

```asm
0x28d0  ldarg.0
0x28d1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x28d6  ldarg.0
0x28d7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_pageLevelScript
0x28dc  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x28e1  ldarg.0
0x28e2  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PushNewTable()
0x28e7  pop
0x28e8  ldarg.0
0x28e9  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x28ee  ldarg.0
0x28ef  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentTable()
0x28f4  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x28f9  ldarg.0
0x28fa  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_pageLevelScript
0x28ff  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2904  ldstr    aLanguage// "language"
0x2909  ldstr    aJavascript// "Javascript"
0x290e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2913  ldarg.0
0x2914  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_pageLevelScript
0x2919  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x291e  ldstr    aType// "type"
0x2923  ldstr    aTextJavascript// "text/Javascript"
0x2928  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x292d  ldarg.0
0x292e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2933  ldarg.0
0x2934  ldfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_validatorScript
0x2939  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x293e  ldarg.0
0x293f  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::SetValidatorScript()
0x2944  ldarg.0
0x2945  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow()
0x294a  pop
0x294b  ldarg.0
0x294c  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2951  pop
0x2952  ldarg.0
0x2953  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileName()
0x2958  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddLabel(string unencodedText)
0x295d  ldarg.0
0x295e  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2963  pop
0x2964  ldarg.0
0x2965  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x296a  ldc.i4.3
0x296b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_ColSpan(int32)
0x2970  ldarg.0
0x2971  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2976  ldc.i4.s 0x4B
0x2978  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Columns(int32)
0x297d  ldarg.0
0x297e  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2983  ldc.i4.0
0x2984  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_TextMode(valuetype [System.Web]System.Web.UI.WebControls.TextBoxMode)
0x2989  ldarg.0
0x298a  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x298f  ldarg.0
0x2990  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileNameID
0x2995  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x299a  ldarg.0
0x299b  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x29a0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x29a5  ldstr    aAriaLabel// "aria-label"
0x29aa  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileName()
0x29af  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x29b4  ldarg.0
0x29b5  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x29ba  call     void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddTextBoxStyles(class [System.Web]System.Web.UI.WebControls.TextBox txt)
0x29bf  ldarg.0
0x29c0  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x29c5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x29ca  ldarg.0
0x29cb  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x29d0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x29d5  ldarg.0
0x29d6  ldarg.0
0x29d7  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x29dc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x29e1  ldstr    aItempath// "ItemPath"
0x29e6  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x29eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29f0  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x29f5  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x29fa  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x29ff  ldarg.0
0x2a00  ldarg.0
0x2a01  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a06  ldarg.0
0x2a07  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a0c  ldstr    asc_55EA// "/"
0x2a11  ldc.i4.4
0x2a12  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2a17  ldc.i4.1
0x2a18  add
0x2a19  ldarg.0
0x2a1a  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a1f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2a24  ldarg.0
0x2a25  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a2a  ldstr    asc_55EA// "/"
0x2a2f  ldc.i4.4
0x2a30  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2a35  sub
0x2a36  ldc.i4.1
0x2a37  sub
0x2a38  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2a3d  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a42  ldarg.0
0x2a43  ldarg.0
0x2a44  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a4e  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x2a53  callvirt instance string [mscorlib]System.String::Trim()
0x2a58  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::ReplaceFileName(string inputFileName)
0x2a5d  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a62  ldarg.0
0x2a63  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2a68  ldarg.0
0x2a69  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x2a6e  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x2a73  ldarg.0
0x2a74  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2a79  pop
0x2a7a  ldarg.0
0x2a7b  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2a80  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a85  ldarg.0
0x2a86  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_invalidFileName
0x2a8b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a90  ldarg.0
0x2a91  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2a96  ldstr    a100// "100%"
0x2a9b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Width(string)
0x2aa0  ldarg.0
0x2aa1  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileNameRequired
0x2aa6  ldc.i4.2
0x2aa7  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_Display(valuetype [System.Web]System.Web.UI.WebControls.ValidatorDisplay)
0x2aac  ldarg.0
0x2aad  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileNameRequired
0x2ab2  ldarg.0
0x2ab3  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileNameID
0x2ab8  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string)
0x2abd  ldarg.0
0x2abe  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileNameRequired
0x2ac3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2ac8  ldarg.0
0x2ac9  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileName()
0x2ace  ldc.i4.1
0x2acf  call     instance class [System.Web]System.Web.UI.Control Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage(string error, bool noWrap)
0x2ad4  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2ad9  ldarg.0
0x2ada  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_invalidFileName
0x2adf  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2ae4  ldarg.0
0x2ae5  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileNameRequired
0x2aea  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2aef  newobj   instance void FileNameValidator::.ctor()
0x2af4  stloc.0
0x2af5  ldloc.0
0x2af6  ldarg.0
0x2af7  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileNameID
0x2afc  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string)
0x2b01  ldloc.0
0x2b02  ldc.i4.2
0x2b03  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_Display(valuetype [System.Web]System.Web.UI.WebControls.ValidatorDisplay)
0x2b08  ldloc.0
0x2b09  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2b0e  ldarg.0
0x2b0f  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileName()
0x2b14  ldc.i4.1
0x2b15  call     instance class [System.Web]System.Web.UI.Control Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage(string error, bool noWrap)
0x2b1a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2b1f  ldarg.0
0x2b20  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2b25  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2b2a  ldloc.0
0x2b2b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2b30  ldarg.0
0x2b31  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow()
0x2b36  pop
0x2b37  ldarg.0
0x2b38  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2b3d  pop
0x2b3e  ldarg.0
0x2b3f  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2b44  pop
0x2b45  ldarg.0
0x2b46  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2b4b  ldc.i4.3
0x2b4c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_ColSpan(int32)
0x2b51  ldarg.0
0x2b52  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x2b57  ldarg.0
0x2b58  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileExtnID
0x2b5d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2b62  ldarg.0
0x2b63  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x2b68  ldc.i4.1
0x2b69  callvirt instance void [System.Web]System.Web.UI.WebControls.CheckBox::set_Checked(bool)
0x2b6e  ldarg.0
0x2b6f  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x2b74  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2b79  ldstr    aAriaLabel// "aria-label"
0x2b7e  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtension()
0x2b83  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b88  ldarg.0
0x2b89  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2b8e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2b93  ldarg.0
0x2b94  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x2b99  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2b9e  ldarg.0
0x2b9f  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtension()
0x2ba4  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddLabel(string unencodedText)
0x2ba9  ldarg.0
0x2baa  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow()
0x2baf  pop
0x2bb0  ldarg.0
0x2bb1  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2bb6  pop
0x2bb7  ldarg.0
0x2bb8  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Path()
0x2bbd  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddLabel(string unencodedText)
0x2bc2  ldarg.0
0x2bc3  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2bc8  pop
0x2bc9  ldarg.0
0x2bca  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2bcf  ldc.i4.3
0x2bd0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_ColSpan(int32)
0x2bd5  ldarg.0
0x2bd6  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PushNewTable()
0x2bdb  pop
0x2bdc  ldarg.0
0x2bdd  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow()
0x2be2  pop
0x2be3  ldarg.0
0x2be4  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2be9  pop
0x2bea  ldarg.0
0x2beb  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2bf0  ldc.i4.s 0x4B
0x2bf2  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Columns(int32)
0x2bf7  ldarg.0
0x2bf8  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2bfd  ldc.i4.0
0x2bfe  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_TextMode(valuetype [System.Web]System.Web.UI.WebControls.TextBoxMode)
0x2c03  ldarg.0
0x2c04  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2c09  ldarg.0
0x2c0a  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_PathID
0x2c0f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2c14  ldarg.0
0x2c15  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2c1a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2c1f  ldstr    aAriaLabel// "aria-label"
0x2c24  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Path()
0x2c29  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2c2e  ldarg.0
0x2c2f  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2c34  call     void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddTextBoxStyles(class [System.Web]System.Web.UI.WebControls.TextBox txt)
0x2c39  ldarg.0
0x2c3a  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2c3f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2c44  ldarg.0
0x2c45  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2c4a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2c4f  ldarg.0
0x2c50  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x2c55  pop
0x2c56  ldarg.0
0x2c57  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2c5c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2c61  ldarg.0
0x2c62  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWordReq
0x2c67  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2c6c  ldarg.0
0x2c6d  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPathNameRequired
0x2c72  ldc.i4.2
0x2c73  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_Display(valuetype [System.Web]System.Web.UI.WebControls.ValidatorDisplay)
0x2c78  ldarg.0
0x2c79  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPathNameRequired
0x2c7e  ldarg.0
0x2c7f  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_PathID
0x2c84  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string)
0x2c89  ldarg.0
0x2c8a  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPathNameRequired
0x2c8f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2c94  ldarg.0
0x2c95  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_EmptyPath()
0x2c9a  ldc.i4.1
0x2c9b  call     instance class [System.Web]System.Web.UI.Control Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage(string error, bool noWrap)
0x2ca0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2ca5  ldarg.0
0x2ca6  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWordReq
0x2cab  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2cb0  ldarg.0
0x2cb1  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPathNameRequired
  ... truncated ...
```
