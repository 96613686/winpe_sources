# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog_0

- ea: `0x80`
- end: `0xc6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::ShowDialog_0`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x80`
- `0xa9f0`

## pseudocode

```c

```

## disassembly

```asm
0x80  ldarg.0
0x81  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x86  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::get_InvokeRequired()
0x8b  brfalse.s loc_B9
0x8d  ldarg.0
0x8e  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x93  ldarg.0
0x94  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x99  ldftn    instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form)
0x9f  newobj   instance void ShowForm::.ctor(object object, native int method)
0xa4  ldc.i4.1
0xa5  newarr   [mscorlib]System.Object
0xaa  dup
0xab  ldc.i4.0
0xac  ldarg.1
0xad  stelem.ref
0xae  callvirt instance object [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::Invoke(class [mscorlib]System.Delegate, object[])
0xb3  unbox.any [System.Windows.Forms]System.Windows.Forms.DialogResult
0xb8  ret
0xb9  ldarg.0
0xba  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0xbf  ldarg.1
0xc0  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form)
0xc5  ret
```
