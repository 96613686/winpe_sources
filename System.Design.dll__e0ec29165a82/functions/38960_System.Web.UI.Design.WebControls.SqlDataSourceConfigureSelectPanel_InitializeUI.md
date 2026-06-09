# System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::InitializeUI

- ea: `0x38960`
- end: `0x38aa1`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::InitializeUI`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x37db0`

## callees

- `0x3a550`
- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x38961`: `SqlDataSourceConfigureSelectPanel_PanelCaption`
- `0x38976`: `SqlDataSourceConfigureSelectPanel_RetrieveDataLabel`
- `0x3898b`: `SqlDataSourceConfigureSelectPanel_TableLabel`
- `0x389a0`: `SqlDataSourceConfigureSelectPanel_CustomSqlLabel`
- `0x389ca`: `SqlDataSourceConfigureSelectPanel_TableNameLabel`
- `0x389df`: `SqlDataSourceConfigureSelectPanel_SortButton`
- `0x389f4`: `SqlDataSourceConfigureSelectPanel_FilterLabel`
- `0x38a09`: `SqlDataSourceConfigureSelectPanel_SelectDistinctLabel`
- `0x38a1e`: `SqlDataSourceConfigureSelectPanel_AdvancedOptions`
- `0x38a33`: `SqlDataSourceConfigureSelectPanel_FieldsLabel`

## pseudocode

```c

```

## disassembly

```asm
0x38960  ldarg.0
0x38961  ldstr    aSqldatasourcec_17// "SqlDataSourceConfigureSelectPanel_Panel"...
0x38966  call     string System.Design.SR::GetString(string name)
0x3896b  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x38970  ldarg.0
0x38971  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x38976  ldstr    aSqldatasourcec_18// "SqlDataSourceConfigureSelectPanel_Retri"...
0x3897b  call     string System.Design.SR::GetString(string name)
0x38980  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x38985  ldarg.0
0x38986  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x3898b  ldstr    aSqldatasourcec_19// "SqlDataSourceConfigureSelectPanel_Table"...
0x38990  call     string System.Design.SR::GetString(string name)
0x38995  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3899a  ldarg.0
0x3899b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x389a0  ldstr    aSqldatasourcec_20// "SqlDataSourceConfigureSelectPanel_Custo"...
0x389a5  call     string System.Design.SR::GetString(string name)
0x389aa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x389af  ldarg.0
0x389b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_previewLabel
0x389b5  ldstr    aSqldatasourceG// "SqlDataSource_General_PreviewLabel"
0x389ba  call     string System.Design.SR::GetString(string name)
0x389bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x389c4  ldarg.0
0x389c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x389ca  ldstr    aSqldatasourcec_21// "SqlDataSourceConfigureSelectPanel_Table"...
0x389cf  call     string System.Design.SR::GetString(string name)
0x389d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x389d9  ldarg.0
0x389da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_addSortButton
0x389df  ldstr    aSqldatasourcec_22// "SqlDataSourceConfigureSelectPanel_SortB"...
0x389e4  call     string System.Design.SR::GetString(string name)
0x389e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x389ee  ldarg.0
0x389ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_addFilterButton
0x389f4  ldstr    aSqldatasourcec_23// "SqlDataSourceConfigureSelectPanel_Filte"...
0x389f9  call     string System.Design.SR::GetString(string name)
0x389fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x38a03  ldarg.0
0x38a04  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_selectDistinctCheckBox
0x38a09  ldstr    aSqldatasourcec_24// "SqlDataSourceConfigureSelectPanel_Selec"...
0x38a0e  call     string System.Design.SR::GetString(string name)
0x38a13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x38a18  ldarg.0
0x38a19  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_advancedOptionsButton
0x38a1e  ldstr    aSqldatasourcec_25// "SqlDataSourceConfigureSelectPanel_Advan"...
0x38a23  call     string System.Design.SR::GetString(string name)
0x38a28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x38a2d  ldarg.0
0x38a2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x38a33  ldstr    aSqldatasourcec_26// "SqlDataSourceConfigureSelectPanel_Field"...
0x38a38  call     string System.Design.SR::GetString(string name)
0x38a3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x38a42  ldarg.0
0x38a43  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38a48  ldarg.0
0x38a49  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x38a4e  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x38a53  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x38a58  ldarg.0
0x38a59  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38a5e  ldarg.0
0x38a5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38a64  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x38a69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x38a6e  ldarg.0
0x38a6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x38a74  ldarg.0
0x38a75  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x38a7a  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x38a7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x38a84  ldarg.0
0x38a85  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x38a8a  ldarg.0
0x38a8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x38a90  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x38a95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x38a9a  ldarg.0
0x38a9b  call     instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::UpdateFonts()
0x38aa0  ret
```
