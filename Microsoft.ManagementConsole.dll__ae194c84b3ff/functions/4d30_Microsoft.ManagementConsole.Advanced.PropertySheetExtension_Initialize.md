# Microsoft.ManagementConsole.Advanced.PropertySheetExtension::Initialize

- ea: `0x4d30`
- end: `0x4d4d`
- name: `Microsoft.ManagementConsole.Advanced.PropertySheetExtension::Initialize`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4230`
- `0x4530`
- `0x4ee0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x4d30  ldarg.0
0x4d31  call     instance void Microsoft.ManagementConsole.SnapInBase::Initialize()
0x4d36  ldarg.0
0x4d37  ldfld    class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_sharedData
0x4d3c  ldarg.0
0x4d3d  call     instance class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::get_SnapInClient()
0x4d42  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0x4d47  callvirt instance void Microsoft.ManagementConsole.SharedData::SetSnapInPlatform(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform snapInPlatform)
0x4d4c  ret
```
