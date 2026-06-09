# Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetSaveLogFileName_0

- ea: `0x358b0`
- end: `0x35a53`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetSaveLogFileName_0`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x20ee0`
- `0x358a0`
- `0x35aa0`
- `0x35ab0`
- `0x48070`

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
- `0x15040`
- `0x15050`
- `0x15110`
- `0x17240`
- `0x1f040`
- `0x33aa0`
- `0x358b0`
- `0x35a60`
- `0x38880`
- `0x38890`

## string_xrefs

- `0x358fc`: `EventFilesSaveExtension`
- `0x35908`: `EventFilesSaveExtensionNoElf`

## pseudocode

```c

```

## disassembly

```asm
0x358b0  ldc.i4.6
0x358b1  stloc.0
0x358b2  ldarg.1
0x358b3  ldnull
0x358b4  stind.ref
0x358b5  ldc.i4.0
0x358b6  stloc.1
0x358b7  ldc.i4.0
0x358b8  stloc.2
0x358b9  br       loc_35A4B
0x358be  ldc.i4.1
0x358bf  stloc.2
0x358c0  ldarg.0
0x358c1  brfalse.s loc_358E7
0x358c3  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ClearLogConfirmationForm::.ctor()
0x358c8  stloc.3
0x358c9  ldarg.2
0x358ca  brfalse.s loc_358DA
0x358cc  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x358d1  ldloc.3
0x358d2  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x358d7  stloc.0
0x358d8  br.s     loc_358E1
0x358da  ldloc.3
0x358db  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.Form::ShowDialog()
0x358e0  stloc.0
0x358e1  ldloc.0
0x358e2  ldc.i4.2
0x358e3  beq.s    loc_358E7
0x358e5  ldc.i4.1
0x358e6  stloc.1
0x358e7  ldloc.0
0x358e8  ldc.i4.6
0x358e9  bne.un   loc_35A4B
0x358ee  ldc.i4.0
0x358ef  stloc.1
0x358f0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.SaveFileDialog::.ctor()
0x358f5  stloc.s  4
0x358f7  ldloc.s  4
0x358f9  ldarg.3
0x358fa  brtrue.s loc_35908
0x358fc  ldstr    aEventfilessave// "EventFilesSaveExtension"
0x35901  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35906  br.s     loc_35912
0x35908  ldstr    aEventfilessave_0// "EventFilesSaveExtensionNoElf"
0x3590d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35912  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x35917  ldloc.s  4
0x35919  ldc.i4.1
0x3591a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x3591f  ldloc.s  4
0x35921  ldc.i4.1
0x35922  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x35927  ldloc.s  4
0x35929  ldstr    aEvtx// "evtx"
0x3592e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_DefaultExt(string)
0x35933  ldloc.s  4
0x35935  call     string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_CurrentDirectory()
0x3593a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x3593f  ldarg.2
0x35940  brfalse.s loc_35951
0x35942  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x35947  ldloc.s  4
0x35949  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.CommonDialog dlg)
0x3594e  stloc.0
0x3594f  br.s     loc_35959
0x35951  ldloc.s  4
0x35953  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x35958  stloc.0
0x35959  ldc.i4.1
0x3595a  ldloc.0
0x3595b  bne.un   loc_35A4B
0x35960  ldarg.1
0x35961  ldloc.s  4
0x35963  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35968  stind.ref
0x35969  ldarg.1
0x3596a  ldind.ref
0x3596b  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::IsValidExportFileName(string fileName)
0x35970  brfalse.s loc_359E7
0x35972  ldarg.s  4
0x35974  brfalse.s loc_3598E
0x35976  ldarg.1
0x35977  ldind.ref
0x35978  ldstr    aEvtx_0// ".evtx"
0x3597d  ldc.i4.5
0x3597e  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x35983  brfalse.s loc_3598E
0x35985  ldarg.1
0x35986  ldarg.1
0x35987  ldind.ref
0x35988  call     string Microsoft.Windows.ManagementUI.CombinedControls.ShareUtil::ConvertToUnc(string path)
0x3598d  stind.ref
0x3598e  ldloc.s  4
0x35990  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35995  ldc.i4.0
0x35996  ldloc.s  4
0x35998  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x3599d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x359a2  ldloc.s  4
0x359a4  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x359a9  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x359ae  callvirt instance int32 [mscorlib]System.String::get_Length()
0x359b3  sub
0x359b4  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x359b9  call     void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_CurrentDirectory(string value)
0x359be  ldc.i4.1
0x359bf  stloc.1
0x359c0  ldarg.1
0x359c1  ldind.ref
0x359c2  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x359c7  stloc.s  5
0x359c9  ldloc.s  5
0x359cb  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x359d0  brfalse.s loc_359D9
0x359d2  ldloc.s  5
0x359d4  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x359d9  leave.s  loc_35A4B
0x359db  pop
0x359dc  leave.s  loc_35A4B
0x359de  pop
0x359df  leave.s  loc_35A4B
0x359e1  pop
0x359e2  leave.s  loc_35A4B
0x359e4  pop
0x359e5  leave.s  loc_35A4B
0x359e7  ldc.i4.0
0x359e8  stloc.2
0x359e9  ldc.i4.6
0x359ea  stloc.0
0x359eb  ldarg.2
0x359ec  brfalse.s loc_359FF
0x359ee  ldstr    aInvalidfilenam// "InvalidFileName"
0x359f3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x359f8  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x359fd  br.s     loc_35A4B
0x359ff  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x35a04  dup
0x35a05  ldc.i4.0
0x35a06  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x35a0b  dup
0x35a0c  ldc.i4.s 0x10
0x35a0e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x35a13  dup
0x35a14  ldc.i4.0
0x35a15  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x35a1a  dup
0x35a1b  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x35a20  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x35a25  dup
0x35a26  ldstr    aViewername// "ViewerName"
0x35a2b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35a30  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x35a35  dup
0x35a36  ldstr    aInvalidfilenam// "InvalidFileName"
0x35a3b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35a40  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x35a45  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x35a4a  stloc.0
0x35a4b  ldloc.2
0x35a4c  brfalse  loc_358BE
0x35a51  ldloc.1
0x35a52  ret
```
