# Microsoft.ManagementConsole.Advanced.NamespaceExtension::ProcessNotification

- ea: `0x4bf0`
- end: `0x4c36`
- name: `Microsoft.ManagementConsole.Advanced.NamespaceExtension::ProcessNotification`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x40e0`
- `0x4150`
- `0x4550`
- `0x4570`
- `0x4a10`
- `0x4bf0`

## pseudocode

```c

```

## disassembly

```asm
0x4bf0  ldarg.1
0x4bf1  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification
0x4bf6  brfalse.s loc_4C2E
0x4bf8  ldarg.1
0x4bf9  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification
0x4bfe  stloc.0
0x4bff  ldarg.0
0x4c00  ldfld    class Microsoft.ManagementConsole.Advanced.PrimaryScopeNode Microsoft.ManagementConsole.Advanced.NamespaceExtension::_primaryNode
0x4c05  ldarg.0
0x4c06  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.NamespaceSnapInBase::_nodeSyncManager
0x4c0b  ldloc.0
0x4c0c  callvirt instance valuetype [mscorlib]System.Guid [MMCFxCommon]Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification::get_PrimaryNodeType()
0x4c11  callvirt instance void Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::Initialize(class Microsoft.ManagementConsole.NodeSyncManager nodeSyncManager, valuetype [mscorlib]System.Guid nodeType)
0x4c16  ldarg.0
0x4c17  ldarg.0
0x4c18  ldfld    class Microsoft.ManagementConsole.Advanced.PrimaryScopeNode Microsoft.ManagementConsole.Advanced.NamespaceExtension::_primaryNode
0x4c1d  callvirt instance class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x4c22  call     instance void Microsoft.ManagementConsole.SnapInBase::AddSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0x4c27  ldarg.0
0x4c28  callvirt instance void Microsoft.ManagementConsole.SnapInBase::OnInitialize()
0x4c2d  ret
0x4c2e  ldarg.0
0x4c2f  ldarg.1
0x4c30  call     instance void Microsoft.ManagementConsole.NamespaceSnapInBase::ProcessNotification(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Notification notif)
0x4c35  ret
```
