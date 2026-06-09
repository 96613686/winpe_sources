# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::RegisterThreadWithUI

- ea: `0x1a0`
- end: `0x1b4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::RegisterThreadWithUI`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.0
0x1a1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x1a6  brfalse.s loc_1B3
0x1a8  ldarg.0
0x1a9  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x1ae  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::RegisterCurrentThreadForUI()
0x1b3  ret
```
