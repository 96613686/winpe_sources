# Microsoft.EventViewer.SnapIn.EventViewerHomepage::FindNodeWithSameQueryOrCreate

- ea: `0x7810`
- end: `0x7947`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::FindNodeWithSameQueryOrCreate`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x70f0`

## callees

- `0x1860`
- `0x1a00`
- `0x3050`
- `0x3530`
- `0x3be0`
- `0x3d70`
- `0x7810`
- `0x9120`

## pseudocode

```c

```

## disassembly

```asm
0x7810  ldarg.0
0x7811  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x7816  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x781b  dup
0x781c  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x7821  callvirt instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetViewsRootNode()
0x7826  stloc.0
0x7827  ldloc.0
0x7828  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x782d  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x7832  ldarg.1
0x7833  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventQuery [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Query()
0x7838  pop
0x7839  ldloc.0
0x783a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x783f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x7844  stloc.2
0x7845  br.s     loc_789A
0x7847  ldloc.2
0x7848  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x784d  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0x7852  stloc.3
0x7853  ldloc.3
0x7854  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x7859  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsHomePageNode()
0x785e  brfalse.s loc_789A
0x7860  ldloc.3
0x7861  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x7866  ldarg.1
0x7867  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x786c  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string)
0x7871  ldarg.1
0x7872  ldloc.3
0x7873  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x7878  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x787d  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string)
0x7882  ldloc.3
0x7883  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x7888  ldarg.1
0x7889  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_QueryConfiguration(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig)
0x788e  ldarg.0
0x788f  ldloc.3
0x7890  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x7895  leave    loc_7946
0x789a  ldloc.2
0x789b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x78a0  brtrue.s loc_7847
0x78a2  leave.s  loc_78B8
0x78a4  ldloc.2
0x78a5  isinst   [mscorlib]System.IDisposable
0x78aa  stloc.s  4
0x78ac  ldloc.s  4
0x78ae  brfalse.s loc_78B7
0x78b0  ldloc.s  4
0x78b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x78b7  endfinally
0x78b8  ldloc.0
0x78b9  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x78be  ldarg.1
0x78bf  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddHomePageView(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig)
0x78c4  ldarg.0
0x78c5  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x78ca  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x78cf  callvirt instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes()
0x78d4  stloc.1
0x78d5  ldarg.0
0x78d6  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x78db  ldc.i4.1
0x78dc  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x78e1  ldloc.1
0x78e2  brfalse.s loc_78EB
0x78e4  ldarg.0
0x78e5  ldloc.1
0x78e6  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x78eb  leave.s  loc_7946
0x78ed  stloc.s  5
0x78ef  ldloc.s  5
0x78f1  ldarg.0
0x78f2  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x78f7  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x78fc  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x7901  brfalse.s loc_790C
0x7903  ldloc.s  5
0x7905  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x790a  brfalse.s loc_7944
0x790c  ldarg.0
0x790d  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x7912  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x7917  stloc.s  6
0x7919  ldloc.s  6
0x791b  brfalse.s loc_7944
0x791d  ldloc.s  6
0x791f  ldloc.s  5
0x7921  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x7926  ldloc.s  6
0x7928  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x792d  brtrue.s loc_7944
0x792f  ldloc.s  6
0x7931  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x7936  brtrue.s loc_7944
0x7938  ldarg.0
0x7939  ldarg.0
0x793a  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x793f  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x7944  leave.s  loc_7946
0x7946  ret
```
