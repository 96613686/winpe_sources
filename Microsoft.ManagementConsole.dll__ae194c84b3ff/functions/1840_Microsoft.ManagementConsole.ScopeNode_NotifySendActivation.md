# Microsoft.ManagementConsole.ScopeNode::NotifySendActivation

- ea: `0x1840`
- end: `0x186e`
- name: `Microsoft.ManagementConsole.ScopeNode::NotifySendActivation`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17c0`
- `0x17e0`

## callees

- `0x6f0`
- `0x1840`

## pseudocode

```c

```

## disassembly

```asm
0x1840  ldarg.0
0x1841  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x1846  ldnull
0x1847  ceq
0x1849  ldc.i4.0
0x184a  ceq
0x184c  stloc.0
0x184d  ldloc.0
0x184e  ldarg.0
0x184f  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1854  callvirt instance bool [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SendActivation()
0x1859  beq.s    loc_186D
0x185b  ldarg.0
0x185c  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1861  ldloc.0
0x1862  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SendActivation(bool)
0x1867  ldarg.0
0x1868  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x186d  ret
```
