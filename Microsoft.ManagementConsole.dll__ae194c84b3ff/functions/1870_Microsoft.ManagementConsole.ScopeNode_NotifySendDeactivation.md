# Microsoft.ManagementConsole.ScopeNode::NotifySendDeactivation

- ea: `0x1870`
- end: `0x189e`
- name: `Microsoft.ManagementConsole.ScopeNode::NotifySendDeactivation`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800`
- `0x1820`

## callees

- `0x6f0`
- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1870  ldarg.0
0x1871  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x1876  ldnull
0x1877  ceq
0x1879  ldc.i4.0
0x187a  ceq
0x187c  stloc.0
0x187d  ldloc.0
0x187e  ldarg.0
0x187f  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1884  callvirt instance bool [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SendDeactivation()
0x1889  beq.s    loc_189D
0x188b  ldarg.0
0x188c  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1891  ldloc.0
0x1892  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SendDeactivation(bool)
0x1897  ldarg.0
0x1898  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x189d  ret
```
