# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Validate

- ea: `0x2350`
- end: `0x240f`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Validate`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18e0`
- `0x2350`
- `0x34f0`
- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x2350  ldarg.0
0x2351  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x2356  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x235b  callvirt instance string [mscorlib]System.String::Trim()
0x2360  ldstr    asc_5248// ""
0x2365  call     bool [mscorlib]System.String::op_Equality(string, string)
0x236a  brtrue.s loc_2388
0x236c  ldarg.0
0x236d  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2372  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2377  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath(string filePathOriginal)
0x237c  ldstr    asc_5248// ""
0x2381  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2386  brfalse.s loc_238A
0x2388  ldc.i4.0
0x2389  ret
0x238a  ldarg.0
0x238b  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2390  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2395  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath(string filePathOriginal)
0x239a  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidPath(string pathname)
0x239f  brtrue.s loc_23A3
0x23a1  ldc.i4.0
0x23a2  ret
0x23a3  ldarg.0
0x23a4  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x23a9  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x23ae  callvirt instance string [mscorlib]System.String::Trim()
0x23b3  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ValidateFileName(string FileName)
0x23b8  brtrue.s loc_23BC
0x23ba  ldc.i4.0
0x23bb  ret
0x23bc  ldarg.0
0x23bd  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x23c2  callvirt instance string [System.Web]System.Web.UI.WebControls.ListControl::get_SelectedValue()
0x23c7  ldstr    aCustomcredenti// "CustomCredentials"
0x23cc  callvirt instance bool [mscorlib]System.String::Equals(string)
0x23d1  brfalse.s loc_240D
0x23d3  ldarg.0
0x23d4  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x23d9  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x23de  callvirt instance string [mscorlib]System.String::Trim()
0x23e3  ldstr    asc_5248// ""
0x23e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23ed  brtrue.s loc_240B
0x23ef  ldarg.0
0x23f0  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWord
0x23f5  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x23fa  callvirt instance string [mscorlib]System.String::Trim()
0x23ff  ldstr    asc_5248// ""
0x2404  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2409  brfalse.s loc_240D
0x240b  ldc.i4.0
0x240c  ret
0x240d  ldc.i4.1
0x240e  ret
```
