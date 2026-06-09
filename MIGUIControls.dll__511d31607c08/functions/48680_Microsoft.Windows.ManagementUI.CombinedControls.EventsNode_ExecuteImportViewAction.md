# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteImportViewAction

- ea: `0x48680`
- end: `0x48803`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteImportViewAction`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x473f0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x15040`
- `0x15050`
- `0x1b4d0`
- `0x38880`
- `0x38890`
- `0x47000`
- `0x48680`
- `0x4ae40`
- `0x4b000`
- `0x4b350`
- `0x4bb30`
- `0x53a10`
- `0x5bb50`
- `0x5bbd0`
- `0x5bbe0`
- `0x5bc20`
- `0x5bc30`
- `0x5bc80`
- `0x5bc90`
- `0x5bca0`
- `0x5bd10`
- `0x5bd20`

## string_xrefs

- `0x48690`: `EventViewFileExtension`

## pseudocode

```c

```

## disassembly

```asm
0x48680  ldc.i4.0
0x48681  stloc.0
0x48682  ldarg.0
0x48683  ldnull
0x48684  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x48689  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x4868e  stloc.2
0x4868f  ldloc.2
0x48690  ldstr    aEventviewfilee// "EventViewFileExtension"
0x48695  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4869a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x4869f  ldloc.2
0x486a0  ldc.i4.1
0x486a1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x486a6  ldloc.2
0x486a7  ldc.i4.1
0x486a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x486ad  ldloc.2
0x486ae  call     string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_CurrentDirectory()
0x486b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x486b8  ldloc.2
0x486b9  ldstr    aImportviewdial// "ImportViewDialogTitle"
0x486be  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x486c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Title(string)
0x486c8  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x486cd  ldloc.2
0x486ce  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.CommonDialog dlg)
0x486d3  stloc.1
0x486d4  ldloc.1
0x486d5  ldc.i4.1
0x486d6  bne.un   loc_48801
0x486db  ldloc.2
0x486dc  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x486e1  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x486e6  call     void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_CurrentDirectory(string value)
0x486eb  ldnull
0x486ec  stloc.3
0x486ed  ldarg.0
0x486ee  ldloca.s 3
0x486f0  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& viewRootNode)
0x486f5  ldloc.3
0x486f6  brfalse  loc_48801
0x486fb  ldloc.3
0x486fc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InsertChildren()
0x48701  ldsfld   string [mscorlib]System.String::Empty
0x48706  stloc.s  4
0x48708  ldsfld   string [mscorlib]System.String::Empty
0x4870d  stloc.s  5
0x4870f  ldloc.2
0x48710  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x48715  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x4871a  ldloca.s 4
0x4871c  ldloca.s 5
0x4871e  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetQueryNameAndDescription(class [mscorlib]System.IO.FileInfo fileInfo, [out] string& viewName, [out] string& viewDesc)
0x48723  ldloc.3
0x48724  ldc.i4.s 9
0x48726  ldstr    aImportviewfile// "ImportViewFile"
0x4872b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48730  ldstr    aSelectwheresav// "SelectWhereSaveView"
0x48735  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4873a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode root, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeType, string title, string labelText)
0x4873f  stloc.s  6
0x48741  ldloc.s  6
0x48743  ldloc.s  4
0x48745  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_ViewName(string value)
0x4874a  ldloc.s  6
0x4874c  ldloc.s  5
0x4874e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_Description(string value)
0x48753  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x48758  ldloc.s  6
0x4875a  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x4875f  stloc.1
0x48760  ldc.i4.1
0x48761  ldloc.1
0x48762  beq.s    loc_48770
0x48764  ldloc.s  6
0x48766  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_FolderCreated()
0x4876b  brfalse  loc_487FA
0x48770  ldc.i4.1
0x48771  stloc.0
0x48772  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x48777  stloc.s  7
0x48779  ldloc.s  6
0x4877b  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NewFolders()
0x48780  stloc.s  8
0x48782  ldc.i4.0
0x48783  stloc.s  9
0x48785  br.s     loc_487A6
0x48787  ldloc.s  8
0x48789  ldloc.s  9
0x4878b  ldelem.ref
0x4878c  stloc.s  0xA
0x4878e  ldloc.3
0x4878f  ldloc.s  7
0x48791  ldloc.s  0xA
0x48793  ldc.i4.1
0x48794  ldloc.s  6
0x48796  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x4879b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x487a0  ldloc.s  9
0x487a2  ldc.i4.1
0x487a3  add
0x487a4  stloc.s  9
0x487a6  ldloc.s  9
0x487a8  ldloc.s  8
0x487aa  ldlen
0x487ab  conv.i4
0x487ac  blt.s    loc_48787
0x487ae  ldc.i4.1
0x487af  ldloc.1
0x487b0  bne.un.s loc_487FA
0x487b2  ldarg.0
0x487b3  ldloc.s  6
0x487b5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x487ba  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x487bf  ldloc.3
0x487c0  ldloc.2
0x487c1  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x487c6  ldloc.s  6
0x487c8  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ParentFolderPath()
0x487cd  ldc.i4.1
0x487ce  ldloc.s  6
0x487d0  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x487d5  ldloc.s  6
0x487d7  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ViewName()
0x487dc  ldloc.s  6
0x487de  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x487e3  ldloc.s  6
0x487e5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x487ea  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(string configFile, string path, bool customView, bool allUserQuery, string viewName, string description, class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode existingNode)
0x487ef  stloc.0
0x487f0  ldc.i4   0xEE4
0x487f5  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x487fa  ldloc.s  6
0x487fc  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x48801  ldloc.0
0x48802  ret
```
