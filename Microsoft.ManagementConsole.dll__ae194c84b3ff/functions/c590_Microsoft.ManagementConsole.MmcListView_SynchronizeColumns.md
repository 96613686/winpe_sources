# Microsoft.ManagementConsole.MmcListView::SynchronizeColumns

- ea: `0xc590`
- end: `0xc642`
- name: `Microsoft.ManagementConsole.MmcListView::SynchronizeColumns`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc280`
- `0xc550`

## callees

- `0x42f0`
- `0x8490`
- `0xb300`
- `0xb320`
- `0xc590`
- `0xcef0`

## string_xrefs

- `0xc5cc`: `Empty column update for view {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xc590  ldarg.1
0xc591  brtrue.s loc_C59E
0xc593  ldstr    aItems// "items"
0xc598  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc59d  throw
0xc59e  ldarg.0
0xc59f  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xc5a4  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xc5a9  stloc.0
0xc5aa  ldloc.0
0xc5ab  brtrue.s loc_C5BD
0xc5ad  ldstr    aMmclistview// "MmcListView"
0xc5b2  ldstr    aSynchronizecol// "SynchronizeColumns"
0xc5b7  call     class [mscorlib]System.InvalidOperationException Microsoft.ManagementConsole.Internal.Utility::CreateClassNotInitializedException(string className, string operation)
0xc5bc  throw
0xc5bd  ldarg.1
0xc5be  ldlen
0xc5bf  conv.i4
0xc5c0  ldc.i4.1
0xc5c1  bge.s    loc_C5F0
0xc5c3  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xc5c8  ldc.i4.s 0x10
0xc5ca  ldc.i4.s 0xC
0xc5cc  ldstr    aEmptyColumnUpd// "Empty column update for view {0}."
0xc5d1  ldc.i4.1
0xc5d2  newarr   [mscorlib]System.Object
0xc5d7  stloc.s  4
0xc5d9  ldloc.s  4
0xc5db  ldc.i4.0
0xc5dc  ldarg.0
0xc5dd  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc5e2  box      [mscorlib]System.Int32
0xc5e7  stelem.ref
0xc5e8  ldloc.s  4
0xc5ea  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xc5ef  ret
0xc5f0  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateColumnsCommand::.ctor()
0xc5f5  stloc.1
0xc5f6  ldloc.1
0xc5f7  ldarg.0
0xc5f8  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc5fd  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xc602  ldloc.1
0xc603  ldarg.3
0xc604  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateColumnsCommand::set_ChangeType(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnCollectionChangeType)
0xc609  ldloc.1
0xc60a  ldarg.2
0xc60b  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateColumnsCommand::set_Index(int32)
0xc610  ldarg.1
0xc611  ldlen
0xc612  conv.i4
0xc613  newarr   [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData
0xc618  stloc.2
0xc619  ldc.i4.0
0xc61a  stloc.3
0xc61b  br.s     loc_C62C
0xc61d  ldloc.2
0xc61e  ldloc.3
0xc61f  ldarg.1
0xc620  ldloc.3
0xc621  ldelem.ref
0xc622  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData Microsoft.ManagementConsole.MmcListViewColumn::get_Data()
0xc627  stelem.ref
0xc628  ldloc.3
0xc629  ldc.i4.1
0xc62a  add
0xc62b  stloc.3
0xc62c  ldloc.3
0xc62d  ldarg.1
0xc62e  ldlen
0xc62f  conv.i4
0xc630  blt.s    loc_C61D
0xc632  ldloc.1
0xc633  ldloc.2
0xc634  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateColumnsCommand::SetData(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData[])
0xc639  ldloc.0
0xc63a  ldloc.1
0xc63b  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xc640  pop
0xc641  ret
```
