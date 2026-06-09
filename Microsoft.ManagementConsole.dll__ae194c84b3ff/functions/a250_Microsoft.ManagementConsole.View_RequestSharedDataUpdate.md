# Microsoft.ManagementConsole.View::RequestSharedDataUpdate

- ea: `0xa250`
- end: `0xa36d`
- name: `Microsoft.ManagementConsole.View::RequestSharedDataUpdate`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9e00`

## callees

- `0x4310`
- `0x5550`
- `0x73d0`
- `0xa250`
- `0xa370`
- `0xb300`
- `0xb430`
- `0xb4b0`
- `0xd1f0`
- `0xd2d0`
- `0xd390`
- `0xd3a0`
- `0xdbf0`
- `0xdc00`
- `0xdc50`
- `0xea40`

## pseudocode

```c

```

## disassembly

```asm
0xa250  ldnull
0xa251  stloc.0
0xa252  ldnull
0xa253  stloc.1
0xa254  ldarg.0
0xa255  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa25a  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectionCardinality Microsoft.ManagementConsole.SelectionData::get_SelectionCardinality()
0xa25f  brfalse.s loc_A272
0xa261  ldarg.2
0xa262  ldarg.0
0xa263  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa268  callvirt instance int32 Microsoft.ManagementConsole.SelectionData::get_Id()
0xa26d  beq      loc_A2F7
0xa272  ldarg.0
0xa273  call     instance class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.View::get_ClipboardSelectionDatas()
0xa278  ldarg.2
0xa279  box      [mscorlib]System.Int32
0xa27e  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionData Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::get_Item(object key)
0xa283  stloc.2
0xa284  ldloc.2
0xa285  brtrue.s loc_A2A3
0xa287  ldarg.0
0xa288  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xa28d  callvirt instance class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.SnapInBase::get_SheetManager()
0xa292  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.PropertySheetManager::get_ActiveViewPropertySheetSelectionDatas()
0xa297  ldarg.2
0xa298  box      [mscorlib]System.Int32
0xa29d  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionData Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::get_Item(object key)
0xa2a2  stloc.2
0xa2a3  ldloc.2
0xa2a4  brfalse.s loc_A2B6
0xa2a6  ldloc.2
0xa2a7  callvirt instance class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.AuxiliarySelectionData::get_SharedData()
0xa2ac  stloc.1
0xa2ad  ldloc.2
0xa2ae  callvirt instance object Microsoft.ManagementConsole.AuxiliarySelectionData::get_SelectionObject()
0xa2b3  stloc.0
0xa2b4  br.s     loc_A30F
0xa2b6  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xa2bb  ldc.i4.4
0xa2bc  ldc.i4.s 0xC
0xa2be  ldstr    aRequestForUpda// "Request for updating data format {0} in"...
0xa2c3  ldc.i4.3
0xa2c4  newarr   [mscorlib]System.Object
0xa2c9  stloc.s  4
0xa2cb  ldloc.s  4
0xa2cd  ldc.i4.0
0xa2ce  ldarga.s 1
0xa2d0  call     instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0xa2d5  stelem.ref
0xa2d6  ldloc.s  4
0xa2d8  ldc.i4.1
0xa2d9  ldarg.0
0xa2da  ldfld    int32 Microsoft.ManagementConsole.View::_viewInstanceId
0xa2df  box      [mscorlib]System.Int32
0xa2e4  stelem.ref
0xa2e5  ldloc.s  4
0xa2e7  ldc.i4.2
0xa2e8  ldarg.2
0xa2e9  box      [mscorlib]System.Int32
0xa2ee  stelem.ref
0xa2ef  ldloc.s  4
0xa2f1  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xa2f6  ret
0xa2f7  ldarg.0
0xa2f8  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa2fd  callvirt instance class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.SelectionData::get_SharedData()
0xa302  stloc.1
0xa303  ldarg.0
0xa304  call     instance class Microsoft.ManagementConsole.SelectionData Microsoft.ManagementConsole.View::get_SelectionData()
0xa309  callvirt instance object Microsoft.ManagementConsole.SelectionData::get_SelectionObject()
0xa30e  stloc.0
0xa30f  ldloc.1
0xa310  ldarga.s 1
0xa312  call     instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0xa317  callvirt instance class Microsoft.ManagementConsole.WritableSharedDataItem Microsoft.ManagementConsole.WritableSharedData::GetItem(string clipboardFormatId)
0xa31c  stloc.3
0xa31d  ldloc.3
0xa31e  brtrue.s loc_A357
0xa320  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xa325  ldc.i4.4
0xa326  ldc.i4.s 0xC
0xa328  ldstr    aTheRequestedDa// "The requested data format {0} is no lon"...
0xa32d  ldc.i4.2
0xa32e  newarr   [mscorlib]System.Object
0xa333  stloc.s  5
0xa335  ldloc.s  5
0xa337  ldc.i4.0
0xa338  ldarga.s 1
0xa33a  call     instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0xa33f  stelem.ref
0xa340  ldloc.s  5
0xa342  ldc.i4.1
0xa343  ldarg.0
0xa344  ldfld    int32 Microsoft.ManagementConsole.View::_viewInstanceId
0xa349  box      [mscorlib]System.Int32
0xa34e  stelem.ref
0xa34f  ldloc.s  5
0xa351  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xa356  ret
0xa357  ldarg.0
0xa358  ldloc.0
0xa359  ldloc.3
0xa35a  ldarga.s 1
0xa35c  call     instance unsigned int8[] [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::GetValue()
0xa361  ldarg.3
0xa362  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xa367  callvirt instance void Microsoft.ManagementConsole.View::OnSharedDataChangeRequested(object selectionValue, class Microsoft.ManagementConsole.WritableSharedDataItem item, unsigned int8[] newValue, class Microsoft.ManagementConsole.AsyncStatus status)
0xa36c  ret
```
