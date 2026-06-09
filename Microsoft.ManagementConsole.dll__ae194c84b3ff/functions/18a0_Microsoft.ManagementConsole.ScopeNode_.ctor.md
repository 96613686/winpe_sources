# Microsoft.ManagementConsole.ScopeNode::.ctor

- ea: `0x18a0`
- end: `0x18fe`
- name: `Microsoft.ManagementConsole.ScopeNode::.ctor`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1900`
- `0x1920`

## callees

- `0x6e0`
- `0x710`
- `0x18a0`
- `0x38b0`

## pseudocode

```c

```

## disassembly

```asm
0x18a0  ldarg.0
0x18a1  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::.ctor()
0x18a6  stfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x18ab  ldarg.0
0x18ac  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus>::.ctor()
0x18b1  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus> Microsoft.ManagementConsole.ScopeNode::_customStatusList
0x18b6  ldarg.0
0x18b7  call     instance void Microsoft.ManagementConsole.Node::.ctor()
0x18bc  ldarg.0
0x18bd  ldarg.0
0x18be  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x18c3  call     instance void Microsoft.ManagementConsole.Node::Initialize(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData data)
0x18c8  ldarg.0
0x18c9  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x18ce  ldtoken  Microsoft.ManagementConsole.NodeTypeAttribute
0x18d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18d8  ldc.i4.1
0x18d9  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x18de  stloc.0
0x18df  ldloc.0
0x18e0  ldlen
0x18e1  conv.i4
0x18e2  ldc.i4.1
0x18e3  bne.un.s loc_18FD
0x18e5  ldarg.0
0x18e6  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x18eb  ldloc.0
0x18ec  ldc.i4.0
0x18ed  ldelem.ref
0x18ee  castclass Microsoft.ManagementConsole.NodeTypeAttribute
0x18f3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ManagementConsole.NodeTypeAttribute::get_Guid()
0x18f8  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_NodeType(valuetype [mscorlib]System.Guid)
0x18fd  ret
```
