# Microsoft.ManagementConsole.View::DoVerb

- ea: `0xac60`
- end: `0xae2f`
- name: `Microsoft.ManagementConsole.View::DoVerb`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x9e00`

## callees

- `0x550`
- `0x4230`
- `0x4570`
- `0x45b0`
- `0x4ec0`
- `0x4ee0`
- `0x73b0`
- `0x73d0`
- `0x7ec0`
- `0xac60`
- `0xae30`
- `0xae40`
- `0xae50`
- `0xae60`
- `0xae70`
- `0xae80`
- `0xb310`
- `0xb430`
- `0xb4b0`
- `0xd390`
- `0xd3a0`
- `0xdc00`
- `0xdc50`

## string_xrefs

- `0xaca4`: `Request CutOrMove in view {0} ignore since selection id {1} could not be found.`

## pseudocode

```c

```

## disassembly

```asm
0xac60  ldarg.1
0xac61  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.CutOrMoveViewSelectionRequestInfo
0xac66  brfalse.s loc_ACD7
0xac68  ldarg.1
0xac69  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.CutOrMoveViewSelectionRequestInfo
0xac6e  stloc.0
0xac6f  ldarg.0
0xac70  call     instance class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.View::get_ClipboardSelectionDatas()
0xac75  ldloc.0
0xac76  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewSelectionRequestInfo::get_SelectionId()
0xac7b  box      [mscorlib]System.Int32
0xac80  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionData Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::get_Item(object key)
0xac85  stloc.1
0xac86  ldloc.1
0xac87  brfalse.s loc_AC9C
0xac89  ldarg.0
0xac8a  ldloc.1
0xac8b  callvirt instance object Microsoft.ManagementConsole.AuxiliarySelectionData::get_SelectionObject()
0xac90  ldarg.2
0xac91  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xac96  callvirt instance void Microsoft.ManagementConsole.View::OnCut(object selectionValue, class Microsoft.ManagementConsole.AsyncStatus status)
0xac9b  ret
0xac9c  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xaca1  ldc.i4.4
0xaca2  ldc.i4.s 0xC
0xaca4  ldstr    aRequestCutormo// "Request CutOrMove in view {0} ignore si"...
0xaca9  ldc.i4.2
0xacaa  newarr   [mscorlib]System.Object
0xacaf  stloc.s  6
0xacb1  ldloc.s  6
0xacb3  ldc.i4.0
0xacb4  ldarg.0
0xacb5  ldfld    int32 Microsoft.ManagementConsole.View::_viewInstanceId
0xacba  box      [mscorlib]System.Int32
0xacbf  stelem.ref
0xacc0  ldloc.s  6
0xacc2  ldc.i4.1
0xacc3  ldloc.0
0xacc4  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewSelectionRequestInfo::get_SelectionId()
0xacc9  box      [mscorlib]System.Int32
0xacce  stelem.ref
0xaccf  ldloc.s  6
0xacd1  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xacd6  ret
0xacd7  ldarg.1
0xacd8  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewSelectionRequestInfo
0xacdd  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewSelectionRequestInfo::get_SelectionId()
0xace2  stloc.2
0xace3  ldarg.0
0xace4  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xace9  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectionCardinality Microsoft.ManagementConsole.SelectionData::get_SelectionCardinality()
0xacee  brfalse.s loc_ACFE
0xacf0  ldloc.2
0xacf1  ldarg.0
0xacf2  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xacf7  callvirt instance int32 Microsoft.ManagementConsole.SelectionData::get_Id()
0xacfc  beq.s    loc_AD43
0xacfe  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xad03  ldc.i4.4
0xad04  ldc.i4.s 0xC
0xad06  ldstr    aRequest0InView// "Request {0} in view {1} selection id {2"...
0xad0b  ldc.i4.3
0xad0c  newarr   [mscorlib]System.Object
0xad11  stloc.s  7
0xad13  ldloc.s  7
0xad15  ldc.i4.0
0xad16  ldarg.1
0xad17  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xad1c  callvirt instance string [mscorlib]System.Type::get_FullName()
0xad21  stelem.ref
0xad22  ldloc.s  7
0xad24  ldc.i4.1
0xad25  ldarg.0
0xad26  ldfld    int32 Microsoft.ManagementConsole.View::_viewInstanceId
0xad2b  box      [mscorlib]System.Int32
0xad30  stelem.ref
0xad31  ldloc.s  7
0xad33  ldc.i4.2
0xad34  ldloc.2
0xad35  box      [mscorlib]System.Int32
0xad3a  stelem.ref
0xad3b  ldloc.s  7
0xad3d  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xad42  ret
0xad43  ldarg.1
0xad44  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.DeleteViewSelectionRequestInfo
0xad49  brfalse.s loc_AD58
0xad4b  ldarg.0
0xad4c  ldarg.2
0xad4d  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xad52  callvirt instance void Microsoft.ManagementConsole.View::OnDelete(class Microsoft.ManagementConsole.SyncStatus status)
0xad57  ret
0xad58  ldarg.1
0xad59  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.RefreshViewSelectionRequestInfo
0xad5e  brfalse.s loc_AD6D
0xad60  ldarg.0
0xad61  ldarg.2
0xad62  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xad67  callvirt instance void Microsoft.ManagementConsole.View::OnRefresh(class Microsoft.ManagementConsole.AsyncStatus status)
0xad6c  ret
0xad6d  ldarg.1
0xad6e  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PrintViewSelectionRequestInfo
0xad73  brfalse.s loc_AD82
0xad75  ldarg.0
0xad76  ldarg.2
0xad77  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xad7c  callvirt instance void Microsoft.ManagementConsole.View::OnPrint(class Microsoft.ManagementConsole.SyncStatus status)
0xad81  ret
0xad82  ldarg.1
0xad83  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameViewSelectionRequestInfo
0xad88  brfalse.s loc_ADA2
0xad8a  ldarg.0
0xad8b  ldarg.1
0xad8c  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameViewSelectionRequestInfo
0xad91  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameViewSelectionRequestInfo::get_NewDisplayName()
0xad96  ldarg.2
0xad97  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xad9c  callvirt instance void Microsoft.ManagementConsole.View::OnRename(string newText, class Microsoft.ManagementConsole.SyncStatus status)
0xada1  ret
0xada2  ldarg.1
0xada3  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteViewSelectionRequestInfo
0xada8  brfalse  loc_AE2E
0xadad  ldarg.1
0xadae  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteViewSelectionRequestInfo
0xadb3  stloc.3
0xadb4  ldloc.3
0xadb5  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteViewSelectionRequestInfo::get_DataObjectId()
0xadba  newobj   instance void Microsoft.ManagementConsole.SharedData::.ctor(int32 dataObjectId)
0xadbf  stloc.s  4
0xadc1  ldarg.0
0xadc2  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.View::get_ScopeNode()
0xadc7  callvirt instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0xadcc  ldloc.s  4
0xadce  callvirt instance void Microsoft.ManagementConsole.SnapInBase::AddSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0xadd3  ldloc.s  4
0xadd5  ldarg.0
0xadd6  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.View::get_ScopeNode()
0xaddb  callvirt instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0xade0  callvirt instance class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::get_SnapInClient()
0xade5  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0xadea  callvirt instance void Microsoft.ManagementConsole.SharedData::SetSnapInPlatform(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform snapInPlatform)
0xadef  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteResponse::.ctor()
0xadf4  stloc.s  5
0xadf6  ldloc.s  5
0xadf8  ldarg.0
0xadf9  ldloc.s  4
0xadfb  ldloc.3
0xadfc  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DragAndDropVerb [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteViewSelectionRequestInfo::get_PasteType()
0xae01  ldarg.2
0xae02  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xae07  callvirt instance bool Microsoft.ManagementConsole.View::OnPaste(class Microsoft.ManagementConsole.SharedData data, valuetype Microsoft.ManagementConsole.DragAndDropVerb pasteType, class Microsoft.ManagementConsole.SyncStatus status)
0xae0c  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteResponse::set_AcceptPaste(bool)
0xae11  ldarg.2
0xae12  ldloc.s  5
0xae14  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0xae19  leave.s  loc_AE2E
0xae1b  ldarg.0
0xae1c  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.View::get_ScopeNode()
0xae21  callvirt instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0xae26  ldloc.s  4
0xae28  callvirt instance void Microsoft.ManagementConsole.SnapInBase::RemoveSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0xae2d  endfinally
0xae2e  ret
```
