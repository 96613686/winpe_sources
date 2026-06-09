# Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo

- ea: `0x9f0`
- end: `0xa0a`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5970`
- `0x6fb0`

## callees

- `0x9f0`
- `0xef0`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldarg.0
0x9f1  ldfld    class Microsoft.ManagementConsole.Internal.PasteTargetInfo Microsoft.ManagementConsole.Internal.ScopeNodeData::_pasteTargetInfo
0x9f6  brtrue.s loc_A03
0x9f8  ldarg.0
0x9f9  newobj   instance void Microsoft.ManagementConsole.Internal.PasteTargetInfo::.ctor()
0x9fe  stfld    class Microsoft.ManagementConsole.Internal.PasteTargetInfo Microsoft.ManagementConsole.Internal.ScopeNodeData::_pasteTargetInfo
0xa03  ldarg.0
0xa04  ldfld    class Microsoft.ManagementConsole.Internal.PasteTargetInfo Microsoft.ManagementConsole.Internal.ScopeNodeData::_pasteTargetInfo
0xa09  ret
```
