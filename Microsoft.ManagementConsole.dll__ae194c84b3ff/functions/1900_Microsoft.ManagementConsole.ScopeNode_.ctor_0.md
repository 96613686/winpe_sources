# Microsoft.ManagementConsole.ScopeNode::.ctor_0

- ea: `0x1900`
- end: `0x1913`
- name: `Microsoft.ManagementConsole.ScopeNode::.ctor_0`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1940`

## callees

- `0x18a0`

## pseudocode

```c

```

## disassembly

```asm
0x1900  ldarg.0
0x1901  call     instance void Microsoft.ManagementConsole.ScopeNode::.ctor()
0x1906  ldarg.0
0x1907  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x190c  ldarg.1
0x190d  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_NodeType(valuetype [mscorlib]System.Guid)
0x1912  ret
```
