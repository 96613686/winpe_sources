# Microsoft.ManagementConsole.ScopeNode::set_ViewDescriptions

- ea: `0x1640`
- end: `0x169c`
- name: `Microsoft.ManagementConsole.ScopeNode::set_ViewDescriptions`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1620`
- `0x16b0`

## callees

- `0x6f0`
- `0x1640`
- `0x1ee0`
- `0x8b10`
- `0x8c20`

## pseudocode

```c

```

## disassembly

```asm
0x1640  ldarg.1
0x1641  ldarg.0
0x1642  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1647  beq.s    loc_169B
0x1649  ldarg.0
0x164a  ldc.i4.0
0x164b  call     instance void Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription(bool fSubscribe)
0x1650  ldarg.0
0x1651  ldarg.1
0x1652  stfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1657  ldarg.0
0x1658  ldc.i4.1
0x1659  call     instance void Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription(bool fSubscribe)
0x165e  ldarg.0
0x165f  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1664  brfalse.s loc_1689
0x1666  ldarg.0
0x1667  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x166c  ldarg.0
0x166d  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1672  callvirt instance int32 Microsoft.ManagementConsole.ViewDescriptionCollection::get_Id()
0x1677  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_ViewSetId(int32)
0x167c  ldarg.0
0x167d  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1682  callvirt instance void Microsoft.ManagementConsole.ViewDescriptionCollection::Initialize()
0x1687  br.s     loc_1695
0x1689  ldarg.0
0x168a  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x168f  ldc.i4.m1
0x1690  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_ViewSetId(int32)
0x1695  ldarg.0
0x1696  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x169b  ret
```
