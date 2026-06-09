# Microsoft.ManagementConsole.Advanced.NamespaceExtension::Initialize

- ea: `0x4bb0`
- end: `0x4bd2`
- name: `Microsoft.ManagementConsole.Advanced.NamespaceExtension::Initialize`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x40e0`
- `0x4230`
- `0x4530`
- `0x4ee0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x4bb0  ldarg.0
0x4bb1  call     instance void Microsoft.ManagementConsole.SnapInBase::Initialize()
0x4bb6  ldarg.0
0x4bb7  ldfld    class Microsoft.ManagementConsole.Advanced.PrimaryScopeNode Microsoft.ManagementConsole.Advanced.NamespaceExtension::_primaryNode
0x4bbc  callvirt instance class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x4bc1  ldarg.0
0x4bc2  call     instance class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::get_SnapInClient()
0x4bc7  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0x4bcc  callvirt instance void Microsoft.ManagementConsole.SharedData::SetSnapInPlatform(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform snapInPlatform)
0x4bd1  ret
```
