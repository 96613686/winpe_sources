# Microsoft.ManagementConsole.Advanced.PropertySheetExtension::ProcessRequest

- ea: `0x4d80`
- end: `0x4dff`
- name: `Microsoft.ManagementConsole.Advanced.PropertySheetExtension::ProcessRequest`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4210`
- `0x4310`
- `0x43d0`
- `0x4d80`
- `0x4e30`
- `0x7250`
- `0x73b0`
- `0xde30`
- `0xdef0`
- `0xe960`

## pseudocode

```c

```

## disassembly

```asm
0x4d80  ldarg.1
0x4d81  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request::get_RequestInfo()
0x4d86  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo
0x4d8b  brfalse.s loc_4DF7
0x4d8d  ldarg.1
0x4d8e  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request::get_RequestInfo()
0x4d93  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo
0x4d98  stloc.0
0x4d99  newobj   instance void Microsoft.ManagementConsole.PropertyPageCollection::.ctor()
0x4d9e  stloc.1
0x4d9f  ldarg.1
0x4da0  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request::get_RequestStatus()
0x4da5  stloc.2
0x4da6  ldloc.2
0x4da7  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x4dac  stloc.3
0x4dad  ldarg.0
0x4dae  ldloc.1
0x4daf  callvirt instance void Microsoft.ManagementConsole.Advanced.PropertySheetExtension::OnAddPropertyPages(class Microsoft.ManagementConsole.PropertyPageCollection propertyPageCollection)
0x4db4  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPagesResponse::.ctor()
0x4db9  stloc.s  4
0x4dbb  ldloc.s  4
0x4dbd  ldloc.1
0x4dbe  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[] Microsoft.ManagementConsole.PropertyPageCollection::ToPropertyPageInfoArray()
0x4dc3  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPagesResponse::SetPropertyPages(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[])
0x4dc8  ldloc.2
0x4dc9  ldloc.s  4
0x4dcb  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0x4dd0  leave.s  loc_4DD9
0x4dd2  ldloc.3
0x4dd3  callvirt instance void Microsoft.ManagementConsole.Status::Close()
0x4dd8  endfinally
0x4dd9  ldarg.0
0x4dda  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x4ddf  callvirt instance class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.SnapInBase::get_SheetManager()
0x4de4  ldloc.0
0x4de5  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo::get_SheetId()
0x4dea  ldloc.1
0x4deb  ldnull
0x4dec  callvirt instance class Microsoft.ManagementConsole.PropertySheet Microsoft.ManagementConsole.PropertySheetManager::CreatePropertySheet(int32 sheetId, class Microsoft.ManagementConsole.PropertyPageCollection pageCollection, class Microsoft.ManagementConsole.AuxiliarySelectionData auxiliarySelectionData)
0x4df1  stfld    class Microsoft.ManagementConsole.PropertySheet Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_extensionPropertySheet
0x4df6  ret
0x4df7  ldarg.0
0x4df8  ldarg.1
0x4df9  call     instance void Microsoft.ManagementConsole.SnapInBase::ProcessRequest(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request request)
0x4dfe  ret
```
