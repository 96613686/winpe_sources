# Microsoft.ManagementConsole.MmcListView::HandleSelectionChange

- ea: `0xc750`
- end: `0xc853`
- name: `Microsoft.ManagementConsole.MmcListView::HandleSelectionChange`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xc420`

## callees

- `0x670`
- `0x15f0`
- `0x5fa0`
- `0x6370`
- `0x6380`
- `0x73b0`
- `0xb310`
- `0xb320`
- `0xc1a0`
- `0xc750`

## string_xrefs

- `0xc7de`: `A selected ResultNode with id {0} in list view {1} appears to have been removed.`

## pseudocode

```c

```

## disassembly

```asm
0xc750  ldarg.0
0xc751  ldfld    class Microsoft.ManagementConsole.SelectedNodeCollection Microsoft.ManagementConsole.MmcListView::_selectedNodes
0xc756  callvirt instance void Microsoft.ManagementConsole.SelectedNodeCollection::Clear()
0xc75b  ldarg.0
0xc75c  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.View::get_ScopeNode()
0xc761  callvirt instance class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::get_Children()
0xc766  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xc76b  stloc.s  4
0xc76d  br.s     loc_C797
0xc76f  ldloc.s  4
0xc771  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc776  castclass Microsoft.ManagementConsole.ScopeNode
0xc77b  stloc.0
0xc77c  ldarg.1
0xc77d  ldloc.0
0xc77e  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0xc783  call     T0x2B000001
0xc788  ldc.i4.m1
0xc789  beq.s    loc_C797
0xc78b  ldarg.0
0xc78c  ldfld    class Microsoft.ManagementConsole.SelectedNodeCollection Microsoft.ManagementConsole.MmcListView::_selectedNodes
0xc791  ldloc.0
0xc792  callvirt instance void Microsoft.ManagementConsole.SelectedNodeCollection::Add(class Microsoft.ManagementConsole.Node item)
0xc797  ldloc.s  4
0xc799  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc79e  brtrue.s loc_C76F
0xc7a0  leave.s  loc_C7B7
0xc7a2  ldloc.s  4
0xc7a4  isinst   [mscorlib]System.IDisposable
0xc7a9  stloc.s  5
0xc7ab  ldloc.s  5
0xc7ad  brfalse.s loc_C7B6
0xc7af  ldloc.s  5
0xc7b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc7b6  endfinally
0xc7b7  ldarg.2
0xc7b8  stloc.s  6
0xc7ba  ldc.i4.0
0xc7bb  stloc.s  7
0xc7bd  br.s     loc_C81F
0xc7bf  ldloc.s  6
0xc7c1  ldloc.s  7
0xc7c3  ldelem.i4
0xc7c4  stloc.1
0xc7c5  ldarg.0
0xc7c6  ldfld    class Microsoft.ManagementConsole.ResultNodeCollection Microsoft.ManagementConsole.MmcListView::_resultNodes
0xc7cb  ldloc.1
0xc7cc  callvirt instance class Microsoft.ManagementConsole.ResultNode Microsoft.ManagementConsole.ResultNodeCollection::GetNode(int32 id)
0xc7d1  stloc.2
0xc7d2  ldloc.2
0xc7d3  brtrue.s loc_C80D
0xc7d5  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xc7da  ldc.i4.s 0x10
0xc7dc  ldc.i4.s 0xC
0xc7de  ldstr    aASelectedResul// "A selected ResultNode with id {0} in li"...
0xc7e3  ldc.i4.2
0xc7e4  newarr   [mscorlib]System.Object
0xc7e9  stloc.s  8
0xc7eb  ldloc.s  8
0xc7ed  ldc.i4.0
0xc7ee  ldloc.1
0xc7ef  box      [mscorlib]System.Int32
0xc7f4  stelem.ref
0xc7f5  ldloc.s  8
0xc7f7  ldc.i4.1
0xc7f8  ldarg.0
0xc7f9  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc7fe  box      [mscorlib]System.Int32
0xc803  stelem.ref
0xc804  ldloc.s  8
0xc806  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xc80b  br.s     loc_C819
0xc80d  ldarg.0
0xc80e  ldfld    class Microsoft.ManagementConsole.SelectedNodeCollection Microsoft.ManagementConsole.MmcListView::_selectedNodes
0xc813  ldloc.2
0xc814  callvirt instance void Microsoft.ManagementConsole.SelectedNodeCollection::Add(class Microsoft.ManagementConsole.Node item)
0xc819  ldloc.s  7
0xc81b  ldc.i4.1
0xc81c  add
0xc81d  stloc.s  7
0xc81f  ldloc.s  7
0xc821  ldloc.s  6
0xc823  ldlen
0xc824  conv.i4
0xc825  blt.s    loc_C7BF
0xc827  ldarg.0
0xc828  dup
0xc829  ldfld    valuetype ListViewStates Microsoft.ManagementConsole.MmcListView::_states
0xc82e  ldc.i4.1
0xc82f  or
0xc830  stfld    valuetype ListViewStates Microsoft.ManagementConsole.MmcListView::_states
0xc835  ldarg.3
0xc836  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0xc83b  stloc.3
0xc83c  ldarg.0
0xc83d  ldloc.3
0xc83e  callvirt instance void Microsoft.ManagementConsole.MmcListView::OnSelectionChanged(class Microsoft.ManagementConsole.SyncStatus status)
0xc843  ldarg.0
0xc844  dup
0xc845  ldfld    valuetype ListViewStates Microsoft.ManagementConsole.MmcListView::_states
0xc84a  ldc.i4.s 0xFE
0xc84c  and
0xc84d  stfld    valuetype ListViewStates Microsoft.ManagementConsole.MmcListView::_states
0xc852  ret
```
