# System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::InitializeUI

- ea: `0x36de0`
- end: `0x36f17`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::InitializeUI`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x35fb0`

## callees

- `0x8ef40`

## string_xrefs

- `0x36de6`: `SqlDataSourceConfigureFilterForm_HelpLabel`
- `0x36dfb`: `SqlDataSourceConfigureFilterForm_ColumnLabel`
- `0x36e10`: `SqlDataSourceConfigureFilterForm_OperatorLabel`
- `0x36e25`: `SqlDataSourceConfigureFilterForm_WhereLabel`
- `0x36e3a`: `SqlDataSourceConfigureFilterForm_ExpressionLabel`
- `0x36e4f`: `SqlDataSourceConfigureFilterForm_ValueLabel`
- `0x36e64`: `SqlDataSourceConfigureFilterForm_ExpressionColumnHeader`
- `0x36e79`: `SqlDataSourceConfigureFilterForm_ValueColumnHeader`
- `0x36e8e`: `SqlDataSourceConfigureFilterForm_ParameterPropertiesGroup`
- `0x36ea3`: `SqlDataSourceConfigureFilterForm_SourceLabel`
- `0x36eb8`: `SqlDataSourceConfigureFilterForm_AddButton`
- `0x36ecd`: `SqlDataSourceConfigureFilterForm_RemoveButton`
- `0x36f07`: `SqlDataSourceConfigureFilterForm_Caption`

## pseudocode

```c

```

## disassembly

```asm
0x36de0  ldarg.0
0x36de1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36de6  ldstr    aSqldatasourcec_0// "SqlDataSourceConfigureFilterForm_HelpLa"...
0x36deb  call     string System.Design.SR::GetString(string name)
0x36df0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36df5  ldarg.0
0x36df6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x36dfb  ldstr    aSqldatasourcec_1// "SqlDataSourceConfigureFilterForm_Column"...
0x36e00  call     string System.Design.SR::GetString(string name)
0x36e05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e0a  ldarg.0
0x36e0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x36e10  ldstr    aSqldatasourcec_2// "SqlDataSourceConfigureFilterForm_Operat"...
0x36e15  call     string System.Design.SR::GetString(string name)
0x36e1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e1f  ldarg.0
0x36e20  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_whereClausesLabel
0x36e25  ldstr    aSqldatasourcec_3// "SqlDataSourceConfigureFilterForm_WhereL"...
0x36e2a  call     string System.Design.SR::GetString(string name)
0x36e2f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e34  ldarg.0
0x36e35  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_expressionLabel
0x36e3a  ldstr    aSqldatasourcec_4// "SqlDataSourceConfigureFilterForm_Expres"...
0x36e3f  call     string System.Design.SR::GetString(string name)
0x36e44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e49  ldarg.0
0x36e4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_valueLabel
0x36e4f  ldstr    aSqldatasourcec_5// "SqlDataSourceConfigureFilterForm_ValueL"...
0x36e54  call     string System.Design.SR::GetString(string name)
0x36e59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e5e  ldarg.0
0x36e5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_expressionColumnHeader
0x36e64  ldstr    aSqldatasourcec_6// "SqlDataSourceConfigureFilterForm_Expres"...
0x36e69  call     string System.Design.SR::GetString(string name)
0x36e6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Text(string)
0x36e73  ldarg.0
0x36e74  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_valueColumnHeader
0x36e79  ldstr    aSqldatasourcec_7// "SqlDataSourceConfigureFilterForm_ValueC"...
0x36e7e  call     string System.Design.SR::GetString(string name)
0x36e83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Text(string)
0x36e88  ldarg.0
0x36e89  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36e8e  ldstr    aSqldatasourcec_8// "SqlDataSourceConfigureFilterForm_Parame"...
0x36e93  call     string System.Design.SR::GetString(string name)
0x36e98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36e9d  ldarg.0
0x36e9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x36ea3  ldstr    aSqldatasourcec_9// "SqlDataSourceConfigureFilterForm_Source"...
0x36ea8  call     string System.Design.SR::GetString(string name)
0x36ead  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36eb2  ldarg.0
0x36eb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_addButton
0x36eb8  ldstr    aSqldatasourcec_10// "SqlDataSourceConfigureFilterForm_AddBut"...
0x36ebd  call     string System.Design.SR::GetString(string name)
0x36ec2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36ec7  ldarg.0
0x36ec8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_removeButton
0x36ecd  ldstr    aSqldatasourcec_11// "SqlDataSourceConfigureFilterForm_Remove"...
0x36ed2  call     string System.Design.SR::GetString(string name)
0x36ed7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36edc  ldarg.0
0x36edd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_okButton
0x36ee2  ldstr    aOk// "OK"
0x36ee7  call     string System.Design.SR::GetString(string name)
0x36eec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36ef1  ldarg.0
0x36ef2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_cancelButton
0x36ef7  ldstr    aCancel// "Cancel"
0x36efc  call     string System.Design.SR::GetString(string name)
0x36f01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36f06  ldarg.0
0x36f07  ldstr    aSqldatasourcec_12// "SqlDataSourceConfigureFilterForm_Captio"...
0x36f0c  call     string System.Design.SR::GetString(string name)
0x36f11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x36f16  ret
```
