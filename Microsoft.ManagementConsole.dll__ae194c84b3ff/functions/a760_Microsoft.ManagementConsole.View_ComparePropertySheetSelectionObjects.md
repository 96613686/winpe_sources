# Microsoft.ManagementConsole.View::ComparePropertySheetSelectionObjects

- ea: `0xa760`
- end: `0xa7dc`
- name: `Microsoft.ManagementConsole.View::ComparePropertySheetSelectionObjects`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x9e00`

## callees

- `0x4210`
- `0x4310`
- `0x7250`
- `0x73b0`
- `0xa760`
- `0xb430`
- `0xd2d0`
- `0xd390`
- `0xd3a0`
- `0xe9b0`

## pseudocode

```c

```

## disassembly

```asm
0xa760  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CompareSelectionObjectsResponse::.ctor()
0xa765  stloc.0
0xa766  ldloc.0
0xa767  ldc.i4.0
0xa768  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CompareSelectionObjectsResponse::set_Result(bool)
0xa76d  ldarg.3
0xa76e  brtrue.s loc_A77B
0xa770  ldstr    aRequeststatus// "requestStatus"
0xa775  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa77a  throw
0xa77b  ldarg.3
0xa77c  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xa781  stloc.1
0xa782  ldarg.0
0xa783  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa788  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectionCardinality Microsoft.ManagementConsole.SelectionData::get_SelectionCardinality()
0xa78d  brfalse.s loc_A7CB
0xa78f  ldarg.1
0xa790  ldarg.0
0xa791  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa796  callvirt instance int32 Microsoft.ManagementConsole.SelectionData::get_Id()
0xa79b  bne.un.s loc_A7CB
0xa79d  ldarg.0
0xa79e  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa7a3  callvirt instance object Microsoft.ManagementConsole.SelectionData::get_SelectionObject()
0xa7a8  brfalse.s loc_A7CB
0xa7aa  ldloc.0
0xa7ab  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0xa7b0  callvirt instance class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.SnapInBase::get_SheetManager()
0xa7b5  ldarg.0
0xa7b6  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa7bb  callvirt instance object Microsoft.ManagementConsole.SelectionData::get_SelectionObject()
0xa7c0  ldarg.2
0xa7c1  callvirt instance bool Microsoft.ManagementConsole.PropertySheetManager::ComparePropertySheetSelectionObjects(object selectionObject, int32 selectionId)
0xa7c6  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.CompareSelectionObjectsResponse::set_Result(bool)
0xa7cb  ldarg.3
0xa7cc  ldloc.0
0xa7cd  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0xa7d2  leave.s  loc_A7DB
0xa7d4  ldloc.1
0xa7d5  callvirt instance void Microsoft.ManagementConsole.Status::Close()
0xa7da  endfinally
0xa7db  ret
```
