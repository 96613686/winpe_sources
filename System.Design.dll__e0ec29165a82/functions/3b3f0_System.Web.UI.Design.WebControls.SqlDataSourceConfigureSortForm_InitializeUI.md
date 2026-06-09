# System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::InitializeUI

- ea: `0x3b3f0`
- end: `0x3b5cf`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::InitializeUI`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x3a5e0`

## callees

- `0x8ef40`

## string_xrefs

- `0x3b3f6`: `SqlDataSourceConfigureSortForm_HelpLabel`
- `0x3b420`: `SqlDataSourceConfigureSortForm_SortByLabel`
- `0x3b435`: `SqlDataSourceConfigureSortForm_ThenByLabel`
- `0x3b44a`: `SqlDataSourceConfigureSortForm_ThenByLabel`
- `0x3b45f`: `SqlDataSourceConfigureSortForm_AscendingLabel`
- `0x3b489`: `SqlDataSourceConfigureSortForm_AscendingLabel`
- `0x3b4b3`: `SqlDataSourceConfigureSortForm_AscendingLabel`
- `0x3b474`: `SqlDataSourceConfigureSortForm_DescendingLabel`
- `0x3b49e`: `SqlDataSourceConfigureSortForm_DescendingLabel`
- `0x3b4c8`: `SqlDataSourceConfigureSortForm_DescendingLabel`
- `0x3b4dd`: `SqlDataSourceConfigureSortForm_SortDirection1`
- `0x3b4f2`: `SqlDataSourceConfigureSortForm_SortDirection1`
- `0x3b507`: `SqlDataSourceConfigureSortForm_SortDirection2`
- `0x3b51c`: `SqlDataSourceConfigureSortForm_SortDirection2`
- `0x3b531`: `SqlDataSourceConfigureSortForm_SortDirection3`
- `0x3b546`: `SqlDataSourceConfigureSortForm_SortDirection3`
- `0x3b55b`: `SqlDataSourceConfigureSortForm_SortColumn1`
- `0x3b570`: `SqlDataSourceConfigureSortForm_SortColumn2`
- `0x3b585`: `SqlDataSourceConfigureSortForm_SortColumn3`
- `0x3b5bf`: `SqlDataSourceConfigureSortForm_Caption`

## pseudocode

```c

```

## disassembly

```asm
0x3b3f0  ldarg.0
0x3b3f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3b3f6  ldstr    aSqldatasourcec_29// "SqlDataSourceConfigureSortForm_HelpLabe"...
0x3b3fb  call     string System.Design.SR::GetString(string name)
0x3b400  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b405  ldarg.0
0x3b406  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_previewLabel
0x3b40b  ldstr    aSqldatasourceG// "SqlDataSource_General_PreviewLabel"
0x3b410  call     string System.Design.SR::GetString(string name)
0x3b415  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b41a  ldarg.0
0x3b41b  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox1
0x3b420  ldstr    aSqldatasourcec_30// "SqlDataSourceConfigureSortForm_SortByLa"...
0x3b425  call     string System.Design.SR::GetString(string name)
0x3b42a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b42f  ldarg.0
0x3b430  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox2
0x3b435  ldstr    aSqldatasourcec_31// "SqlDataSourceConfigureSortForm_ThenByLa"...
0x3b43a  call     string System.Design.SR::GetString(string name)
0x3b43f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b444  ldarg.0
0x3b445  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox3
0x3b44a  ldstr    aSqldatasourcec_31// "SqlDataSourceConfigureSortForm_ThenByLa"...
0x3b44f  call     string System.Design.SR::GetString(string name)
0x3b454  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b459  ldarg.0
0x3b45a  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3b45f  ldstr    aSqldatasourcec_32// "SqlDataSourceConfigureSortForm_Ascendin"...
0x3b464  call     string System.Design.SR::GetString(string name)
0x3b469  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b46e  ldarg.0
0x3b46f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3b474  ldstr    aSqldatasourcec_33// "SqlDataSourceConfigureSortForm_Descendi"...
0x3b479  call     string System.Design.SR::GetString(string name)
0x3b47e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b483  ldarg.0
0x3b484  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3b489  ldstr    aSqldatasourcec_32// "SqlDataSourceConfigureSortForm_Ascendin"...
0x3b48e  call     string System.Design.SR::GetString(string name)
0x3b493  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b498  ldarg.0
0x3b499  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3b49e  ldstr    aSqldatasourcec_33// "SqlDataSourceConfigureSortForm_Descendi"...
0x3b4a3  call     string System.Design.SR::GetString(string name)
0x3b4a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b4ad  ldarg.0
0x3b4ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton3
0x3b4b3  ldstr    aSqldatasourcec_32// "SqlDataSourceConfigureSortForm_Ascendin"...
0x3b4b8  call     string System.Design.SR::GetString(string name)
0x3b4bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b4c2  ldarg.0
0x3b4c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton3
0x3b4c8  ldstr    aSqldatasourcec_33// "SqlDataSourceConfigureSortForm_Descendi"...
0x3b4cd  call     string System.Design.SR::GetString(string name)
0x3b4d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b4d7  ldarg.0
0x3b4d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3b4dd  ldstr    aSqldatasourcec_34// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b4e2  call     string System.Design.SR::GetString(string name)
0x3b4e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b4ec  ldarg.0
0x3b4ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3b4f2  ldstr    aSqldatasourcec_34// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b4f7  call     string System.Design.SR::GetString(string name)
0x3b4fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b501  ldarg.0
0x3b502  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3b507  ldstr    aSqldatasourcec_35// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b50c  call     string System.Design.SR::GetString(string name)
0x3b511  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b516  ldarg.0
0x3b517  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3b51c  ldstr    aSqldatasourcec_35// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b521  call     string System.Design.SR::GetString(string name)
0x3b526  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b52b  ldarg.0
0x3b52c  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton3
0x3b531  ldstr    aSqldatasourcec_36// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b536  call     string System.Design.SR::GetString(string name)
0x3b53b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b540  ldarg.0
0x3b541  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton3
0x3b546  ldstr    aSqldatasourcec_36// "SqlDataSourceConfigureSortForm_SortDire"...
0x3b54b  call     string System.Design.SR::GetString(string name)
0x3b550  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x3b555  ldarg.0
0x3b556  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3b55b  ldstr    aSqldatasourcec_37// "SqlDataSourceConfigureSortForm_SortColu"...
0x3b560  call     string System.Design.SR::GetString(string name)
0x3b565  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x3b56a  ldarg.0
0x3b56b  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3b570  ldstr    aSqldatasourcec_38// "SqlDataSourceConfigureSortForm_SortColu"...
0x3b575  call     string System.Design.SR::GetString(string name)
0x3b57a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x3b57f  ldarg.0
0x3b580  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox3
0x3b585  ldstr    aSqldatasourcec_39// "SqlDataSourceConfigureSortForm_SortColu"...
0x3b58a  call     string System.Design.SR::GetString(string name)
0x3b58f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x3b594  ldarg.0
0x3b595  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_okButton
0x3b59a  ldstr    aOk// "OK"
0x3b59f  call     string System.Design.SR::GetString(string name)
0x3b5a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b5a9  ldarg.0
0x3b5aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_cancelButton
0x3b5af  ldstr    aCancel// "Cancel"
0x3b5b4  call     string System.Design.SR::GetString(string name)
0x3b5b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b5be  ldarg.0
0x3b5bf  ldstr    aSqldatasourcec_40// "SqlDataSourceConfigureSortForm_Caption"
0x3b5c4  call     string System.Design.SR::GetString(string name)
0x3b5c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3b5ce  ret
```
