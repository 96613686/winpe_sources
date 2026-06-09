# Microsoft.Reporting.WebForms.DataSourceControl::CreateChildControls

- ea: `0xba00`
- end: `0xbb2d`
- name: `Microsoft.Reporting.WebForms.DataSourceControl::CreateChildControls`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14a0`
- `0x14b0`
- `0x2050`
- `0x40b0`
- `0xba00`
- `0xbba0`
- `0x22a80`

## string_xrefs

- `0xbab5`: `autocomplete`

## pseudocode

```c

```

## disassembly

```asm
0xba00  ldarg.0
0xba01  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xba06  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0xba0b  ldarg.0
0xba0c  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfo Microsoft.Reporting.WebForms.DataSourceControl::m_dsInfo
0xba11  callvirt instance string Microsoft.Reporting.WebForms.ReportDataSourceInfo::get_Prompt()
0xba16  brfalse.s loc_BA52
0xba18  ldarg.0
0xba19  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfo Microsoft.Reporting.WebForms.DataSourceControl::m_dsInfo
0xba1e  callvirt instance string Microsoft.Reporting.WebForms.ReportDataSourceInfo::get_Prompt()
0xba23  callvirt instance int32 [mscorlib]System.String::get_Length()
0xba28  ldc.i4.0
0xba29  ble.s    loc_BA52
0xba2b  ldarg.0
0xba2c  ldarg.0
0xba2d  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfo Microsoft.Reporting.WebForms.DataSourceControl::m_dsInfo
0xba32  callvirt instance string Microsoft.Reporting.WebForms.ReportDataSourceInfo::get_Prompt()
0xba37  newobj   instance void Microsoft.Reporting.WebForms.SafeLiteralControl::.ctor(string text)
0xba3c  stfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_dsPromptControl
0xba41  ldarg.0
0xba42  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xba47  ldarg.0
0xba48  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_dsPromptControl
0xba4d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xba52  ldarg.0
0xba53  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0xba58  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_UserNamePrompt()
0xba5d  newobj   instance void Microsoft.Reporting.WebForms.SafeLiteralControl::.ctor(string text)
0xba62  stfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_userPromptControl
0xba67  ldarg.0
0xba68  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xba6d  ldarg.0
0xba6e  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_userPromptControl
0xba73  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xba78  ldarg.0
0xba79  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0xba7e  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_PasswordPrompt()
0xba83  newobj   instance void Microsoft.Reporting.WebForms.SafeLiteralControl::.ctor(string text)
0xba88  stfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_pwdPromptControl
0xba8d  ldarg.0
0xba8e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xba93  ldarg.0
0xba94  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.DataSourceControl::m_pwdPromptControl
0xba99  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xba9e  ldarg.0
0xba9f  ldarg.0
0xbaa0  call     instance class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::CreateTextBox()
0xbaa5  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_userControl
0xbaaa  ldarg.0
0xbaab  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_userControl
0xbab0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xbab5  ldstr    aAutocomplete// "autocomplete"
0xbaba  ldstr    aOff// "off"
0xbabf  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbac4  ldarg.0
0xbac5  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_userControl
0xbaca  ldarg.0
0xbacb  ldftn    instance void Microsoft.Reporting.WebForms.DataSourceControl::OnChanged(object sender, class [mscorlib]System.EventArgs e)
0xbad1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xbad6  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::add_TextChanged(class [mscorlib]System.EventHandler)
0xbadb  ldarg.0
0xbadc  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbae1  ldarg.0
0xbae2  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_userControl
0xbae7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbaec  ldarg.0
0xbaed  ldarg.0
0xbaee  call     instance class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::CreateTextBox()
0xbaf3  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_pwdControl
0xbaf8  ldarg.0
0xbaf9  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_pwdControl
0xbafe  ldarg.0
0xbaff  ldftn    instance void Microsoft.Reporting.WebForms.DataSourceControl::OnChanged(object sender, class [mscorlib]System.EventArgs e)
0xbb05  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xbb0a  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::add_TextChanged(class [mscorlib]System.EventHandler)
0xbb0f  ldarg.0
0xbb10  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_pwdControl
0xbb15  ldc.i4.2
0xbb16  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_TextMode(valuetype [System.Web]System.Web.UI.WebControls.TextBoxMode)
0xbb1b  ldarg.0
0xbb1c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbb21  ldarg.0
0xbb22  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.DataSourceControl::m_pwdControl
0xbb27  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbb2c  ret
```
