# System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::InitializeUI

- ea: `0x41160`
- end: `0x411c5`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::InitializeUI`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x40da0`

## callees

- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x41166`: `SqlDataSourceSaveConfiguredConnectionPanel_HelpLabel`
- `0x4117b`: `SqlDataSourceSaveConfiguredConnectionPanel_SaveLabel`
- `0x41190`: `SqlDataSourceSaveConfiguredConnectionPanel_SaveCheckBox`
- `0x411a5`: `SqlDataSourceSaveConfiguredConnectionPanel_NameTextBoxDescription`
- `0x411b5`: `SqlDataSourceSaveConfiguredConnectionPanel_PanelCaption`

## pseudocode

```c

```

## disassembly

```asm
0x41160  ldarg.0
0x41161  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::_helpLabel
0x41166  ldstr    aSqldatasources_0// "SqlDataSourceSaveConfiguredConnectionPa"...
0x4116b  call     string System.Design.SR::GetString(string name)
0x41170  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x41175  ldarg.0
0x41176  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::_saveLabel
0x4117b  ldstr    aSqldatasources_1// "SqlDataSourceSaveConfiguredConnectionPa"...
0x41180  call     string System.Design.SR::GetString(string name)
0x41185  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4118a  ldarg.0
0x4118b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::_saveCheckBox
0x41190  ldstr    aSqldatasources_2// "SqlDataSourceSaveConfiguredConnectionPa"...
0x41195  call     string System.Design.SR::GetString(string name)
0x4119a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4119f  ldarg.0
0x411a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceSaveConfiguredConnectionPanel::_nameHelpLabel
0x411a5  ldstr    aSqldatasources_3// "SqlDataSourceSaveConfiguredConnectionPa"...
0x411aa  call     string System.Design.SR::GetString(string name)
0x411af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x411b4  ldarg.0
0x411b5  ldstr    aSqldatasources_4// "SqlDataSourceSaveConfiguredConnectionPa"...
0x411ba  call     string System.Design.SR::GetString(string name)
0x411bf  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x411c4  ret
```
