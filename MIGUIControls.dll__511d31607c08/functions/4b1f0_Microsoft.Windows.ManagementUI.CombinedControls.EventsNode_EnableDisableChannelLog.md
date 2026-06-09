# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::EnableDisableChannelLog

- ea: `0x4b1f0`
- end: `0x4b30b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::EnableDisableChannelLog`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x481a0`
- `0x68640`

## callees

- `0x11f50`
- `0x12ed0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15020`
- `0x15110`
- `0x4b1f0`
- `0x4ea30`
- `0x4ea60`
- `0x4f1a0`
- `0x4f250`

## string_xrefs

- `0x4b21e`: `EventsNode : Ignoring InvalidOperationOverEnabledDirectChannel from Crimson during EvtSaveChannelConfig.`

## pseudocode

```c

```

## disassembly

```asm
0x4b1f0  ldc.i4.0
0x4b1f1  stloc.0
0x4b1f2  ldarg.0
0x4b1f3  ldarg.0
0x4b1f4  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_LogEnabled()
0x4b1f9  ldc.i4.0
0x4b1fa  ceq
0x4b1fc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::set_LogEnabled(bool value)
0x4b201  ldarg.0
0x4b202  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::Save()
0x4b207  stloc.1
0x4b208  ldloc.1
0x4b209  brtrue.s loc_4B216
0x4b20b  ldc.i4.1
0x4b20c  stloc.0
0x4b20d  ldarg.0
0x4b20e  ldc.i4.1
0x4b20f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_NeedsRefresh(bool value)
0x4b214  br.s     loc_4B274
0x4b216  ldloc.1
0x4b217  ldc.i4   0x3AAE
0x4b21c  bne.un.s loc_4B22C
0x4b21e  ldstr    aEventsnodeIgno// "EventsNode : Ignoring InvalidOperationO"...
0x4b223  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x4b228  ldc.i4.1
0x4b229  stloc.0
0x4b22a  br.s     loc_4B274
0x4b22c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x4b231  dup
0x4b232  ldc.i4.0
0x4b233  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x4b238  dup
0x4b239  ldc.i4.s 0x30
0x4b23b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x4b240  dup
0x4b241  ldc.i4.0
0x4b242  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x4b247  dup
0x4b248  ldc.i4.0
0x4b249  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x4b24e  dup
0x4b24f  ldstr    aViewername// "ViewerName"
0x4b254  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4b259  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x4b25e  ldloc.1
0x4b25f  ldloca.s 2
0x4b261  call     unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::FormatMessage(unsigned int32 lastError, [out] string& msg)
0x4b266  pop
0x4b267  dup
0x4b268  ldloc.2
0x4b269  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x4b26e  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x4b273  pop
0x4b274  leave    loc_4B309
0x4b279  stloc.3
0x4b27a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x4b27f  dup
0x4b280  ldc.i4.0
0x4b281  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x4b286  dup
0x4b287  ldc.i4.s 0x30
0x4b289  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x4b28e  dup
0x4b28f  ldc.i4.0
0x4b290  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x4b295  dup
0x4b296  ldc.i4.0
0x4b297  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x4b29c  dup
0x4b29d  ldstr    aViewername// "ViewerName"
0x4b2a2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4b2a7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x4b2ac  dup
0x4b2ad  ldloc.3
0x4b2ae  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4b2b3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x4b2b8  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x4b2bd  pop
0x4b2be  leave.s  loc_4B309
0x4b2c0  stloc.s  4
0x4b2c2  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x4b2c7  dup
0x4b2c8  ldc.i4.0
0x4b2c9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x4b2ce  dup
0x4b2cf  ldc.i4.s 0x30
0x4b2d1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x4b2d6  dup
0x4b2d7  ldc.i4.0
0x4b2d8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x4b2dd  dup
0x4b2de  ldc.i4.0
0x4b2df  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x4b2e4  dup
0x4b2e5  ldstr    aViewername// "ViewerName"
0x4b2ea  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4b2ef  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x4b2f4  dup
0x4b2f5  ldloc.s  4
0x4b2f7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4b2fc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x4b301  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x4b306  pop
0x4b307  leave.s  loc_4B309
0x4b309  ldloc.0
0x4b30a  ret
```
