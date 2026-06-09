# Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::OnChildrenChanged

- ea: `0x41a0`
- end: `0x41f0`
- name: `Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::OnChildrenChanged`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1230`
- `0x1350`
- `0x41a0`
- `0x5970`
- `0x5980`
- `0x59b0`

## pseudocode

```c

```

## disassembly

```asm
0x41a0  ldarg.2
0x41a1  callvirt instance valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::get_ChangeType()
0x41a6  stloc.0
0x41a7  ldloc.0
0x41a8  switch   loc_41B6, loc_41D6
0x41b5  ret
0x41b6  ldarg.0
0x41b7  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x41bc  brfalse.s loc_41EF
0x41be  ldarg.0
0x41bf  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x41c4  ldarg.2
0x41c5  callvirt instance class Microsoft.ManagementConsole.ScopeNode[] Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::GetItems()
0x41ca  ldarg.2
0x41cb  callvirt instance int32 Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::get_Index()
0x41d0  callvirt instance void Microsoft.ManagementConsole.NodeSyncManager::AddNodes(class Microsoft.ManagementConsole.ScopeNode[] items, int32 index)
0x41d5  ret
0x41d6  ldarg.0
0x41d7  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x41dc  brfalse.s loc_41EF
0x41de  ldarg.0
0x41df  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_nodeSyncManager
0x41e4  ldarg.2
0x41e5  callvirt instance class Microsoft.ManagementConsole.ScopeNode[] Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::GetItems()
0x41ea  callvirt instance void Microsoft.ManagementConsole.NodeSyncManager::RemoveNodes(class Microsoft.ManagementConsole.ScopeNode[] items)
0x41ef  ret
```
