# Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneItems

- ea: `0x14e0`
- end: `0x151d`
- name: `Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneItems`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xa80`
- `0xb40`
- `0x10b0`
- `0x19e0`

## callees

- `0x14e0`
- `0x2f10`
- `0x2f20`
- `0x3240`
- `0x3290`

## pseudocode

```c

```

## disassembly

```asm
0x14e0  ldarg.0
0x14e1  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneItems
0x14e6  brtrue.s loc_1516
0x14e8  ldarg.0
0x14e9  newobj   instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::.ctor()
0x14ee  stfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneItems
0x14f3  ldarg.0
0x14f4  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneItems
0x14f9  ldc.i4.0
0x14fa  callvirt instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::set_InsertionLocation(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsInsertionLocation value)
0x14ff  ldarg.0
0x1500  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneItems
0x1505  ldarg.0
0x1506  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnActionsPaneItemsChanged(object sender, class Microsoft.ManagementConsole.ActionsPaneItemCollectionEventArgs e)
0x150c  newobj   instance void ActionsPaneItemCollectionEventHandler::.ctor(object object, native int method)
0x1511  callvirt instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::add_Changed(class ActionsPaneItemCollectionEventHandler value)
0x1516  ldarg.0
0x1517  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneItems
0x151c  ret
```
