# Microsoft.ManagementConsole.ScopeNode::set_LanguageIndependentName

- ea: `0x1580`
- end: `0x15a1`
- name: `Microsoft.ManagementConsole.ScopeNode::set_LanguageIndependentName`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6f0`
- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldarg.1
0x1581  brtrue.s loc_158E
0x1583  ldstr    aValue// "value"
0x1588  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x158d  throw
0x158e  ldarg.0
0x158f  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1594  ldarg.1
0x1595  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_LanguageIndependentName(string)
0x159a  ldarg.0
0x159b  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x15a0  ret
```
