# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateActions

- ea: `0x97f0`
- end: `0x999d`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateActions`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1860`
- `0x3be0`
- `0x7cb0`
- `0x7cf0`
- `0x8120`
- `0x91b0`
- `0x97f0`
- `0x9c40`

## pseudocode

```c

```

## disassembly

```asm
0x97f0  ldarg.0
0x97f1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::subscriptionControl
0x97f6  brfalse.s loc_9800
0x97f8  ldarg.0
0x97f9  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x97fe  brtrue.s loc_9801
0x9800  ret
0x9801  nop
0x9802  ldarg.0
0x9803  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9808  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x980d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::BeginUpdates()
0x9812  ldarg.0
0x9813  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::subscriptionControl
0x9818  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl::get_SubscriptionCount()
0x981d  ldc.i4.0
0x981e  ble      loc_98F9
0x9823  ldarg.0
0x9824  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::UpdateActions()
0x9829  ldarg.0
0x982a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::subscriptionControl
0x982f  callvirt instance class [mscorlib]System.Collections.ICollection [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl::get_Actions()
0x9834  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9839  stloc.0
0x983a  br.s     loc_984F
0x983c  ldloc.0
0x983d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9842  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x9847  stloc.1
0x9848  ldarg.0
0x9849  ldloc.1
0x984a  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x984f  ldloc.0
0x9850  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9855  brtrue.s loc_983C
0x9857  leave.s  loc_986A
0x9859  ldloc.0
0x985a  isinst   [mscorlib]System.IDisposable
0x985f  stloc.2
0x9860  ldloc.2
0x9861  brfalse.s loc_9869
0x9863  ldloc.2
0x9864  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9869  endfinally
0x986a  ldarg.0
0x986b  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9870  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x9875  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Clear()
0x987a  ldarg.0
0x987b  ldfld    string Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionDisplay
0x9880  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9885  brtrue.s loc_989D
0x9887  ldarg.0
0x9888  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x988d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x9892  ldarg.0
0x9893  ldfld    string Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionDisplay
0x9898  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x989d  ldarg.0
0x989e  ldfld    object Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionData
0x98a3  brfalse.s loc_98FF
0x98a5  ldarg.0
0x98a6  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x98ab  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x98b0  ldarg.0
0x98b1  ldfld    object Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionData
0x98b6  ldc.i4.0
0x98b7  ldnull
0x98b8  ldnull
0x98b9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Update(object, bool, valuetype [mscorlib]System.Guid[], class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.WritableSharedData)
0x98be  ldarg.0
0x98bf  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x98c4  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x98c9  ldarg.0
0x98ca  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x98cf  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x98d4  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_HelpTopic()
0x98d9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_HelpTopic(string)
0x98de  ldarg.0
0x98df  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x98e4  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x98e9  dup
0x98ea  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_EnabledStandardVerbs()
0x98ef  ldc.i4.s 0x40
0x98f1  or
0x98f2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x98f7  br.s     loc_98FF
0x98f9  ldarg.0
0x98fa  call     instance void Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::ClearActions()
0x98ff  ldarg.0
0x9900  ldc.i4.1
0x9901  stfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::actionsInitialized
0x9906  ldarg.0
0x9907  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x990c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x9911  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::EndUpdates()
0x9916  leave    loc_999C
0x991b  stloc.3
0x991c  ldarg.0
0x991d  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9922  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x9927  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x992c  stloc.s  4
0x992e  ldloc.3
0x992f  ldloc.s  4
0x9931  ldarg.0
0x9932  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9937  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x993c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x9941  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class Microsoft.EventViewer.SnapIn.ViewerRootNode viewerNode, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x9946  brfalse.s loc_9950
0x9948  ldloc.3
0x9949  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x994e  brfalse.s loc_999A
0x9950  ldloc.s  4
0x9952  brfalse.s loc_999A
0x9954  ldloc.s  4
0x9956  ldloc.3
0x9957  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x995c  ldloc.s  4
0x995e  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x9963  brtrue.s loc_999A
0x9965  ldarg.0
0x9966  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x996b  ldarg.0
0x996c  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9971  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x9976  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x997b  ldloc.s  4
0x997d  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x9982  brtrue.s loc_999A
0x9984  ldarg.0
0x9985  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x998a  ldarg.0
0x998b  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9990  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x9995  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x999a  leave.s  loc_999C
0x999c  ret
```
