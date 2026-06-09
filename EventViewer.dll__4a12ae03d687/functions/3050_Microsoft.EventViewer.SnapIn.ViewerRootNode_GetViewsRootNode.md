# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetViewsRootNode

- ea: `0x3050`
- end: `0x3101`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetViewsRootNode`
- size: `177`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9e0`
- `0x1cc0`
- `0x1e70`
- `0x2050`
- `0x37c0`
- `0x4b00`
- `0x7810`

## callees

- `0x1860`
- `0x1ae0`
- `0x3050`
- `0x3be0`
- `0x3d70`
- `0x9120`

## pseudocode

```c

```

## disassembly

```asm
0x3050  ldnull
0x3051  stloc.0
0x3052  ldarg.0
0x3053  call     instance class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventViewerRootNode()
0x3058  stloc.1
0x3059  ldloc.1
0x305a  brfalse.s loc_30C7
0x305c  ldloc.1
0x305d  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x3062  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x3067  ldloc.1
0x3068  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x306d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3072  stloc.2
0x3073  br.s     loc_309B
0x3075  ldloc.2
0x3076  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x307b  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x3080  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3085  stloc.3
0x3086  ldloc.3
0x3087  brfalse.s loc_309B
0x3089  ldloc.3
0x308a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x308f  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x3094  ldc.i4.7
0x3095  bne.un.s loc_309B
0x3097  ldloc.3
0x3098  stloc.0
0x3099  br.s     loc_30A3
0x309b  ldloc.2
0x309c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30a1  brtrue.s loc_3075
0x30a3  leave.s  loc_30B9
0x30a5  ldloc.2
0x30a6  isinst   [mscorlib]System.IDisposable
0x30ab  stloc.s  4
0x30ad  ldloc.s  4
0x30af  brfalse.s loc_30B8
0x30b1  ldloc.s  4
0x30b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30b8  endfinally
0x30b9  ldloc.0
0x30ba  brfalse.s loc_30C7
0x30bc  ldloc.0
0x30bd  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x30c2  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x30c7  leave.s  loc_30FF
0x30c9  stloc.s  5
0x30cb  ldloc.s  5
0x30cd  ldarg.0
0x30ce  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x30d3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x30d8  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x30dd  brfalse.s loc_30E8
0x30df  ldloc.s  5
0x30e1  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x30e6  brfalse.s loc_30FD
0x30e8  ldarg.0
0x30e9  ldloc.s  5
0x30eb  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x30f0  ldloc.0
0x30f1  brfalse.s loc_30FD
0x30f3  ldloc.0
0x30f4  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x30f9  brfalse.s loc_30FD
0x30fb  ldnull
0x30fc  stloc.0
0x30fd  leave.s  loc_30FF
0x30ff  ldloc.0
0x3100  ret
```
