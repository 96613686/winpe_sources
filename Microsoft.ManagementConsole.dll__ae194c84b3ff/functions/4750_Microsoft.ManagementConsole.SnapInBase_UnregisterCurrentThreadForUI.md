# Microsoft.ManagementConsole.SnapInBase::UnregisterCurrentThreadForUI

- ea: `0x4750`
- end: `0x475d`
- name: `Microsoft.ManagementConsole.SnapInBase::UnregisterCurrentThreadForUI`
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
0x4750  ldarg.0
0x4751  ldfld    class Microsoft.ManagementConsole.Internal.SnapInUIThreadTable Microsoft.ManagementConsole.SnapInBase::_uiThreadTable
0x4756  ldc.i4.0
0x4757  callvirt instance void Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterCurrentThread(bool register)
0x475c  ret
```
