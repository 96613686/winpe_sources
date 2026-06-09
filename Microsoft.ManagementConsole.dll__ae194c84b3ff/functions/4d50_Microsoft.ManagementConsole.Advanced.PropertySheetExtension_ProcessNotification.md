# Microsoft.ManagementConsole.Advanced.PropertySheetExtension::ProcessNotification

- ea: `0x4d50`
- end: `0x4d80`
- name: `Microsoft.ManagementConsole.Advanced.PropertySheetExtension::ProcessNotification`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4430`
- `0x4570`
- `0x4d50`

## pseudocode

```c

```

## disassembly

```asm
0x4d50  ldarg.1
0x4d51  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertySheetExtensionInitNotification
0x4d56  brfalse.s loc_4D78
0x4d58  ldarg.1
0x4d59  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertySheetExtensionInitNotification
0x4d5e  stloc.0
0x4d5f  ldarg.0
0x4d60  ldloc.0
0x4d61  callvirt instance valuetype [mscorlib]System.Guid[] [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertySheetExtensionInitNotification::GetPrimaryNodeTypes()
0x4d66  stfld    valuetype [mscorlib]System.Guid[] Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_nodeTypes
0x4d6b  ldarg.0
0x4d6c  ldarg.0
0x4d6d  ldfld    class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_sharedData
0x4d72  call     instance void Microsoft.ManagementConsole.SnapInBase::AddSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0x4d77  ret
0x4d78  ldarg.0
0x4d79  ldarg.1
0x4d7a  call     instance void Microsoft.ManagementConsole.SnapInBase::ProcessNotification(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Notification notification)
0x4d7f  ret
```
