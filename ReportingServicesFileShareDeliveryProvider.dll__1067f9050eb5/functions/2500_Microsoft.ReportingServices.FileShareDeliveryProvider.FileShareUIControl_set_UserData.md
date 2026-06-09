# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::set_UserData

- ea: `0x2500`
- end: `0x26d2`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::set_UserData`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x850`
- `0x870`
- `0x890`
- `0x8b0`
- `0x8c0`
- `0x2500`
- `0x26e0`
- `0x2730`
- `0x3740`
- `0x3760`
- `0x3830`
- `0x3860`

## pseudocode

```c

```

## disassembly

```asm
0x2500  newobj   instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::.ctor()
0x2505  stloc.0
0x2506  ldloc.0
0x2507  ldarg.1
0x2508  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x250d  ldloc.0
0x250e  callvirt instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_UsingDefaultCreds()
0x2513  brfalse.s loc_2527
0x2515  ldarg.0
0x2516  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x251b  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x2520  callvirt instance void [System.Web]System.Web.UI.WebControls.ListControl::set_SelectedValue(string)
0x2525  br.s     loc_2537
0x2527  ldarg.0
0x2528  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x252d  ldstr    aCustomcredenti// "CustomCredentials"
0x2532  callvirt instance void [System.Web]System.Web.UI.WebControls.ListControl::set_SelectedValue(string)
0x2537  ldarg.0
0x2538  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::UpdateRequiredFields()
0x253d  ldarg.0
0x253e  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2543  ldloc.0
0x2544  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x2549  callvirt instance string [mscorlib]System.String::Trim()
0x254e  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x2553  ldarg.0
0x2554  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2559  ldloc.0
0x255a  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x255f  callvirt instance string [mscorlib]System.String::Trim()
0x2564  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x2569  ldarg.0
0x256a  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x256f  ldloc.0
0x2570  callvirt instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FileExtn()
0x2575  callvirt instance void [System.Web]System.Web.UI.WebControls.CheckBox::set_Checked(bool)
0x257a  ldarg.0
0x257b  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2580  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2585  ldstr    aOnchange// "onchange"
0x258a  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x258f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2594  ldarg.0
0x2595  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x259a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x259f  ldstr    aOnchange// "onchange"
0x25a4  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x25a9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25ae  ldarg.0
0x25af  ldfld    class [System.Web]System.Web.UI.WebControls.DropDownList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_ddRenderFormat
0x25b4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x25b9  ldstr    aOnchange// "onchange"
0x25be  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x25c3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25c8  ldarg.0
0x25c9  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x25ce  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x25d3  ldstr    aOnclick// "onclick"
0x25d8  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x25dd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25e2  ldarg.0
0x25e3  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbWriteMode
0x25e8  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x25ed  ldstr    aOnclick// "onclick"
0x25f2  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x25f7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25fc  ldarg.0
0x25fd  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x2602  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2607  ldstr    aOnchange// "onchange"
0x260c  ldstr    aJavascriptDocu// "JavaScript:document.getElementById('Sha"...
0x2611  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2616  ldarg.0
0x2617  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x261c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2621  ldstr    aValue// "value"
0x2626  ldloc.0
0x2627  callvirt instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FullyQualifiedUserName()
0x262c  call     string [System.Web]System.Web.HttpUtility::HtmlAttributeEncode(string)
0x2631  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2636  ldarg.0
0x2637  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWord
0x263c  ldc.i4.1
0x263d  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x2642  ldarg.0
0x2643  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbWriteMode
0x2648  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x264d  ldloc.0
0x264e  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x2653  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItem [System.Web]System.Web.UI.WebControls.ListItemCollection::FindByValue(string)
0x2658  ldc.i4.1
0x2659  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Selected(bool)
0x265e  leave.s  loc_2671
0x2660  stloc.1
0x2661  ldarg.0
0x2662  ldloc.1
0x2663  callvirt instance string [mscorlib]System.Object::ToString()
0x2668  ldc.i4.0
0x2669  call     instance class [System.Web]System.Web.UI.Control Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage(string error, bool noWrap)
0x266e  pop
0x266f  leave.s  loc_2671
0x2671  ldarg.0
0x2672  ldfld    class [System.Web]System.Web.UI.WebControls.DropDownList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_ddRenderFormat
0x2677  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x267c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.WebControls.ListItemCollection::GetEnumerator()
0x2681  stloc.2
0x2682  br.s     loc_26B3
0x2684  ldloc.2
0x2685  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x268a  castclass [System.Web]System.Web.UI.WebControls.ListItem
0x268f  stloc.3
0x2690  ldloc.3
0x2691  callvirt instance string [System.Web]System.Web.UI.WebControls.ListItem::get_Value()
0x2696  ldloc.0
0x2697  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_RenderFormat()
0x269c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26a1  brfalse.s loc_26AC
0x26a3  ldloc.3
0x26a4  ldc.i4.1
0x26a5  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Selected(bool)
0x26aa  br.s     loc_26B3
0x26ac  ldloc.3
0x26ad  ldc.i4.0
0x26ae  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Selected(bool)
0x26b3  ldloc.2
0x26b4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26b9  brtrue.s loc_2684
0x26bb  leave.s  loc_26D1
0x26bd  ldloc.2
0x26be  isinst   [mscorlib]System.IDisposable
0x26c3  stloc.s  4
0x26c5  ldloc.s  4
0x26c7  brfalse.s loc_26D0
0x26c9  ldloc.s  4
0x26cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d0  endfinally
0x26d1  ret
```
