# Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::.ctor_0

- ea: `0x85d30`
- end: `0x85ea7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::.ctor_0`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x85d20`

## callees

- `0x12090`
- `0x12ed0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15010`
- `0x15020`
- `0x15110`
- `0x5ea60`
- `0x85960`
- `0x85d30`
- `0x85eb0`
- `0x861f0`

## string_xrefs

- `0x85e2f`: `ApplicationTaskScheduler`

## pseudocode

```c

```

## disassembly

```asm
0x85d30  ldarg.0
0x85d31  newobj   instance void [mscorlib]System.Security.SecureString::.ctor()
0x85d36  stfld    class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::encryptedPassword
0x85d3b  ldarg.0
0x85d3c  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::.ctor()
0x85d41  ldarg.0
0x85d42  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::InitializeComponent()
0x85d47  ldarg.1
0x85d48  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x85d4d  brfalse.s loc_85D58
0x85d4f  ldarg.0
0x85d50  ldnull
0x85d51  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::compName
0x85d56  br.s     loc_85D5F
0x85d58  ldarg.0
0x85d59  ldarg.1
0x85d5a  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::compName
0x85d5f  ldarg.0
0x85d60  ldarg.1
0x85d61  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::GetDefaultApplicationUser(string computerName)
0x85d66  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x85d6b  ldarg.0
0x85d6c  ldarg.0
0x85d6d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x85d72  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x85d77  ldarg.0
0x85d78  ldarg.0
0x85d79  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x85d7e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_CancelButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x85d83  ldc.i4   0x111
0x85d88  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x85d8d  stloc.0
0x85d8e  ldarg.0
0x85d8f  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::compName
0x85d94  ldc.i4   0x111
0x85d99  ldloc.0
0x85d9a  call     unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::GetNetScheduleAccountInformation([hasfieldmarshal] string serverName, int32 count, [out] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder account)
0x85d9f  stloc.1
0x85da0  ldloc.0
0x85da1  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x85da6  brfalse.s loc_85DB4
0x85da8  ldarg.0
0x85da9  ldloc.0
0x85daa  callvirt instance string [mscorlib]System.Object::ToString()
0x85daf  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x85db4  ldarg.0
0x85db5  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x85dba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x85dbf  ldstr    aThisaccount// "ThisAccount"
0x85dc4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x85dc9  ldc.i4.1
0x85dca  newarr   [mscorlib]System.Object
0x85dcf  dup
0x85dd0  ldc.i4.0
0x85dd1  ldarg.0
0x85dd2  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x85dd7  stelem.ref
0x85dd8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x85ddd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x85de2  ldloc.1
0x85de3  brtrue.s loc_85DF6
0x85de5  ldarg.0
0x85de6  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x85deb  ldc.i4.1
0x85dec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x85df1  br       loc_85E95
0x85df6  ldloc.1
0x85df7  ldc.i4.1
0x85df8  bne.un.s loc_85E0B
0x85dfa  ldarg.0
0x85dfb  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x85e00  ldc.i4.1
0x85e01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x85e06  br       loc_85E95
0x85e0b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x85e10  stloc.2
0x85e11  ldloc.2
0x85e12  ldc.i4.0
0x85e13  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x85e18  ldloc.2
0x85e19  ldc.i4.s 0x10
0x85e1b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x85e20  ldloc.2
0x85e21  ldc.i4.0
0x85e22  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x85e27  ldloc.2
0x85e28  ldc.i4.0
0x85e29  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x85e2e  ldloc.2
0x85e2f  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x85e34  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x85e39  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x85e3e  ldloc.2
0x85e3f  ldnull
0x85e40  ldstr    aMessageunexpec// "MessageUnexpectedError"
0x85e45  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x85e4a  ldc.i4.2
0x85e4b  newarr   [mscorlib]System.Object
0x85e50  dup
0x85e51  ldc.i4.0
0x85e52  ldloc.1
0x85e53  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x85e58  callvirt instance string [mscorlib]System.Exception::get_Message()
0x85e5d  stelem.ref
0x85e5e  dup
0x85e5f  ldc.i4.1
0x85e60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x85e65  stelem.ref
0x85e66  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x85e6b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x85e70  ldloc.2
0x85e71  ldarg.0
0x85e72  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x85e77  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ParentWindow(class [System.Windows.Forms]System.Windows.Forms.IWin32Window value)
0x85e7c  ldloc.2
0x85e7d  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x85e82  pop
0x85e83  ldarg.0
0x85e84  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x85e89  ldc.i4.1
0x85e8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x85e8f  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceUnavailableException::.ctor()
0x85e94  throw
0x85e95  ldarg.0
0x85e96  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::EnableBrowseButton()
0x85e9b  ldarg.0
0x85e9c  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x85ea1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Refresh()
0x85ea6  ret
```
