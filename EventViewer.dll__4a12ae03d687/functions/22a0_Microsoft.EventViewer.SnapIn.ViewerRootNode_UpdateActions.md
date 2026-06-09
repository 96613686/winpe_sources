# Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions

- ea: `0x22a0`
- end: `0x22e2`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions`
- size: `66`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1010`
- `0x15c0`
- `0x1a70`
- `0x1aa0`
- `0x1ad0`
- `0x1ea0`
- `0x1f40`
- `0x1fd0`
- `0x3c50`

## callees

- `0x22a0`
- `0x2470`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  ldarg.0
0x22a1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x22a6  callvirt instance class [mscorlib]System.Collections.ICollection [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Actions()
0x22ab  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x22b0  stloc.0
0x22b1  br.s     loc_22C6
0x22b3  ldloc.0
0x22b4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22b9  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x22be  stloc.1
0x22bf  ldarg.0
0x22c0  ldloc.1
0x22c1  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::AddOrModifyAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x22c6  ldloc.0
0x22c7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22cc  brtrue.s loc_22B3
0x22ce  leave.s  loc_22E1
0x22d0  ldloc.0
0x22d1  isinst   [mscorlib]System.IDisposable
0x22d6  stloc.2
0x22d7  ldloc.2
0x22d8  brfalse.s loc_22E0
0x22da  ldloc.2
0x22db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22e0  endfinally
0x22e1  ret
```
