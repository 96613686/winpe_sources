# Microsoft.ManagementConsole.ScopeNode::set_HelpTopic

- ea: `0x14b0`
- end: `0x14d6`
- name: `Microsoft.ManagementConsole.ScopeNode::set_HelpTopic`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6f0`
- `0x14b0`

## pseudocode

```c

```

## disassembly

```asm
0x14b0  ldarg.1
0x14b1  ldarg.0
0x14b2  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x14b7  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_HelpTopic()
0x14bc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x14c1  brfalse.s loc_14D5
0x14c3  ldarg.0
0x14c4  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x14c9  ldarg.1
0x14ca  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_HelpTopic(string)
0x14cf  ldarg.0
0x14d0  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x14d5  ret
```
