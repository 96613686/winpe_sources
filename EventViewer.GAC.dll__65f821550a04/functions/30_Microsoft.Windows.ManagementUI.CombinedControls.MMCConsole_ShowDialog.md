# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog

- ea: `0x30`
- end: `0x76`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x30`
- `0xa9a0`

## pseudocode

```c

```

## disassembly

```asm
0x30  ldarg.0
0x31  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x36  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::get_InvokeRequired()
0x3b  brfalse.s loc_69
0x3d  ldarg.0
0x3e  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x43  ldarg.0
0x44  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x49  ldftn    instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.CommonDialog)
0x4f  newobj   instance void ShowCommonDialog::.ctor(object object, native int method)
0x54  ldc.i4.1
0x55  newarr   [mscorlib]System.Object
0x5a  dup
0x5b  ldc.i4.0
0x5c  ldarg.1
0x5d  stelem.ref
0x5e  callvirt instance object [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::Invoke(class [mscorlib]System.Delegate, object[])
0x63  unbox.any [System.Windows.Forms]System.Windows.Forms.DialogResult
0x68  ret
0x69  ldarg.0
0x6a  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x6f  ldarg.1
0x70  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.CommonDialog)
0x75  ret
```
