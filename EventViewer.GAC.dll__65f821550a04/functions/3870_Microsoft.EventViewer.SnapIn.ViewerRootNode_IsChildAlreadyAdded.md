# Microsoft.EventViewer.SnapIn.ViewerRootNode::IsChildAlreadyAdded

- ea: `0x3870`
- end: `0x38cc`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::IsChildAlreadyAdded`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3f40`

## callees

- `0x3870`

## pseudocode

```c

```

## disassembly

```asm
0x3870  ldarg.0
0x3871  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3876  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x387b  stloc.0
0x387c  br.s     loc_38AD
0x387e  ldloc.0
0x387f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3884  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x3889  isinst   Microsoft.EventViewer.SnapIn.MMCEventsNode
0x388e  stloc.1
0x388f  ldloc.1
0x3890  brfalse.s loc_38AD
0x3892  ldloc.1
0x3893  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3898  ldarg.1
0x3899  bne.un.s loc_38AD
0x389b  ldloc.1
0x389c  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x38a1  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x38a6  ldc.i4.4
0x38a7  beq.s    loc_38AD
0x38a9  ldc.i4.1
0x38aa  stloc.2
0x38ab  leave.s  loc_38CA
0x38ad  ldloc.0
0x38ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x38b3  brtrue.s loc_387E
0x38b5  leave.s  loc_38C8
0x38b7  ldloc.0
0x38b8  isinst   [mscorlib]System.IDisposable
0x38bd  stloc.3
0x38be  ldloc.3
0x38bf  brfalse.s loc_38C7
0x38c1  ldloc.3
0x38c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38c7  endfinally
0x38c8  ldc.i4.0
0x38c9  ret
0x38ca  ldloc.2
0x38cb  ret
```
