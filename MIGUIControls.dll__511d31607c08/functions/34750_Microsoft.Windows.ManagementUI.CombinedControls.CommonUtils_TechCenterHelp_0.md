# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::TechCenterHelp_0

- ea: `0x34750`
- end: `0x34950`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::TechCenterHelp_0`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x345b0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x12fe0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15020`
- `0x15050`
- `0x15110`
- `0x24a40`
- `0x24b40`
- `0x24b80`
- `0x34630`
- `0x34750`
- `0x34950`
- `0x34ef0`

## string_xrefs

- `0x34799`: `CommonUtils.TechCenterHelp`
- `0x347b8`: `CommonUtils.TechCenterHelp`
- `0x347d7`: `CommonUtils.TechCenterHelp`
- `0x347f6`: `CommonUtils.TechCenterHelp`
- `0x347be`: `Help commandArgs: '{0}'`
- `0x348b9`: `OpenTechCenterLinkCustomProgramError`
- `0x34921`: `OpenTechCenterLinkError`

## pseudocode

```c

```

## disassembly

```asm
0x34750  call     bool Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::ShouldPopup()
0x34755  brfalse.s loc_34786
0x34757  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::confirmDlg
0x3475c  brtrue.s loc_34768
0x3475e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::.ctor()
0x34763  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::confirmDlg
0x34768  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::confirmDlg
0x3476d  ldarg.0
0x3476e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::LoadEventInfo(class Microsoft.Windows.ManagementUI.CombinedControls.EventInfoToSend[] eventInfo)
0x34773  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x34778  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::confirmDlg
0x3477d  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x34782  ldc.i4.6
0x34783  beq.s    loc_34786
0x34785  ret
0x34786  ldloca.s 0
0x34788  ldloca.s 1
0x3478a  ldarga.s 2
0x3478c  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::DetermineTechCenterHelpSource([out] string& helpProgram, [out] string& commandArgs, string& baseUrl)
0x34791  ldarg.0
0x34792  ldarg.2
0x34793  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::CalcUrl(class Microsoft.Windows.ManagementUI.CombinedControls.EventInfoToSend[] eventInfoToSend, string baseUrl)
0x34798  stloc.2
0x34799  ldstr    aCommonutilsTec// "CommonUtils.TechCenterHelp"
0x3479e  ldnull
0x3479f  ldstr    aHelpProgram0// "Help program: '{0}'"
0x347a4  ldc.i4.1
0x347a5  newarr   [mscorlib]System.Object
0x347aa  dup
0x347ab  ldc.i4.0
0x347ac  ldloc.0
0x347ad  stelem.ref
0x347ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x347b3  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x347b8  ldstr    aCommonutilsTec// "CommonUtils.TechCenterHelp"
0x347bd  ldnull
0x347be  ldstr    aHelpCommandarg// "Help commandArgs: '{0}'"
0x347c3  ldc.i4.1
0x347c4  newarr   [mscorlib]System.Object
0x347c9  dup
0x347ca  ldc.i4.0
0x347cb  ldloc.1
0x347cc  stelem.ref
0x347cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x347d2  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x347d7  ldstr    aCommonutilsTec// "CommonUtils.TechCenterHelp"
0x347dc  ldnull
0x347dd  ldstr    aHelpBaseurl0// "Help baseUrl: '{0}'"
0x347e2  ldc.i4.1
0x347e3  newarr   [mscorlib]System.Object
0x347e8  dup
0x347e9  ldc.i4.0
0x347ea  ldarg.2
0x347eb  stelem.ref
0x347ec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x347f1  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x347f6  ldstr    aCommonutilsTec// "CommonUtils.TechCenterHelp"
0x347fb  ldnull
0x347fc  ldstr    aHelpUrl0// "Help url: '{0}'"
0x34801  ldc.i4.1
0x34802  newarr   [mscorlib]System.Object
0x34807  dup
0x34808  ldc.i4.0
0x34809  ldloc.2
0x3480a  stelem.ref
0x3480b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x34810  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x34815  ldloc.0
0x34816  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3481b  brtrue   loc_348EB
0x34820  ldloc.1
0x34821  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34826  brtrue.s loc_3485E
0x34828  ldloc.1
0x34829  ldstr    aS// "%s"
0x3482e  ldc.i4.0
0x3482f  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x34834  stloc.s  5
0x34836  ldloc.s  5
0x34838  ldc.i4.m1
0x34839  beq.s    loc_3485E
0x3483b  ldloc.1
0x3483c  ldc.i4.0
0x3483d  ldloc.s  5
0x3483f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x34844  ldloc.2
0x34845  ldloc.1
0x34846  ldloc.s  5
0x34848  ldstr    aS// "%s"
0x3484d  call     instance int32 [mscorlib]System.String::get_Length()
0x34852  add
0x34853  callvirt instance string [mscorlib]System.String::Substring(int32)
0x34858  call     string [mscorlib]System.String::Concat(string, string, string)
0x3485d  stloc.1
0x3485e  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x34863  stloc.3
0x34864  ldloc.3
0x34865  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x3486a  ldloc.0
0x3486b  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x34870  ldloc.1
0x34871  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34876  brtrue.s loc_34884
0x34878  ldloc.3
0x34879  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x3487e  ldloc.1
0x3487f  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x34884  ldc.i4.0
0x34885  stloc.s  4
0x34887  ldloc.3
0x34888  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x3488d  pop
0x3488e  leave    loc_3494F
0x34893  pop
0x34894  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x34899  dup
0x3489a  ldc.i4.4
0x3489b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x348a0  dup
0x348a1  ldc.i4.s 0x10
0x348a3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x348a8  dup
0x348a9  ldstr    aViewername// "ViewerName"
0x348ae  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x348b3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x348b8  dup
0x348b9  ldstr    aOpentechcenter// "OpenTechCenterLinkCustomProgramError"
0x348be  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x348c3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x348c8  dup
0x348c9  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x348ce  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x348d3  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x348d8  ldc.i4.6
0x348d9  ceq
0x348db  stloc.s  4
0x348dd  leave.s  loc_348DF
0x348df  ldloc.s  4
0x348e1  brfalse.s loc_348F1
0x348e3  ldloc.2
0x348e4  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::LaunchWebBrowserAsLua(string url)
0x348e9  br.s     loc_348F1
0x348eb  ldloc.2
0x348ec  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::LaunchWebBrowserAsLua(string url)
0x348f1  leave.s  loc_3494F
0x348f3  stloc.s  6
0x348f5  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x348fa  dup
0x348fb  ldc.i4.0
0x348fc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x34901  dup
0x34902  ldc.i4.s 0x10
0x34904  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x34909  dup
0x3490a  ldc.i4.0
0x3490b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x34910  dup
0x34911  ldstr    aViewername// "ViewerName"
0x34916  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3491b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x34920  dup
0x34921  ldstr    aOpentechcenter_0// "OpenTechCenterLinkError"
0x34926  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3492b  ldloc.s  6
0x3492d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x34932  call     string [mscorlib]System.String::Concat(string, string)
0x34937  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x3493c  dup
0x3493d  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x34942  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x34947  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x3494c  pop
0x3494d  leave.s  loc_3494F
0x3494f  ret
```
