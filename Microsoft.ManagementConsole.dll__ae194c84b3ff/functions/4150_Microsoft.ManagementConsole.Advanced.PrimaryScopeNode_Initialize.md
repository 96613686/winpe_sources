# Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::Initialize

- ea: `0x4150`
- end: `0x4192`
- name: `Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::Initialize`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4bf0`

## callees

- `0x1230`
- `0x4150`
- `0x5a80`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldarg.1
0x4151  brtrue.s loc_415E
0x4153  ldstr    aNodesyncmanage_7// "nodeSyncManager"
0x4158  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x415d  throw
0x415e  ldarg.0
0x415f  ldarg.1
0x4160  stfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x4165  ldarg.0
0x4166  ldarg.2
0x4167  stfld    valuetype [mscorlib]System.Guid Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeType
0x416c  ldarg.0
0x416d  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_children
0x4172  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4177  ldc.i4.0
0x4178  ble.s    loc_4191
0x417a  ldarg.0
0x417b  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x4180  ldarg.0
0x4181  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_children
0x4186  callvirt instance class Microsoft.ManagementConsole.ScopeNode[] Microsoft.ManagementConsole.ScopeNodeCollection::ToArray()
0x418b  ldc.i4.0
0x418c  callvirt instance void Microsoft.ManagementConsole.NodeSyncManager::AddNodes(class Microsoft.ManagementConsole.ScopeNode[] items, int32 index)
0x4191  ret
```
