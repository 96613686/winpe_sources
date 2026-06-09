# Microsoft.ManagementConsole.SharedDataItem::RequestDataUpdate

- ea: `0x5300`
- end: `0x536c`
- name: `Microsoft.ManagementConsole.SharedDataItem::RequestDataUpdate`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3d0`
- `0x5200`
- `0x5300`
- `0x6a20`
- `0x8440`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarg.0
0x5301  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SharedDataItem::_snapInPlatform
0x5306  brtrue.s loc_5318
0x5308  call     string Microsoft.ManagementConsole.Internal.Strings::get_AdvancedSharedDataItemNotInitialized()
0x530d  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x5312  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5317  throw
0x5318  ldloca.s 0
0x531a  initobj  [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData
0x5320  ldloca.s 0
0x5322  ldarg.0
0x5323  call     instance string Microsoft.ManagementConsole.SharedDataItemBase::get_ClipboardFormatId()
0x5328  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::set_ClipboardFormatId(string)
0x532d  ldloca.s 0
0x532f  ldarg.1
0x5330  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::SetValue(unsigned int8[])
0x5335  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestWriteDataCommand::.ctor()
0x533a  stloc.1
0x533b  ldloc.1
0x533c  ldarg.0
0x533d  ldfld    int32 Microsoft.ManagementConsole.SharedDataItem::_dataObjectId
0x5342  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataCommand::set_DataObjectId(int32)
0x5347  ldloc.1
0x5348  ldloc.0
0x5349  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestWriteDataCommand::set_RequestedValue(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData)
0x534e  ldarg.0
0x534f  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SharedDataItem::_snapInPlatform
0x5354  ldloc.1
0x5355  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x535a  pop
0x535b  leave.s  loc_536B
0x535d  stloc.2
0x535e  ldloc.2
0x535f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5364  ldloc.2
0x5365  newobj   instance void Microsoft.ManagementConsole.Advanced.PrimarySnapInDataException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x536a  throw
0x536b  ret
```
