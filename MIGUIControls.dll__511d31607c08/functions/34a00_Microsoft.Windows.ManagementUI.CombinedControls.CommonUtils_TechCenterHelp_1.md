# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::TechCenterHelp_1

- ea: `0x34a00`
- end: `0x34bb6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::TechCenterHelp_1`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x12fe0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15020`
- `0x15110`
- `0x345d0`
- `0x34a00`

## string_xrefs

- `0x34a35`: `MicrosoftRedirectionProgramCommandLineParameters`
- `0x34a5b`: `http://go.microsoft.com/fwlink/events.asp`
- `0x34a73`: `http://go.microsoft.com/fwlink/events.asp`
- `0x34b26`: `OpenTechCenterLinkCustomProgramError`
- `0x34b87`: `OpenTechCenterLinkError`

## pseudocode

```c

```

## disassembly

```asm
0x34a00  ldnull
0x34a01  stloc.0
0x34a02  ldc.i4   0x80000002
0x34a07  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\Windows NT\\Curren"...
0x34a0c  ldstr    aMicrosoftredir// "MicrosoftRedirectionProgram"
0x34a11  ldstr    asc_AA3F4// ""
0x34a16  ldsfld   string [mscorlib]System.String::Empty
0x34a1b  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x34a20  stloc.0
0x34a21  ldnull
0x34a22  stloc.1
0x34a23  ldloc.0
0x34a24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34a29  brtrue.s loc_34A4A
0x34a2b  ldc.i4   0x80000002
0x34a30  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\Windows NT\\Curren"...
0x34a35  ldstr    aMicrosoftredir_0// "MicrosoftRedirectionProgramCommandLineP"...
0x34a3a  ldstr    asc_AA3F4// ""
0x34a3f  ldsfld   string [mscorlib]System.String::Empty
0x34a44  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x34a49  stloc.1
0x34a4a  ldnull
0x34a4b  stloc.2
0x34a4c  ldc.i4   0x80000002
0x34a51  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\Windows NT\\Curren"...
0x34a56  ldstr    aMicrosoftredir_1// "MicrosoftRedirectionURL"
0x34a5b  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/events.a"...
0x34a60  ldsfld   string [mscorlib]System.String::Empty
0x34a65  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x34a6a  stloc.2
0x34a6b  ldloc.2
0x34a6c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34a71  brfalse.s loc_34A79
0x34a73  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/events.a"...
0x34a78  stloc.2
0x34a79  ldloc.0
0x34a7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34a7f  brfalse.s loc_34A8D
0x34a81  ldloc.2
0x34a82  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(string)
0x34a87  pop
0x34a88  br       loc_34B57
0x34a8d  ldloc.1
0x34a8e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34a93  brtrue.s loc_34ACB
0x34a95  ldloc.1
0x34a96  ldstr    aS// "%s"
0x34a9b  ldc.i4.0
0x34a9c  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x34aa1  stloc.s  5
0x34aa3  ldloc.s  5
0x34aa5  ldc.i4.m1
0x34aa6  beq.s    loc_34ACB
0x34aa8  ldloc.1
0x34aa9  ldc.i4.0
0x34aaa  ldloc.s  5
0x34aac  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x34ab1  ldloc.2
0x34ab2  ldloc.1
0x34ab3  ldloc.s  5
0x34ab5  ldstr    aS// "%s"
0x34aba  call     instance int32 [mscorlib]System.String::get_Length()
0x34abf  add
0x34ac0  callvirt instance string [mscorlib]System.String::Substring(int32)
0x34ac5  call     string [mscorlib]System.String::Concat(string, string, string)
0x34aca  stloc.1
0x34acb  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x34ad0  stloc.3
0x34ad1  ldloc.3
0x34ad2  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x34ad7  ldloc.0
0x34ad8  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x34add  ldloc.1
0x34ade  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ae3  brtrue.s loc_34AF1
0x34ae5  ldloc.3
0x34ae6  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x34aeb  ldloc.1
0x34aec  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x34af1  ldc.i4.0
0x34af2  stloc.s  4
0x34af4  ldloc.3
0x34af5  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x34afa  pop
0x34afb  leave    loc_34BB5
0x34b00  pop
0x34b01  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x34b06  dup
0x34b07  ldc.i4.4
0x34b08  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x34b0d  dup
0x34b0e  ldc.i4.s 0x10
0x34b10  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x34b15  dup
0x34b16  ldstr    aViewername// "ViewerName"
0x34b1b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x34b20  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x34b25  dup
0x34b26  ldstr    aOpentechcenter// "OpenTechCenterLinkCustomProgramError"
0x34b2b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x34b30  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x34b35  dup
0x34b36  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x34b3b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x34b40  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x34b45  ldc.i4.6
0x34b46  ceq
0x34b48  stloc.s  4
0x34b4a  leave.s  loc_34B4C
0x34b4c  ldloc.s  4
0x34b4e  brfalse.s loc_34B57
0x34b50  ldloc.2
0x34b51  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(string)
0x34b56  pop
0x34b57  leave.s  loc_34BB5
0x34b59  stloc.s  6
0x34b5b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x34b60  dup
0x34b61  ldc.i4.0
0x34b62  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x34b67  dup
0x34b68  ldc.i4.s 0x10
0x34b6a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x34b6f  dup
0x34b70  ldc.i4.0
0x34b71  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x34b76  dup
0x34b77  ldstr    aViewername// "ViewerName"
0x34b7c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x34b81  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x34b86  dup
0x34b87  ldstr    aOpentechcenter_0// "OpenTechCenterLinkError"
0x34b8c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x34b91  ldloc.s  6
0x34b93  callvirt instance string [mscorlib]System.Exception::get_Message()
0x34b98  call     string [mscorlib]System.String::Concat(string, string)
0x34b9d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x34ba2  dup
0x34ba3  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x34ba8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x34bad  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x34bb2  pop
0x34bb3  leave.s  loc_34BB5
0x34bb5  ret
```
