# Microsoft.EventViewer.SnapIn.ViewerRootNode::DeleteNode

- ea: `0x38f0`
- end: `0x39d3`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::DeleteNode`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1cc0`
- `0x3d60`

## callees

- `0x2280`
- `0x38f0`
- `0xa570`
- `0xa590`
- `0xa7b0`
- `0xaaa0`

## pseudocode

```c

```

## disassembly

```asm
0x38f0  ldarg.0
0x38f1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x38f6  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_CanDelete()
0x38fb  brfalse  loc_39D2
0x3900  ldc.i4.1
0x3901  stloc.0
0x3902  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteFolderConfirmation()
0x3907  stloc.1
0x3908  ldarg.0
0x3909  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x390e  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x3913  brtrue.s loc_3930
0x3915  ldnull
0x3916  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteConfirmation()
0x391b  ldc.i4.1
0x391c  newarr   [mscorlib]System.Object
0x3921  dup
0x3922  ldc.i4.0
0x3923  ldarg.0
0x3924  call     instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x3929  stelem.ref
0x392a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x392f  stloc.1
0x3930  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x3935  stloc.2
0x3936  ldloc.2
0x3937  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x393c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x3941  ldloc.2
0x3942  ldloc.1
0x3943  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x3948  ldloc.2
0x3949  ldc.i4.4
0x394a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons)
0x394f  ldloc.2
0x3950  ldc.i4.s 0x20
0x3952  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x3957  ldarg.0
0x3958  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x395d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x3962  ldloc.2
0x3963  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x3968  ldc.i4.7
0x3969  bne.un.s loc_396D
0x396b  ldc.i4.0
0x396c  stloc.0
0x396d  ldloc.0
0x396e  brfalse.s loc_39D2
0x3970  ldarg.0
0x3971  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3976  ldc.i4.s 0xD
0x3978  ldc.i4.0
0x3979  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x397e  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x3983  brfalse.s loc_39D2
0x3985  ldarg.0
0x3986  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x398b  brfalse.s loc_39A0
0x398d  ldarg.0
0x398e  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x3993  ldc.i4.s 0xD
0x3995  ldc.i4.0
0x3996  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x399b  callvirt instance void ViewerScopeNodeChanged::Invoke(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x39a0  ldarg.0
0x39a1  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x39a6  isinst   Microsoft.EventViewer.SnapIn.MMCEventsNode
0x39ab  stloc.3
0x39ac  ldarg.0
0x39ad  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x39b2  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x39b7  ldarg.0
0x39b8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Remove(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x39bd  ldarg.0
0x39be  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x39c3  ldc.i4.1
0x39c4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x39c9  ldloc.3
0x39ca  brfalse.s loc_39D2
0x39cc  ldloc.3
0x39cd  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView()
0x39d2  ret
```
