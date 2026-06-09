# Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateActions

- ea: `0x57a0`
- end: `0x595b`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateActions`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1860`
- `0x3be0`
- `0x57a0`
- `0x7cb0`
- `0x7cf0`
- `0x8120`
- `0x91b0`

## pseudocode

```c

```

## disassembly

```asm
0x57a0  ldarg.0
0x57a1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x57a6  brfalse.s loc_57B0
0x57a8  ldarg.0
0x57a9  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x57ae  brtrue.s loc_57B1
0x57b0  ret
0x57b1  nop
0x57b2  ldarg.0
0x57b3  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x57b8  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x57bd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::BeginUpdates()
0x57c2  ldarg.0
0x57c3  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::UpdateActions()
0x57c8  ldarg.0
0x57c9  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x57ce  callvirt instance class [mscorlib]System.Collections.ICollection [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_Actions()
0x57d3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x57d8  stloc.0
0x57d9  br.s     loc_57EE
0x57db  ldloc.0
0x57dc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57e1  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x57e6  stloc.1
0x57e7  ldarg.0
0x57e8  ldloc.1
0x57e9  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x57ee  ldloc.0
0x57ef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57f4  brtrue.s loc_57DB
0x57f6  leave.s  loc_5809
0x57f8  ldloc.0
0x57f9  isinst   [mscorlib]System.IDisposable
0x57fe  stloc.2
0x57ff  ldloc.2
0x5800  brfalse.s loc_5808
0x5802  ldloc.2
0x5803  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5808  endfinally
0x5809  ldarg.0
0x580a  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x580f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x5814  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Clear()
0x5819  ldarg.0
0x581a  ldfld    string Microsoft.EventViewer.SnapIn.MMCEventsResultView::selectionDisplay
0x581f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5824  brtrue.s loc_583C
0x5826  ldarg.0
0x5827  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x582c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x5831  ldarg.0
0x5832  ldfld    string Microsoft.EventViewer.SnapIn.MMCEventsResultView::selectionDisplay
0x5837  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x583c  ldarg.0
0x583d  ldfld    object Microsoft.EventViewer.SnapIn.MMCEventsResultView::selectionData
0x5842  brfalse.s loc_589D
0x5844  ldarg.0
0x5845  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x584a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x584f  ldarg.0
0x5850  ldfld    object Microsoft.EventViewer.SnapIn.MMCEventsResultView::selectionData
0x5855  ldarg.0
0x5856  ldfld    bool Microsoft.EventViewer.SnapIn.MMCEventsResultView::multiSelected
0x585b  ldnull
0x585c  ldnull
0x585d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Update(object, bool, valuetype [mscorlib]System.Guid[], class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.WritableSharedData)
0x5862  ldarg.0
0x5863  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5868  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x586d  ldarg.0
0x586e  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5873  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5878  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_HelpTopic()
0x587d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_HelpTopic(string)
0x5882  ldarg.0
0x5883  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5888  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x588d  dup
0x588e  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_EnabledStandardVerbs()
0x5893  ldc.i4.s 0x40
0x5895  or
0x5896  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x589b  br.s     loc_58B6
0x589d  ldarg.0
0x589e  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x58a3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x58a8  dup
0x58a9  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_EnabledStandardVerbs()
0x58ae  ldc.i4.s 0x40
0x58b0  or
0x58b1  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x58b6  ldarg.0
0x58b7  ldnull
0x58b8  stfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IEventBase Microsoft.EventViewer.SnapIn.MMCEventsResultView::curEventSelected
0x58bd  ldarg.0
0x58be  ldc.i4.1
0x58bf  stfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::actionsInitialized
0x58c4  ldarg.0
0x58c5  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x58ca  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x58cf  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::EndUpdates()
0x58d4  leave    loc_595A
0x58d9  stloc.3
0x58da  ldarg.0
0x58db  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x58e0  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x58e5  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x58ea  stloc.s  4
0x58ec  ldloc.3
0x58ed  ldloc.s  4
0x58ef  ldarg.0
0x58f0  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x58f5  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x58fa  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x58ff  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class Microsoft.EventViewer.SnapIn.ViewerRootNode viewerNode, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x5904  brfalse.s loc_590E
0x5906  ldloc.3
0x5907  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x590c  brfalse.s loc_5958
0x590e  ldloc.s  4
0x5910  brfalse.s loc_5958
0x5912  ldloc.s  4
0x5914  ldloc.3
0x5915  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x591a  ldloc.s  4
0x591c  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x5921  brtrue.s loc_5958
0x5923  ldarg.0
0x5924  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5929  ldarg.0
0x592a  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x592f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5934  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x5939  ldloc.s  4
0x593b  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x5940  brtrue.s loc_5958
0x5942  ldarg.0
0x5943  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5948  ldarg.0
0x5949  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x594e  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5953  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x5958  leave.s  loc_595A
0x595a  ret
```
