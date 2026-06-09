# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_UserData

- ea: `0x2430`
- end: `0x24f5`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_UserData`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x840`
- `0x860`
- `0x880`
- `0x8a0`
- `0x950`
- `0x36f0`
- `0x3730`
- `0x3750`
- `0x3770`
- `0x37f0`
- `0x3860`

## pseudocode

```c

```

## disassembly

```asm
0x2430  newobj   instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::.ctor()
0x2435  dup
0x2436  ldarg.0
0x2437  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x243c  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2441  callvirt instance string [mscorlib]System.String::Trim()
0x2446  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_FileName(string value)
0x244b  dup
0x244c  ldarg.0
0x244d  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2452  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2457  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath(string filePathOriginal)
0x245c  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_Path(string value)
0x2461  dup
0x2462  ldarg.0
0x2463  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x2468  callvirt instance bool [System.Web]System.Web.UI.WebControls.CheckBox::get_Checked()
0x246d  callvirt instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_FileExtn(bool value)
0x2472  dup
0x2473  ldarg.0
0x2474  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x2479  callvirt instance string [System.Web]System.Web.UI.WebControls.ListControl::get_SelectedValue()
0x247e  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x2483  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2488  callvirt instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UsingDefaultCreds(bool value)
0x248d  dup
0x248e  ldarg.0
0x248f  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x2494  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2499  callvirt instance string [mscorlib]System.String::Trim()
0x249e  callvirt instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UserName(string value)
0x24a3  dup
0x24a4  ldarg.0
0x24a5  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWord
0x24aa  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x24af  callvirt instance string [mscorlib]System.String::Trim()
0x24b4  callvirt instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_PassWord(string value)
0x24b9  dup
0x24ba  ldarg.0
0x24bb  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbWriteMode
0x24c0  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItem [System.Web]System.Web.UI.WebControls.ListControl::get_SelectedItem()
0x24c5  callvirt instance string [System.Web]System.Web.UI.WebControls.ListItem::get_Value()
0x24ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24cf  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x24d4  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_WriteMode(string value)
0x24d9  dup
0x24da  ldarg.0
0x24db  ldfld    class [System.Web]System.Web.UI.WebControls.DropDownList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_ddRenderFormat
0x24e0  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItem [System.Web]System.Web.UI.WebControls.ListControl::get_SelectedItem()
0x24e5  callvirt instance string [System.Web]System.Web.UI.WebControls.ListItem::get_Value()
0x24ea  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_RenderFormat(string value)
0x24ef  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::ToSettingArray()
0x24f4  ret
```
