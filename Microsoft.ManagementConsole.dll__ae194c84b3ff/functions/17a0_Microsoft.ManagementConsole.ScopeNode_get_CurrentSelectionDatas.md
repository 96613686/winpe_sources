# Microsoft.ManagementConsole.ScopeNode::get_CurrentSelectionDatas

- ea: `0x17a0`
- end: `0x17ba`
- name: `Microsoft.ManagementConsole.ScopeNode::get_CurrentSelectionDatas`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9d20`
- `0xd950`
- `0xda50`

## callees

- `0x17a0`
- `0xdd00`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldarg.0
0x17a1  ldfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.ScopeNode::_currentSelectionDatas
0x17a6  brtrue.s loc_17B3
0x17a8  ldarg.0
0x17a9  newobj   instance void Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::.ctor()
0x17ae  stfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.ScopeNode::_currentSelectionDatas
0x17b3  ldarg.0
0x17b4  ldfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.ScopeNode::_currentSelectionDatas
0x17b9  ret
```
