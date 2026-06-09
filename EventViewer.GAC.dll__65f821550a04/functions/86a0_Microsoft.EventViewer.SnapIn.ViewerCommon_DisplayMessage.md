# Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayMessage

- ea: `0x86a0`
- end: `0x86cb`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayMessage`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5560`
- `0x8690`

## pseudocode

```c

```

## disassembly

```asm
0x86a0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x86a5  stloc.0
0x86a6  ldloc.0
0x86a7  ldarg.0
0x86a8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x86ad  ldloc.0
0x86ae  ldarg.1
0x86af  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x86b4  ldloc.0
0x86b5  ldc.i4.0
0x86b6  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons)
0x86bb  ldloc.0
0x86bc  ldarg.2
0x86bd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x86c2  ldarg.3
0x86c3  ldloc.0
0x86c4  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x86c9  pop
0x86ca  ret
```
