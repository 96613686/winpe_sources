# Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneHelpItems

- ea: `0x1520`
- end: `0x155d`
- name: `Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneHelpItems`
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

- `0x1520`
- `0x2f10`
- `0x2f20`
- `0x3240`
- `0x3290`

## pseudocode

```c

```

## disassembly

```asm
0x1520  ldarg.0
0x1521  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneHelpItems
0x1526  brtrue.s loc_1556
0x1528  ldarg.0
0x1529  newobj   instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::.ctor()
0x152e  stfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneHelpItems
0x1533  ldarg.0
0x1534  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneHelpItems
0x1539  ldc.i4.2
0x153a  callvirt instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::set_InsertionLocation(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsInsertionLocation value)
0x153f  ldarg.0
0x1540  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneHelpItems
0x1545  ldarg.0
0x1546  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnActionsPaneHelpItemsChanged(object sender, class Microsoft.ManagementConsole.ActionsPaneItemCollectionEventArgs e)
0x154c  newobj   instance void ActionsPaneItemCollectionEventHandler::.ctor(object object, native int method)
0x1551  callvirt instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::add_Changed(class ActionsPaneItemCollectionEventHandler value)
0x1556  ldarg.0
0x1557  ldfld    class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::_actionsPaneHelpItems
0x155c  ret
```
