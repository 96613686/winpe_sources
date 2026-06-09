# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery_Click

- ea: `0x5a2f0`
- end: `0x5a42c`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery_Click`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

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
- `0x5a2f0`
- `0x9aac0`

## string_xrefs

- `0x5a3fb`: `QueryEditRollBackMesg`

## pseudocode

```c

```

## disassembly

```asm
0x5a2f0  ldarg.0
0x5a2f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery
0x5a2f6  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x5a2fb  brtrue.s loc_5A365
0x5a2fd  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x5a302  stloc.0
0x5a303  ldloc.0
0x5a304  ldc.i4.4
0x5a305  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x5a30a  ldloc.0
0x5a30b  ldc.i4.s 0x30
0x5a30d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x5a312  ldloc.0
0x5a313  ldc.i4.0
0x5a314  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x5a319  ldloc.0
0x5a31a  ldc.i4.0
0x5a31b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x5a320  ldloc.0
0x5a321  ldstr    aViewername// "ViewerName"
0x5a326  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5a32b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x5a330  ldloc.0
0x5a331  ldstr    aManualqueryedi// "ManualQueryEditWarningMesg"
0x5a336  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5a33b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x5a340  ldloc.0
0x5a341  ldarg.0
0x5a342  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x5a347  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ParentWindow(class [System.Windows.Forms]System.Windows.Forms.IWin32Window value)
0x5a34c  ldc.i4.6
0x5a34d  ldloc.0
0x5a34e  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x5a353  bne.un   loc_5A42B
0x5a358  ldarg.0
0x5a359  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery
0x5a35e  ldc.i4.1
0x5a35f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x5a364  ret
0x5a365  ldarg.0
0x5a366  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::disallowManualRollBack
0x5a36b  brfalse.s loc_5A3BF
0x5a36d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x5a372  stloc.0
0x5a373  ldloc.0
0x5a374  ldc.i4.0
0x5a375  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x5a37a  ldloc.0
0x5a37b  ldc.i4.s 0x10
0x5a37d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x5a382  ldloc.0
0x5a383  ldc.i4.0
0x5a384  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x5a389  ldloc.0
0x5a38a  ldc.i4.0
0x5a38b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x5a390  ldloc.0
0x5a391  ldstr    aViewername// "ViewerName"
0x5a396  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5a39b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x5a3a0  ldloc.0
0x5a3a1  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_QueryRollBackDisallowed()
0x5a3a6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x5a3ab  ldloc.0
0x5a3ac  ldarg.0
0x5a3ad  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x5a3b2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ParentWindow(class [System.Windows.Forms]System.Windows.Forms.IWin32Window value)
0x5a3b7  ldloc.0
0x5a3b8  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x5a3bd  pop
0x5a3be  ret
0x5a3bf  ldarg.0
0x5a3c0  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x5a3c5  brfalse.s loc_5A42B
0x5a3c7  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x5a3cc  stloc.0
0x5a3cd  ldloc.0
0x5a3ce  ldc.i4.4
0x5a3cf  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x5a3d4  ldloc.0
0x5a3d5  ldc.i4.s 0x30
0x5a3d7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x5a3dc  ldloc.0
0x5a3dd  ldc.i4.0
0x5a3de  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x5a3e3  ldloc.0
0x5a3e4  ldc.i4.0
0x5a3e5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x5a3ea  ldloc.0
0x5a3eb  ldstr    aViewername// "ViewerName"
0x5a3f0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5a3f5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x5a3fa  ldloc.0
0x5a3fb  ldstr    aQueryeditrollb// "QueryEditRollBackMesg"
0x5a400  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5a405  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x5a40a  ldloc.0
0x5a40b  ldarg.0
0x5a40c  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x5a411  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ParentWindow(class [System.Windows.Forms]System.Windows.Forms.IWin32Window value)
0x5a416  ldc.i4.6
0x5a417  ldloc.0
0x5a418  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x5a41d  bne.un.s loc_5A42B
0x5a41f  ldarg.0
0x5a420  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery
0x5a425  ldc.i4.0
0x5a426  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x5a42b  ret
```
