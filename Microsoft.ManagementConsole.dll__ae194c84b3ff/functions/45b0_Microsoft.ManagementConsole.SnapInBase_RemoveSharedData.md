# Microsoft.ManagementConsole.SnapInBase::RemoveSharedData

- ea: `0x45b0`
- end: `0x45ee`
- name: `Microsoft.ManagementConsole.SnapInBase::RemoveSharedData`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1b40`
- `0xac60`

## callees

- `0x4230`
- `0x5190`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x45b0  ldarg.0
0x45b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.SharedData> Microsoft.ManagementConsole.SnapInBase::_externalDataObjects
0x45b6  ldarg.1
0x45b7  callvirt instance int32 Microsoft.ManagementConsole.SharedData::get_DataObjectId()
0x45bc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.SharedData>::Remove(var<u1>)
0x45c1  pop
0x45c2  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ChangeNotificationSubscriptionCommand::.ctor()
0x45c7  stloc.0
0x45c8  ldloc.0
0x45c9  ldarg.1
0x45ca  callvirt instance int32 Microsoft.ManagementConsole.SharedData::get_DataObjectId()
0x45cf  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataCommand::set_DataObjectId(int32)
0x45d4  ldloc.0
0x45d5  ldc.i4.0
0x45d6  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ChangeNotificationSubscriptionCommand::set_IsActive(bool)
0x45db  ldarg.0
0x45dc  call     instance class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::get_SnapInClient()
0x45e1  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0x45e6  ldloc.0
0x45e7  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x45ec  pop
0x45ed  ret
```
