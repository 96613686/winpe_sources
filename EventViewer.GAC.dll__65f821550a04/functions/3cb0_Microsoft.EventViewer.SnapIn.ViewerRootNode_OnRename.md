# Microsoft.EventViewer.SnapIn.ViewerRootNode::OnRename

- ea: `0x3cb0`
- end: `0x3d5d`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::OnRename`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1a00`
- `0x2280`
- `0x3cb0`
- `0x8690`
- `0xa730`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x3cb0  ldc.i4.1
0x3cb1  newarr   [mscorlib]System.Char
0x3cb6  dup
0x3cb7  ldc.i4.0
0x3cb8  ldc.i4.s 0x20
0x3cba  stelem.i2
0x3cbb  stloc.0
0x3cbc  ldarg.1
0x3cbd  ldloc.0
0x3cbe  callvirt instance string [mscorlib]System.String::Trim(char[])
0x3cc3  starg.s  1
0x3cc5  ldarg.1
0x3cc6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3ccb  brfalse.s loc_3CE8
0x3ccd  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x3cd2  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_NodeNameError()
0x3cd7  ldarg.0
0x3cd8  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3cdd  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x3ce2  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayError(string caption, string text, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x3ce7  ret
0x3ce8  ldarg.0
0x3ce9  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3cee  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::CanRename()
0x3cf3  brfalse.s loc_3D50
0x3cf5  ldarg.0
0x3cf6  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3cfb  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x3d00  ldarg.1
0x3d01  ldc.i4.5
0x3d02  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3d07  brfalse.s loc_3D5C
0x3d09  ldarg.0
0x3d0a  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x3d0f  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3d14  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x3d19  ldarg.0
0x3d1a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3d1f  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x3d24  ldarg.1
0x3d25  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ModifyName(string, string)
0x3d2a  brfalse.s loc_3D5C
0x3d2c  ldarg.0
0x3d2d  ldarg.1
0x3d2e  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x3d33  ldarg.0
0x3d34  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x3d39  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3d3e  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView()
0x3d43  ldarg.0
0x3d44  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3d49  ldc.i4.1
0x3d4a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x3d4f  ret
0x3d50  ldarg.0
0x3d51  ldarg.0
0x3d52  call     instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x3d57  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x3d5c  ret
```
