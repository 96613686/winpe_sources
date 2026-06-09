# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog_1

- ea: `0xd0`
- end: `0x194`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog_1`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xd0`
- `0xaa40`

## pseudocode

```c

```

## disassembly

```asm
0xd0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0xd5  stloc.0
0xd6  ldloc.0
0xd7  ldarg.1
0xd8  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Buttons()
0xdd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons)
0xe2  ldloc.0
0xe3  ldarg.1
0xe4  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Caption()
0xe9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0xee  ldloc.0
0xef  ldarg.1
0xf0  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_DefaultButton()
0xf5  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton)
0xfa  ldloc.0
0xfb  ldarg.1
0xfc  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_HelpFilePath()
0x101  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_HelpFilePath(string)
0x106  ldloc.0
0x107  ldarg.1
0x108  callvirt instance object [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_HelpTopicId()
0x10d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_HelpTopicId(object)
0x112  ldloc.0
0x113  ldarg.1
0x114  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Icon()
0x119  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x11e  ldloc.0
0x11f  ldarg.1
0x120  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.HelpNavigator [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Navigator()
0x125  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Navigator(valuetype [System.Windows.Forms]System.Windows.Forms.HelpNavigator)
0x12a  ldloc.0
0x12b  ldarg.1
0x12c  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Options()
0x131  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions)
0x136  ldloc.0
0x137  ldarg.1
0x138  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_ShowHelp()
0x13d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_ShowHelp(bool)
0x142  ldloc.0
0x143  ldarg.1
0x144  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::get_Text()
0x149  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x14e  ldarg.0
0x14f  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x154  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::get_InvokeRequired()
0x159  brfalse.s loc_187
0x15b  ldarg.0
0x15c  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x161  ldarg.0
0x162  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x167  ldftn    instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x16d  newobj   instance void ShowMessage::.ctor(object object, native int method)
0x172  ldc.i4.1
0x173  newarr   [mscorlib]System.Object
0x178  dup
0x179  ldc.i4.0
0x17a  ldloc.0
0x17b  stelem.ref
0x17c  callvirt instance object [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::Invoke(class [mscorlib]System.Delegate, object[])
0x181  unbox.any [System.Windows.Forms]System.Windows.Forms.DialogResult
0x186  ret
0x187  ldarg.0
0x188  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x18d  ldloc.0
0x18e  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x193  ret
```
