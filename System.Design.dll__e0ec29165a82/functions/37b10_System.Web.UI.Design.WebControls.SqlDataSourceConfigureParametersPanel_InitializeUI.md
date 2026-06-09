# System.Web.UI.Design.WebControls.SqlDataSourceConfigureParametersPanel::InitializeUI

- ea: `0x37b10`
- end: `0x37b4b`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureParametersPanel::InitializeUI`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x37800`

## callees

- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x37b11`: `SqlDataSourceConfigureParametersPanel_PanelCaption`
- `0x37b26`: `SqlDataSourceConfigureParametersPanel_HelpLabel`

## pseudocode

```c

```

## disassembly

```asm
0x37b10  ldarg.0
0x37b11  ldstr    aSqldatasourcec_14// "SqlDataSourceConfigureParametersPanel_P"...
0x37b16  call     string System.Design.SR::GetString(string name)
0x37b1b  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x37b20  ldarg.0
0x37b21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureParametersPanel::_helpLabel
0x37b26  ldstr    aSqldatasourcec_15// "SqlDataSourceConfigureParametersPanel_H"...
0x37b2b  call     string System.Design.SR::GetString(string name)
0x37b30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x37b35  ldarg.0
0x37b36  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureParametersPanel::_previewLabel
0x37b3b  ldstr    aSqldatasourceG// "SqlDataSource_General_PreviewLabel"
0x37b40  call     string System.Design.SR::GetString(string name)
0x37b45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x37b4a  ret
```
