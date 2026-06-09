# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextSubItems

- ea: `0x71a0`
- end: `0x71ad`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextSubItems`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6fb0`

## callees

- `0x870`
- `0x7130`

## pseudocode

```c

```

## disassembly

```asm
0x71a0  ldarg.0
0x71a1  ldarg.1
0x71a2  callvirt instance string Microsoft.ManagementConsole.Internal.NodeSubItemData::get_DisplayName()
0x71a7  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x71ac  ret
```
