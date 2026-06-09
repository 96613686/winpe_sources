# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::UnRegisterThreadWithUI

- ea: `0x1c0`
- end: `0x1d4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::UnRegisterThreadWithUI`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x1c6  brfalse.s loc_1D3
0x1c8  ldarg.0
0x1c9  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x1ce  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::UnregisterCurrentThreadForUI()
0x1d3  ret
```
