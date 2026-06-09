# Microsoft.ManagementConsole.MmcListView::SynchronizeResultNodes

- ea: `0xc690`
- end: `0xc742`
- name: `Microsoft.ManagementConsole.MmcListView::SynchronizeResultNodes`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc280`
- `0xc650`

## callees

- `0x6c0`
- `0x42f0`
- `0x8490`
- `0xb300`
- `0xb320`
- `0xc690`

## string_xrefs

- `0xc6cc`: `Empty result nodes update for view {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xc690  ldarg.0
0xc691  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xc696  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xc69b  stloc.0
0xc69c  ldloc.0
0xc69d  brtrue.s loc_C6AF
0xc69f  ldstr    aMmclistview// "MmcListView"
0xc6a4  ldstr    aSynchronizeres// "SynchronizeResultNodes"
0xc6a9  call     class [mscorlib]System.InvalidOperationException Microsoft.ManagementConsole.Internal.Utility::CreateClassNotInitializedException(string className, string operation)
0xc6ae  throw
0xc6af  ldarg.1
0xc6b0  brtrue.s loc_C6BD
0xc6b2  ldstr    aItems// "items"
0xc6b7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc6bc  throw
0xc6bd  ldarg.1
0xc6be  ldlen
0xc6bf  conv.i4
0xc6c0  ldc.i4.1
0xc6c1  bge.s    loc_C6F0
0xc6c3  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xc6c8  ldc.i4.s 0x10
0xc6ca  ldc.i4.s 0xC
0xc6cc  ldstr    aEmptyResultNod// "Empty result nodes update for view {0}."
0xc6d1  ldc.i4.1
0xc6d2  newarr   [mscorlib]System.Object
0xc6d7  stloc.s  4
0xc6d9  ldloc.s  4
0xc6db  ldc.i4.0
0xc6dc  ldarg.0
0xc6dd  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc6e2  box      [mscorlib]System.Int32
0xc6e7  stelem.ref
0xc6e8  ldloc.s  4
0xc6ea  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xc6ef  ret
0xc6f0  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateResultNodesCommand::.ctor()
0xc6f5  stloc.1
0xc6f6  ldloc.1
0xc6f7  ldarg.0
0xc6f8  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc6fd  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xc702  ldloc.1
0xc703  ldarg.3
0xc704  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateResultNodesCommand::set_ChangeType(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ResultNodeCollectionChangeType)
0xc709  ldloc.1
0xc70a  ldarg.2
0xc70b  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateResultNodesCommand::set_Index(int32)
0xc710  ldarg.1
0xc711  ldlen
0xc712  conv.i4
0xc713  newarr   [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData
0xc718  stloc.2
0xc719  ldc.i4.0
0xc71a  stloc.3
0xc71b  br.s     loc_C72C
0xc71d  ldloc.2
0xc71e  ldloc.3
0xc71f  ldarg.1
0xc720  ldloc.3
0xc721  ldelem.ref
0xc722  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData Microsoft.ManagementConsole.Node::get_Data()
0xc727  stelem.ref
0xc728  ldloc.3
0xc729  ldc.i4.1
0xc72a  add
0xc72b  stloc.3
0xc72c  ldloc.3
0xc72d  ldarg.1
0xc72e  ldlen
0xc72f  conv.i4
0xc730  blt.s    loc_C71D
0xc732  ldloc.1
0xc733  ldloc.2
0xc734  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateResultNodesCommand::SetData(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData[])
0xc739  ldloc.0
0xc73a  ldloc.1
0xc73b  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xc740  pop
0xc741  ret
```
