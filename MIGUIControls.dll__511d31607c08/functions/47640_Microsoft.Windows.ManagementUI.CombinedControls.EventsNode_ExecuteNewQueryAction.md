# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteNewQueryAction

- ea: `0x47640`
- end: `0x477d6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteNewQueryAction`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x473f0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x15050`
- `0x1b4d0`
- `0x46130`
- `0x46520`
- `0x46680`
- `0x46b70`
- `0x46ea0`
- `0x47640`
- `0x4ae40`
- `0x4b170`
- `0x4b350`
- `0x54040`
- `0x540f0`
- `0x5a980`
- `0x5aba0`
- `0x5abd0`
- `0x5ac30`
- `0x5aca0`
- `0x5ad00`
- `0x5bb50`
- `0x5bbd0`
- `0x5bc20`
- `0x5bc80`
- `0x5bc90`
- `0x5bca0`
- `0x5bd10`
- `0x5bd20`

## string_xrefs

- `0x4769a`: `CreateView`

## pseudocode

```c

```

## disassembly

```asm
0x47640  ldc.i4.0
0x47641  stloc.0
0x47642  ldarg.0
0x47643  ldnull
0x47644  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x47649  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::.ctor()
0x4764e  stloc.2
0x4764f  ldloc.2
0x47650  ldarg.0
0x47651  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Context()
0x47656  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x4765b  ldloc.2
0x4765c  ldarg.0
0x4765d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewerRootNode()
0x47662  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::InitializeView(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode rootNode)
0x47667  ldarg.0
0x47668  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_nodeType
0x4766d  ldc.i4.1
0x4766e  beq.s    loc_47682
0x47670  ldarg.0
0x47671  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_nodeType
0x47676  ldc.i4.6
0x47677  bne.un.s loc_47699
0x47679  ldarg.0
0x4767a  call     instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x4767f  ldc.i4.5
0x47680  beq.s    loc_47699
0x47682  ldc.i4.1
0x47683  newarr   [mscorlib]System.String
0x47688  stloc.3
0x47689  ldloc.3
0x4768a  ldc.i4.0
0x4768b  ldarg.0
0x4768c  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ChannelPath()
0x47691  stelem.ref
0x47692  ldloc.2
0x47693  ldloc.3
0x47694  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_SelectedChannels(string[] value)
0x47699  ldloc.2
0x4769a  ldstr    aCreateview// "CreateView"
0x4769f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x476a4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_DialogTitle(string value)
0x476a9  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x476ae  ldloc.2
0x476af  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x476b4  stloc.1
0x476b5  ldloc.1
0x476b6  ldc.i4.1
0x476b7  bne.un   loc_477CE
0x476bc  ldnull
0x476bd  stloc.s  4
0x476bf  ldarg.0
0x476c0  ldloca.s 4
0x476c2  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& viewRootNode)
0x476c7  ldloc.s  4
0x476c9  ldc.i4.s 9
0x476cb  ldstr    aSavefilterasvi// "SaveFilterAsView"
0x476d0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x476d5  ldstr    aSelectwheresav// "SelectWhereSaveView"
0x476da  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x476df  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode root, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeType, string title, string labelText)
0x476e4  stloc.s  5
0x476e6  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x476eb  ldloc.s  5
0x476ed  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x476f2  stloc.1
0x476f3  ldc.i4.1
0x476f4  ldloc.1
0x476f5  beq.s    loc_47703
0x476f7  ldloc.s  5
0x476f9  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_FolderCreated()
0x476fe  brfalse  loc_477C7
0x47703  ldloc.s  5
0x47705  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NewFolders()
0x4770a  stloc.s  6
0x4770c  ldc.i4.0
0x4770d  stloc.s  7
0x4770f  br.s     loc_47735
0x47711  ldloc.s  6
0x47713  ldloc.s  7
0x47715  ldelem.ref
0x47716  stloc.s  8
0x47718  ldloc.s  4
0x4771a  ldloc.2
0x4771b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x47720  ldloc.s  8
0x47722  ldc.i4.1
0x47723  ldloc.s  5
0x47725  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x4772a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x4772f  ldloc.s  7
0x47731  ldc.i4.1
0x47732  add
0x47733  stloc.s  7
0x47735  ldloc.s  7
0x47737  ldloc.s  6
0x47739  ldlen
0x4773a  conv.i4
0x4773b  blt.s    loc_47711
0x4773d  ldc.i4.1
0x4773e  ldloc.1
0x4773f  bne.un   loc_477C7
0x47744  ldloc.s  5
0x47746  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x4774b  brtrue.s loc_4778B
0x4774d  ldloc.2
0x4774e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x47753  stloc.s  9
0x47755  ldloc.s  9
0x47757  ldloc.s  5
0x47759  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ViewName()
0x4775e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x47763  ldloc.s  9
0x47765  ldloc.s  5
0x47767  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x4776c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Description(string value)
0x47771  ldloc.s  4
0x47773  ldloc.s  9
0x47775  ldloc.s  5
0x47777  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ParentFolderPath()
0x4777c  ldc.i4.1
0x4777d  ldloc.s  5
0x4777f  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x47784  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x47789  br.s     loc_477BD
0x4778b  ldloc.s  5
0x4778d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x47792  ldloc.2
0x47793  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x47798  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_QueryConfiguration(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig value)
0x4779d  ldloc.s  5
0x4779f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x477a4  ldloc.s  5
0x477a6  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x477ab  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x477b0  ldarg.0
0x477b1  ldloc.s  5
0x477b3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x477b8  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x477bd  ldc.i4   0xED9
0x477c2  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x477c7  ldloc.s  5
0x477c9  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x477ce  ldloc.2
0x477cf  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x477d4  ldloc.0
0x477d5  ret
```
