# Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton_Click

- ea: `0x85fd0`
- end: `0x86157`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton_Click`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12080`
- `0x12ed0`
- `0x85fd0`
- `0x86160`

## string_xrefs

- `0x860ce`: `ERROR_ACCESS_DENIED`
- `0x860e7`: `SCHED_E_SERVICE_NOT_RUNNING`
- `0x86100`: `MessageATTaskInvalidPassword`
- `0x86112`: `AtServiceAccountUnknownError`

## pseudocode

```c

```

## disassembly

```asm
0x85fd0  ldc.i4.0
0x85fd1  stloc.0
0x85fd2  ldarg.0
0x85fd3  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x85fd8  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.RadioButton::get_Checked()
0x85fdd  brfalse.s loc_85FF3
0x85fdf  ldarg.0
0x85fe0  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::compName
0x85fe5  ldnull
0x85fe6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85feb  call     unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetNetScheduleAccountInformation([hasfieldmarshal] string serverName, [hasfieldmarshal] string account, native int password)
0x85ff0  stloc.0
0x85ff1  br.s     loc_86059
0x85ff3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85ff8  stloc.1
0x85ff9  ldarg.0
0x85ffa  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x85fff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86004  brtrue.s loc_86025
0x86006  ldarg.0
0x86007  ldfld    class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::encryptedPassword
0x8600c  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToGlobalAllocUnicode(class [mscorlib]System.Security.SecureString)
0x86011  stloc.1
0x86012  ldarg.0
0x86013  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::compName
0x86018  ldarg.0
0x86019  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x8601e  ldloc.1
0x8601f  call     unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetNetScheduleAccountInformation([hasfieldmarshal] string serverName, [hasfieldmarshal] string account, native int password)
0x86024  stloc.0
0x86025  leave.s  loc_8603B
0x86027  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8602c  ldloc.1
0x8602d  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x86032  brfalse.s loc_8603A
0x86034  ldloc.1
0x86035  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeGlobalAllocUnicode(native int)
0x8603a  endfinally
0x8603b  ldarg.0
0x8603c  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::account
0x86041  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86046  brfalse.s loc_86059
0x86048  ldarg.0
0x86049  ldstr    aAccountnamemis// "AccountNameMissing"
0x8604e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x86053  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x86058  ret
0x86059  ldloc.0
0x8605a  brfalse  loc_8614F
0x8605f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x86064  ldstr    a00x1X// "{0}0x{1:X}"
0x86069  ldc.i4.2
0x8606a  newarr   [mscorlib]System.Object
0x8606f  dup
0x86070  ldc.i4.0
0x86071  ldstr    aSetnetschedule// "SetNetScheduleAccountInformationErrorNu"...
0x86076  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8607b  stelem.ref
0x8607c  dup
0x8607d  ldc.i4.1
0x8607e  ldloc.0
0x8607f  box      [mscorlib]System.UInt32
0x86084  stelem.ref
0x86085  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8608a  stloc.2
0x8608b  ldloc.0
0x8608c  ldc.i4   0x80041310
0x86091  beq.s    loc_8609B
0x86093  ldloc.0
0x86094  ldc.i4   0x80070534
0x86099  bne.un.s loc_860AC
0x8609b  ldarg.0
0x8609c  ldstr    aSchedEAccountN// "SCHED_E_ACCOUNT_NAME_NOT_FOUND"
0x860a1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x860a6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x860ab  ret
0x860ac  ldloc.0
0x860ad  ldc.i4   0x80041311
0x860b2  bne.un.s loc_860C5
0x860b4  ldarg.0
0x860b5  ldstr    aSchedEAccountD// "SCHED_E_ACCOUNT_DBASE_CORRUPT"
0x860ba  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x860bf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x860c4  ret
0x860c5  ldloc.0
0x860c6  ldc.i4   0x80070005
0x860cb  bne.un.s loc_860DE
0x860cd  ldarg.0
0x860ce  ldstr    aErrorAccessDen// "ERROR_ACCESS_DENIED"
0x860d3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x860d8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x860dd  ret
0x860de  ldloc.0
0x860df  ldc.i4   0x80041315
0x860e4  bne.un.s loc_860F7
0x860e6  ldarg.0
0x860e7  ldstr    aSchedEServiceN// "SCHED_E_SERVICE_NOT_RUNNING"
0x860ec  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x860f1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x860f6  ret
0x860f7  ldloc.0
0x860f8  ldc.i4   0x8007052E
0x860fd  bne.un.s loc_86110
0x860ff  ldarg.0
0x86100  ldstr    aMessageattaski// "MessageATTaskInvalidPassword"
0x86105  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8610a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x8610f  ret
0x86110  ldarg.0
0x86111  ldnull
0x86112  ldstr    aAtserviceaccou// "AtServiceAccountUnknownError"
0x86117  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8611c  ldc.i4.1
0x8611d  newarr   [mscorlib]System.Object
0x86122  dup
0x86123  ldc.i4.0
0x86124  ldloc.2
0x86125  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8612a  ldtoken  [mscorlib]System.UInt32
0x8612f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86134  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x86139  castclass [mscorlib]System.IFormatProvider
0x8613e  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x86143  stelem.ref
0x86144  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x86149  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::ShowMessageBox(string errorMsg)
0x8614e  ret
0x8614f  ldarg.0
0x86150  ldc.i4.1
0x86151  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x86156  ret
```
