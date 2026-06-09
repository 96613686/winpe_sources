# Microsoft.ManagementConsole.NodeSyncManager::GenerateSharedDataFormatConfiguration

- ea: `0xf10`
- end: `0xf72`
- name: `Microsoft.ManagementConsole.NodeSyncManager::GenerateSharedDataFormatConfiguration`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10b0`

## callees

- `0xf10`
- `0x16c0`
- `0x5200`
- `0x5590`
- `0x5780`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldnull
0xf11  stloc.0
0xf12  ldarg.1
0xf13  callvirt instance class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::get_SharedData()
0xf18  callvirt instance class Microsoft.ManagementConsole.WritableSharedDataItem[] Microsoft.ManagementConsole.WritableSharedData::GetItems()
0xf1d  stloc.1
0xf1e  ldloc.1
0xf1f  ldlen
0xf20  conv.i4
0xf21  ldc.i4.0
0xf22  ble.s    loc_F70
0xf24  ldloc.1
0xf25  ldlen
0xf26  conv.i4
0xf27  newarr   [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xf2c  stloc.0
0xf2d  ldc.i4.0
0xf2e  stloc.2
0xf2f  br.s     loc_F6A
0xf31  ldloc.0
0xf32  ldloc.2
0xf33  ldelema  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xf38  initobj  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xf3e  ldloc.0
0xf3f  ldloc.2
0xf40  ldelema  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xf45  ldloc.1
0xf46  ldloc.2
0xf47  ldelem.ref
0xf48  callvirt instance bool Microsoft.ManagementConsole.WritableSharedDataItem::get_RequiresCallback()
0xf4d  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_RequiresQuery(bool)
0xf52  ldloc.0
0xf53  ldloc.2
0xf54  ldelema  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xf59  ldloc.1
0xf5a  ldloc.2
0xf5b  ldelem.ref
0xf5c  callvirt instance string Microsoft.ManagementConsole.SharedDataItemBase::get_ClipboardFormatId()
0xf61  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_ClipboardFormatId(string)
0xf66  ldloc.2
0xf67  ldc.i4.1
0xf68  add
0xf69  stloc.2
0xf6a  ldloc.2
0xf6b  ldloc.1
0xf6c  ldlen
0xf6d  conv.i4
0xf6e  blt.s    loc_F31
0xf70  ldloc.0
0xf71  ret
```
