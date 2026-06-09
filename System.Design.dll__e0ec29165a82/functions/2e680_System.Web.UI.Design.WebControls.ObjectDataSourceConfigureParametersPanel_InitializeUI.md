# System.Web.UI.Design.WebControls.ObjectDataSourceConfigureParametersPanel::InitializeUI

- ea: `0x2e680`
- end: `0x2e6bb`
- name: `System.Web.UI.Design.WebControls.ObjectDataSourceConfigureParametersPanel::InitializeUI`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x2e3a0`

## callees

- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x2e681`: `ObjectDataSourceConfigureParametersPanel_PanelCaption`
- `0x2e696`: `ObjectDataSourceConfigureParametersPanel_HelpLabel`

## pseudocode

```c

```

## disassembly

```asm
0x2e680  ldarg.0
0x2e681  ldstr    aObjectdatasour_10// "ObjectDataSourceConfigureParametersPane"...
0x2e686  call     string System.Design.SR::GetString(string name)
0x2e68b  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x2e690  ldarg.0
0x2e691  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceConfigureParametersPanel::_helpLabel
0x2e696  ldstr    aObjectdatasour_11// "ObjectDataSourceConfigureParametersPane"...
0x2e69b  call     string System.Design.SR::GetString(string name)
0x2e6a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2e6a5  ldarg.0
0x2e6a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceConfigureParametersPanel::_signatureLabel
0x2e6ab  ldstr    aObjectdatasour_12// "ObjectDataSource_General_MethodSignatur"...
0x2e6b0  call     string System.Design.SR::GetString(string name)
0x2e6b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2e6ba  ret
```
