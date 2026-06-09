# Microsoft.ManagementConsole.ScopeNode::get_HelpTopic

- ea: `0x1490`
- end: `0x14af`
- name: `Microsoft.ManagementConsole.ScopeNode::get_HelpTopic`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1490`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldarg.0
0x1491  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1496  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_HelpTopic()
0x149b  brfalse.s loc_14A9
0x149d  ldarg.0
0x149e  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x14a3  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_HelpTopic()
0x14a8  ret
0x14a9  ldsfld   string [mscorlib]System.String::Empty
0x14ae  ret
```
