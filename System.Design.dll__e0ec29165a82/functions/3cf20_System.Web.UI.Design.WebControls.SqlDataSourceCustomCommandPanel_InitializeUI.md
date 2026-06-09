# System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::InitializeUI

- ea: `0x3cf20`
- end: `0x3cf46`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::InitializeUI`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3c9a0`

## callees

- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x3cf26`: `SqlDataSourceCustomCommandPanel_HelpLabel`
- `0x3cf36`: `SqlDataSourceCustomCommandPanel_PanelCaption`

## pseudocode

```c

```

## disassembly

```asm
0x3cf20  ldarg.0
0x3cf21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3cf26  ldstr    aSqldatasourcec_50// "SqlDataSourceCustomCommandPanel_HelpLab"...
0x3cf2b  call     string System.Design.SR::GetString(string name)
0x3cf30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3cf35  ldarg.0
0x3cf36  ldstr    aSqldatasourcec_51// "SqlDataSourceCustomCommandPanel_PanelCa"...
0x3cf3b  call     string System.Design.SR::GetString(string name)
0x3cf40  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x3cf45  ret
```
