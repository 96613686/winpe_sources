# Microsoft.ManagementConsole.ScopeNode::GetPropertyPages

- ea: `0x1d40`
- end: `0x1da2`
- name: `Microsoft.ManagementConsole.ScopeNode::GetPropertyPages`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x330`
- `0x1d40`
- `0x1db0`
- `0x4210`
- `0x4310`
- `0x7250`
- `0x73b0`
- `0x8440`
- `0xde30`
- `0xdef0`
- `0xe960`

## pseudocode

```c

```

## disassembly

```asm
0x1d40  ldarg.2
0x1d41  brtrue.s loc_1D58
0x1d43  ldstr    aRequeststatus// "requestStatus"
0x1d48  call     string Microsoft.ManagementConsole.Internal.Strings::get_ScopeNodeRequestInterfaceNull()
0x1d4d  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x1d52  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x1d57  throw
0x1d58  newobj   instance void Microsoft.ManagementConsole.PropertyPageCollection::.ctor()
0x1d5d  stloc.0
0x1d5e  ldarg.2
0x1d5f  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1d64  stloc.1
0x1d65  ldarg.0
0x1d66  ldloc.0
0x1d67  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnAddPropertyPages(class Microsoft.ManagementConsole.PropertyPageCollection propertyPageCollection)
0x1d6c  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPagesResponse::.ctor()
0x1d71  stloc.2
0x1d72  ldloc.2
0x1d73  ldloc.0
0x1d74  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[] Microsoft.ManagementConsole.PropertyPageCollection::ToPropertyPageInfoArray()
0x1d79  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPagesResponse::SetPropertyPages(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[])
0x1d7e  ldarg.2
0x1d7f  ldloc.2
0x1d80  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0x1d85  leave.s  loc_1D8E
0x1d87  ldloc.1
0x1d88  callvirt instance void Microsoft.ManagementConsole.Status::Close()
0x1d8d  endfinally
0x1d8e  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x1d93  callvirt instance class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.SnapInBase::get_SheetManager()
0x1d98  ldarg.1
0x1d99  ldloc.0
0x1d9a  ldnull
0x1d9b  callvirt instance class Microsoft.ManagementConsole.PropertySheet Microsoft.ManagementConsole.PropertySheetManager::CreatePropertySheet(int32 sheetId, class Microsoft.ManagementConsole.PropertyPageCollection pageCollection, class Microsoft.ManagementConsole.AuxiliarySelectionData auxiliarySelectionData)
0x1da0  pop
0x1da1  ret
```
