# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::UpdateRequiredFields

- ea: `0x26e0`
- end: `0x2727`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::UpdateRequiredFields`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2500`
- `0x3380`

## pseudocode

```c

```

## disassembly

```asm
0x26e0  ldarg.0
0x26e1  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x26e6  callvirt instance string [System.Web]System.Web.UI.WebControls.ListControl::get_SelectedValue()
0x26eb  ldstr    aCustomcredenti// "CustomCredentials"
0x26f0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x26f5  stloc.0
0x26f6  ldarg.0
0x26f7  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x26fc  ldloc.0
0x26fd  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Enabled(bool)
0x2702  ldarg.0
0x2703  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWord
0x2708  ldloc.0
0x2709  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Enabled(bool)
0x270e  ldarg.0
0x270f  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserNameRequired
0x2714  ldloc.0
0x2715  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Enabled(bool)
0x271a  ldarg.0
0x271b  ldfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWordRequired
0x2720  ldloc.0
0x2721  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Enabled(bool)
0x2726  ret
```
