# Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::get_SyncRoot

- ea: `0x68f0`
- end: `0x68f7`
- name: `Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::get_SyncRoot`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x6810`
- `0x6880`

## pseudocode

```c

```

## disassembly

```asm
0x68f0  ldarg.0
0x68f1  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x68f6  ret
```
