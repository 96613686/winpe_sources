# System.Web.UI.Design.WebControls.AccessDataSourceConnectionChooserPanel::InitializeUI

- ea: `0x13d30`
- end: `0x13d80`
- name: `System.Web.UI.Design.WebControls.AccessDataSourceConnectionChooserPanel::InitializeUI`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x13a60`

## callees

- `0x541a0`
- `0x8ef40`

## string_xrefs

- `0x13d36`: `AccessDataSourceConnectionChooserPanel_DataFileLabel`
- `0x13d4b`: `AccessDataSourceConnectionChooserPanel_BrowseButton`
- `0x13d60`: `AccessDataSourceConnectionChooserPanel_HelpLabel`
- `0x13d70`: `AccessDataSourceConnectionChooserPanel_PanelCaption`

## pseudocode

```c

```

## disassembly

```asm
0x13d30  ldarg.0
0x13d31  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.AccessDataSourceConnectionChooserPanel::_dataFileLabel
0x13d36  ldstr    aAccessdatasour_1// "AccessDataSourceConnectionChooserPanel_"...
0x13d3b  call     string System.Design.SR::GetString(string name)
0x13d40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x13d45  ldarg.0
0x13d46  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.AccessDataSourceConnectionChooserPanel::_selectFileButton
0x13d4b  ldstr    aAccessdatasour_2// "AccessDataSourceConnectionChooserPanel_"...
0x13d50  call     string System.Design.SR::GetString(string name)
0x13d55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x13d5a  ldarg.0
0x13d5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.AccessDataSourceConnectionChooserPanel::_helpLabel
0x13d60  ldstr    aAccessdatasour_3// "AccessDataSourceConnectionChooserPanel_"...
0x13d65  call     string System.Design.SR::GetString(string name)
0x13d6a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x13d6f  ldarg.0
0x13d70  ldstr    aAccessdatasour_4// "AccessDataSourceConnectionChooserPanel_"...
0x13d75  call     string System.Design.SR::GetString(string name)
0x13d7a  call     instance void System.Web.UI.Design.Util.WizardPanel::set_Caption(string value)
0x13d7f  ret
```
