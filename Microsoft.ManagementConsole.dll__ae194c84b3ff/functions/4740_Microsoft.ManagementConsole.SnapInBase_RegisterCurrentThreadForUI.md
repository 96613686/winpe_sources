# Microsoft.ManagementConsole.SnapInBase::RegisterCurrentThreadForUI

- ea: `0x4740`
- end: `0x474d`
- name: `Microsoft.ManagementConsole.SnapInBase::RegisterCurrentThreadForUI`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6880`

## pseudocode

```c

```

## disassembly

```asm
0x4740  ldarg.0
0x4741  ldfld    class Microsoft.ManagementConsole.Internal.SnapInUIThreadTable Microsoft.ManagementConsole.SnapInBase::_uiThreadTable
0x4746  ldc.i4.1
0x4747  callvirt instance void Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterCurrentThread(bool register)
0x474c  ret
```
