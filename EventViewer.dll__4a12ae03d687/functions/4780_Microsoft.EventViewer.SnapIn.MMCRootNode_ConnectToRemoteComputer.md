# Microsoft.EventViewer.SnapIn.MMCRootNode::ConnectToRemoteComputer

- ea: `0x4780`
- end: `0x493d`
- name: `Microsoft.EventViewer.SnapIn.MMCRootNode::ConnectToRemoteComputer`
- size: `445`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x4e0`
- `0x7b0`
- `0x8d0`

## callees

- `0x360`
- `0x1a00`
- `0x1aa0`
- `0x1b40`
- `0x1ba0`
- `0x3be0`
- `0x4690`
- `0x4780`
- `0xa950`
- `0xab00`

## pseudocode

```c

```

## disassembly

```asm
0x4780  ldarg.0
0x4781  ldstr    aSetRemotemachi// "set_RemoteMachineName"
0x4786  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object, string)
0x478b  ldc.i4.1
0x478c  stloc.0
0x478d  ldarg.0
0x478e  ldsfld   string [mscorlib]System.String::Empty
0x4793  stfld    string Microsoft.EventViewer.SnapIn.MMCRootNode::legacyMachine
0x4798  ldarg.0
0x4799  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x479e  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_RemoteComputer()
0x47a3  ldarg.1
0x47a4  ldc.i4.4
0x47a5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x47aa  brfalse  loc_4889
0x47af  ldarg.0
0x47b0  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ConnectionStatus()
0x47b5  ldc.i4.3
0x47b6  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SetSyncStatus(string statusText, int32 percent)
0x47bb  ldarg.0
0x47bc  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x47c1  ldarg.1
0x47c2  ldarg.2
0x47c3  ldarg.3
0x47c4  ldarg.s  4
0x47c6  ldarg.s  5
0x47c8  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ConnectToRemoteComputer(string, string, string, class [mscorlib]System.Security.SecureString, bool)
0x47cd  pop
0x47ce  ldarg.0
0x47cf  ldarg.0
0x47d0  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x47d5  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x47da  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x47df  ldarg.0
0x47e0  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ConnectionStatus()
0x47e5  ldc.i4.s 0x50
0x47e7  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SetSyncStatus(string statusText, int32 percent)
0x47ec  ldnull
0x47ed  stloc.1
0x47ee  ldarg.0
0x47ef  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x47f4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x47f9  ldc.i4.0
0x47fa  ble.s    loc_480E
0x47fc  ldarg.0
0x47fd  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x4802  ldc.i4.0
0x4803  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::get_Item(int32)
0x4808  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormViewDescription
0x480d  stloc.1
0x480e  ldloc.1
0x480f  brfalse.s loc_482B
0x4811  ldloc.1
0x4812  brfalse.s loc_4839
0x4814  ldloc.1
0x4815  callvirt instance class [mscorlib]System.Type [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormViewDescription::get_ControlType()
0x481a  ldtoken  [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl
0x481f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4824  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4829  brfalse.s loc_4839
0x482b  ldarg.0
0x482c  ldc.i4.1
0x482d  call     instance void Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage(bool homepage)
0x4832  ldarg.0
0x4833  ldarg.0
0x4834  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x4839  ldarg.0
0x483a  ldfld    bool Microsoft.EventViewer.SnapIn.MMCRootNode::failed
0x483f  brfalse.s loc_485B
0x4841  ldarg.0
0x4842  call     instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x4847  ldc.i4.s 0xC
0x4849  ldc.i4.0
0x484a  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x484f  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x4854  pop
0x4855  ldarg.0
0x4856  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::InitializeNode()
0x485b  ldarg.0
0x485c  ldfld    class ViewerContextChanged Microsoft.EventViewer.SnapIn.MMCRootNode::ContextChanged
0x4861  brfalse.s loc_486E
0x4863  ldarg.0
0x4864  ldfld    class ViewerContextChanged Microsoft.EventViewer.SnapIn.MMCRootNode::ContextChanged
0x4869  callvirt instance void ViewerContextChanged::Invoke()
0x486e  ldarg.0
0x486f  ldc.i4.0
0x4870  stfld    bool Microsoft.EventViewer.SnapIn.MMCRootNode::failed
0x4875  ldarg.0
0x4876  ldc.i4.0
0x4877  stfld    bool Microsoft.EventViewer.SnapIn.ViewerRootNode::expanded
0x487c  ldarg.0
0x487d  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x4882  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x4887  br.s     loc_48A2
0x4889  ldarg.s  5
0x488b  brtrue.s loc_48A2
0x488d  ldarg.0
0x488e  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x4893  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4898  ldc.i4.0
0x4899  ble.s    loc_48A2
0x489b  ldarg.0
0x489c  ldc.i4.1
0x489d  stfld    bool Microsoft.EventViewer.SnapIn.ViewerRootNode::expanded
0x48a2  leave.s  loc_4923
0x48a4  pop
0x48a5  ldarg.0
0x48a6  ldc.i4.1
0x48a7  stfld    bool Microsoft.EventViewer.SnapIn.MMCRootNode::failed
0x48ac  ldc.i4.0
0x48ad  stloc.0
0x48ae  ldarg.0
0x48af  ldc.i4.1
0x48b0  stfld    bool Microsoft.EventViewer.SnapIn.ViewerRootNode::expanded
0x48b5  leave.s  loc_4923
0x48b7  pop
0x48b8  ldarg.0
0x48b9  ldarg.0
0x48ba  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x48bf  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x48c4  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x48c9  ldarg.0
0x48ca  ldarg.1
0x48cb  stfld    string Microsoft.EventViewer.SnapIn.MMCRootNode::legacyMachine
0x48d0  ldarg.0
0x48d1  ldc.i4.0
0x48d2  call     instance void Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage(bool homepage)
0x48d7  ldarg.0
0x48d8  ldarg.0
0x48d9  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x48de  ldc.i4.1
0x48df  stloc.0
0x48e0  leave.s  loc_4923
0x48e2  stloc.2
0x48e3  ldarg.0
0x48e4  ldc.i4.1
0x48e5  stfld    bool Microsoft.EventViewer.SnapIn.MMCRootNode::failed
0x48ea  ldc.i4.0
0x48eb  stloc.0
0x48ec  ldarg.0
0x48ed  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x48f2  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x48f7  stloc.3
0x48f8  ldloc.3
0x48f9  brfalse.s loc_4907
0x48fb  ldloc.3
0x48fc  ldloc.2
0x48fd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4902  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::set_ErrorMessage(string value)
0x4907  ldarg.s  5
0x4909  brfalse.s loc_4921
0x490b  ldloc.2
0x490c  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x4911  brfalse.s loc_491A
0x4913  ldarg.0
0x4914  ldloc.2
0x4915  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x491a  ldarg.0
0x491b  ldc.i4.1
0x491c  stfld    bool Microsoft.EventViewer.SnapIn.ViewerRootNode::expanded
0x4921  leave.s  loc_4923
0x4923  ldarg.0
0x4924  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ConnectionStatus()
0x4929  ldc.i4.s 0x64
0x492b  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SetSyncStatus(string statusText, int32 percent)
0x4930  ldarg.0
0x4931  ldstr    aSetRemotemachi// "set_RemoteMachineName"
0x4936  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object, string)
0x493b  ldloc.0
0x493c  ret
```
