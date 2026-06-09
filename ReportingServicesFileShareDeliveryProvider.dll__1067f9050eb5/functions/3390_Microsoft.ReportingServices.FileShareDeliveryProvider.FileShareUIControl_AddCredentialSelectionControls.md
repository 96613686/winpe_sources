# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddCredentialSelectionControls

- ea: `0x3390`
- end: `0x34e1`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddCredentialSelectionControls`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x1ee0`
- `0x1f60`
- `0x2000`
- `0x2070`
- `0x20a0`
- `0x20e0`
- `0x21b0`
- `0x3390`
- `0x3aa0`
- `0x3ab0`
- `0x3ac0`

## pseudocode

```c

```

## disassembly

```asm
0x3390  ldarg.0
0x3391  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x3396  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x339b  ldstr    aClass// "class"
0x33a0  ldstr    aMsrsNormal// "msrs-normal"
0x33a5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x33aa  ldarg.0
0x33ab  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x33b0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x33b5  ldstr    aAriaLabel// "aria-label"
0x33ba  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_SecurityCredentials()
0x33bf  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x33c4  ldarg.0
0x33c5  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x33ca  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x33cf  ldstr    aRole// "role"
0x33d4  ldstr    aRadiogroup// "radiogroup"
0x33d9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x33de  ldarg.0
0x33df  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x33e4  ldstr    aCredentialsele// "CredentialSelection"
0x33e9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x33ee  ldarg.0
0x33ef  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x33f4  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x33f9  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UseFileShareAccount()
0x33fe  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x3403  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x3408  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x340d  ldarg.0
0x340e  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x3413  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x3418  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_WindowsCredentials()
0x341d  ldstr    aCustomcredenti// "CustomCredentials"
0x3422  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x3427  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x342c  ldarg.0
0x342d  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x3432  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x3437  ldstr    aOnclick// "onclick"
0x343c  ldstr    aCredentialsele_0// "CredentialSelectionChanged();"
0x3441  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x3446  ldarg.0
0x3447  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x344c  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x3451  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x3456  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItem [System.Web]System.Web.UI.WebControls.ListItemCollection::FindByValue(string)
0x345b  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_DefaultAccountSpecified()
0x3460  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Enabled(bool)
0x3465  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_DefaultAccountSpecified()
0x346a  brfalse.s loc_347E
0x346c  ldarg.0
0x346d  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x3472  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x3477  callvirt instance void [System.Web]System.Web.UI.WebControls.ListControl::set_SelectedValue(string)
0x347c  br.s     loc_348E
0x347e  ldarg.0
0x347f  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x3484  ldstr    aCustomcredenti// "CustomCredentials"
0x3489  callvirt instance void [System.Web]System.Web.UI.WebControls.ListControl::set_SelectedValue(string)
0x348e  ldarg.0
0x348f  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x3494  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x3499  ldarg.0
0x349a  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x349f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x34a4  ldarg.0
0x34a5  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x34aa  ldc.i4.1
0x34ab  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_NoWrap(bool)
0x34b0  ldarg.0
0x34b1  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x34b6  ldc.i4.2
0x34b7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_ColSpan(int32)
0x34bc  ldarg.0
0x34bd  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PopTable()
0x34c2  pop
0x34c3  ldarg.0
0x34c4  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PushNewTable()
0x34c9  pop
0x34ca  ldarg.0
0x34cb  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow()
0x34d0  pop
0x34d1  ldarg.0
0x34d2  ldc.i4.s 0x14
0x34d4  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddHorizontalSpacerCell(int32 width)
0x34d9  ldarg.0
0x34da  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x34df  pop
0x34e0  ret
```
