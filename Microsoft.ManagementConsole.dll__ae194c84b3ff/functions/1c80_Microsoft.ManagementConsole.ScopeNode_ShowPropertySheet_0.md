# Microsoft.ManagementConsole.ScopeNode::ShowPropertySheet_0

- ea: `0x1c80`
- end: `0x1d3c`
- name: `Microsoft.ManagementConsole.ScopeNode::ShowPropertySheet_0`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1c70`

## callees

- `0x670`
- `0x1c80`
- `0x1db0`
- `0x4210`
- `0x42f0`
- `0x4310`
- `0xde30`
- `0xdef0`
- `0xe960`

## pseudocode

```c

```

## disassembly

```asm
0x1c80  ldarg.1
0x1c81  brtrue.s loc_1C8E
0x1c83  ldstr    aTitle// "title"
0x1c88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1c8d  throw
0x1c8e  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.FindPropertySheetForScopeNodeCommand::.ctor()
0x1c93  stloc.0
0x1c94  ldloc.0
0x1c95  ldarg.0
0x1c96  call     instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x1c9b  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.FindPropertySheetForScopeNodeCommand::set_ScopeNodeId(int32)
0x1ca0  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x1ca5  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0x1caa  ldloc.0
0x1cab  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x1cb0  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.FindPropertySheetCommandResult
0x1cb5  stloc.1
0x1cb6  ldloc.1
0x1cb7  brfalse.s loc_1CC3
0x1cb9  ldloc.1
0x1cba  callvirt instance bool [MMCFxCommon]Microsoft.ManagementConsole.Internal.FindPropertySheetCommandResult::get_SheetExists()
0x1cbf  brfalse.s loc_1CC3
0x1cc1  ldc.i4.0
0x1cc2  ret
0x1cc3  newobj   instance void Microsoft.ManagementConsole.PropertyPageCollection::.ctor()
0x1cc8  stloc.2
0x1cc9  ldarg.0
0x1cca  ldloc.2
0x1ccb  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnAddPropertyPages(class Microsoft.ManagementConsole.PropertyPageCollection propertyPageCollection)
0x1cd0  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetForScopeNodeCommand::.ctor()
0x1cd5  stloc.3
0x1cd6  ldloc.3
0x1cd7  ldarg.1
0x1cd8  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommand::set_Title(string)
0x1cdd  ldloc.3
0x1cde  ldarg.0
0x1cdf  call     instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x1ce4  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetForScopeNodeCommand::set_ScopeNodeId(int32)
0x1ce9  ldloc.3
0x1cea  ldarg.2
0x1ceb  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommand::set_HideApplyButton(bool)
0x1cf0  ldloc.3
0x1cf1  ldloc.2
0x1cf2  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[] Microsoft.ManagementConsole.PropertyPageCollection::ToPropertyPageInfoArray()
0x1cf7  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommand::set_PropertyPagesData(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PropertyPageInfo[])
0x1cfc  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x1d01  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0x1d06  ldloc.3
0x1d07  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x1d0c  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommandResult
0x1d11  stloc.s  4
0x1d13  ldloc.s  4
0x1d15  brfalse.s loc_1D3A
0x1d17  ldloc.s  4
0x1d19  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommandResult::get_SheetId()
0x1d1e  ldc.i4.m1
0x1d1f  beq.s    loc_1D3A
0x1d21  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x1d26  callvirt instance class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.SnapInBase::get_SheetManager()
0x1d2b  ldloc.s  4
0x1d2d  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.CreatePropertySheetCommandResult::get_SheetId()
0x1d32  ldloc.2
0x1d33  ldnull
0x1d34  callvirt instance class Microsoft.ManagementConsole.PropertySheet Microsoft.ManagementConsole.PropertySheetManager::CreatePropertySheet(int32 sheetId, class Microsoft.ManagementConsole.PropertyPageCollection pageCollection, class Microsoft.ManagementConsole.AuxiliarySelectionData auxiliarySelectionData)
0x1d39  pop
0x1d3a  ldc.i4.1
0x1d3b  ret
```
