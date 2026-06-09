# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetExportLogRootNode

- ea: `0x31d0`
- end: `0x3276`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetExportLogRootNode`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9e0`
- `0x1cc0`
- `0x37c0`

## callees

- `0x1860`
- `0x1ae0`
- `0x31d0`
- `0x3be0`
- `0x3d70`
- `0x9120`

## pseudocode

```c

```

## disassembly

```asm
0x31d0  ldnull
0x31d1  stloc.0
0x31d2  ldarg.0
0x31d3  call     instance class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventViewerRootNode()
0x31d8  stloc.1
0x31d9  ldloc.1
0x31da  brfalse.s loc_323C
0x31dc  ldloc.1
0x31dd  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x31e2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x31e7  stloc.2
0x31e8  br.s     loc_3210
0x31ea  ldloc.2
0x31eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x31f0  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x31f5  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x31fa  stloc.3
0x31fb  ldloc.3
0x31fc  brfalse.s loc_3210
0x31fe  ldloc.3
0x31ff  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3204  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x3209  ldc.i4.5
0x320a  bne.un.s loc_3210
0x320c  ldloc.3
0x320d  stloc.0
0x320e  br.s     loc_3218
0x3210  ldloc.2
0x3211  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3216  brtrue.s loc_31EA
0x3218  leave.s  loc_322E
0x321a  ldloc.2
0x321b  isinst   [mscorlib]System.IDisposable
0x3220  stloc.s  4
0x3222  ldloc.s  4
0x3224  brfalse.s loc_322D
0x3226  ldloc.s  4
0x3228  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x322d  endfinally
0x322e  ldloc.0
0x322f  brfalse.s loc_323C
0x3231  ldloc.0
0x3232  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x3237  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x323c  leave.s  loc_3274
0x323e  stloc.s  5
0x3240  ldloc.s  5
0x3242  ldarg.0
0x3243  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3248  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x324d  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x3252  brfalse.s loc_325D
0x3254  ldloc.s  5
0x3256  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x325b  brfalse.s loc_3272
0x325d  ldarg.0
0x325e  ldloc.s  5
0x3260  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x3265  ldloc.0
0x3266  brfalse.s loc_3272
0x3268  ldloc.0
0x3269  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x326e  brfalse.s loc_3272
0x3270  ldnull
0x3271  stloc.0
0x3272  leave.s  loc_3274
0x3274  ldloc.0
0x3275  ret
```
