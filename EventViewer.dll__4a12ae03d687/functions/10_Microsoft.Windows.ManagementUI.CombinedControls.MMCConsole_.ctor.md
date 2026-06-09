# Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::.ctor

- ea: `0x10`
- end: `0x25`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::.ctor`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x430`
- `0x1340`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  call     instance void [mscorlib]System.Object::.ctor()
0x16  ldarg.0
0x17  ldarg.1
0x18  stfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::mmcConsole
0x1d  ldarg.0
0x1e  ldarg.2
0x1f  stfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::snapinBase
0x24  ret
```
