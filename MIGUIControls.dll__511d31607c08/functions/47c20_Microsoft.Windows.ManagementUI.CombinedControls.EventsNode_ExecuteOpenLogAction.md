# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteOpenLogAction

- ea: `0x47c20`
- end: `0x47df5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteOpenLogAction`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x473f0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x14db0`
- `0x14e30`
- `0x15050`
- `0x1b4c0`
- `0x1b4d0`
- `0x32e00`
- `0x35f60`
- `0x46530`
- `0x46600`
- `0x46610`
- `0x46880`
- `0x46dd0`
- `0x46ea0`
- `0x47b70`
- `0x47c20`
- `0x4a800`
- `0x4b3d0`
- `0x5bb50`
- `0x5bbd0`
- `0x5bbe0`
- `0x5bc20`
- `0x5bc80`
- `0x5bc90`
- `0x5bca0`
- `0x5bd10`
- `0x5bd20`

## string_xrefs

- `0x47cc2`: `TitleOpenLogFile`

## pseudocode

```c

```

## disassembly

```asm
0x47c20  ldc.i4.0
0x47c21  stloc.0
0x47c22  ldarg.0
0x47c23  ldnull
0x47c24  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x47c29  call     string Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::OpenLog()
0x47c2e  stloc.2
0x47c2f  ldloc.2
0x47c30  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47c35  brtrue   loc_47DF3
0x47c3a  ldnull
0x47c3b  stloc.3
0x47c3c  ldarg.0
0x47c3d  ldloca.s 3
0x47c3f  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetExternalLogRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& logRootNode)
0x47c44  ldc.i4.0
0x47c45  stloc.s  4
0x47c47  ldloc.3
0x47c48  brtrue.s loc_47C54
0x47c4a  ldc.i4.1
0x47c4b  stloc.s  4
0x47c4d  ldc.i4.5
0x47c4e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x47c53  stloc.3
0x47c54  ldloc.2
0x47c55  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsExternalLogFileForwardOnly(string eventLogFile)
0x47c5a  brfalse.s loc_47CB6
0x47c5c  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::OptedIn()
0x47c61  brfalse.s loc_47C95
0x47c63  ldloc.2
0x47c64  ldstr    aEvt// "evt"
0x47c69  ldc.i4.5
0x47c6a  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47c6f  brfalse.s loc_47C7D
0x47c71  ldc.i4   0x13DE
0x47c76  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x47c7b  br.s     loc_47C95
0x47c7d  ldloc.2
0x47c7e  ldstr    aEtl// "etl"
0x47c83  ldc.i4.5
0x47c84  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47c89  brfalse.s loc_47C95
0x47c8b  ldc.i4   0x13DF
0x47c90  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x47c95  ldsfld   string [mscorlib]System.String::Empty
0x47c9a  stloc.s  6
0x47c9c  ldarg.0
0x47c9d  ldloc.2
0x47c9e  ldloca.s 6
0x47ca0  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ProcessClassicEventLogs(string incomingClassicLogName, string& convertedName)
0x47ca5  brfalse.s loc_47CC0
0x47ca7  ldloc.s  6
0x47ca9  stloc.2
0x47caa  ldc.i4   0x13E1
0x47caf  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x47cb4  br.s     loc_47CC0
0x47cb6  ldc.i4   0x13E0
0x47cbb  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x47cc0  ldloc.3
0x47cc1  ldc.i4.6
0x47cc2  ldstr    aTitleopenlogfi// "TitleOpenLogFile"
0x47cc7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x47ccc  ldstr    aSelectwheresav_0// "SelectWhereSaveExportLog"
0x47cd1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x47cd6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode root, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeType, string title, string labelText)
0x47cdb  stloc.s  5
0x47cdd  ldloc.s  5
0x47cdf  ldloc.2
0x47ce0  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x47ce5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_ViewName(string value)
0x47cea  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x47cef  ldloc.s  5
0x47cf1  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x47cf6  stloc.1
0x47cf7  ldc.i4.1
0x47cf8  ldloc.1
0x47cf9  beq.s    loc_47D07
0x47cfb  ldloc.s  5
0x47cfd  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_FolderCreated()
0x47d02  brfalse  loc_47DEC
0x47d07  ldloc.s  5
0x47d09  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NewFolders()
0x47d0e  stloc.s  7
0x47d10  ldc.i4.0
0x47d11  stloc.s  8
0x47d13  br.s     loc_47D40
0x47d15  ldloc.s  7
0x47d17  ldloc.s  8
0x47d19  ldelem.ref
0x47d1a  stloc.s  9
0x47d1c  ldloc.3
0x47d1d  ldsfld   string [mscorlib]System.String::Empty
0x47d22  ldsfld   string [mscorlib]System.String::Empty
0x47d27  ldloc.s  9
0x47d29  ldloc.s  5
0x47d2b  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x47d30  ldsfld   string [mscorlib]System.String::Empty
0x47d35  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddExternalLogNode(string filePath, string name, string nodePath, bool allUsersExternalLog, string description)
0x47d3a  ldloc.s  8
0x47d3c  ldc.i4.1
0x47d3d  add
0x47d3e  stloc.s  8
0x47d40  ldloc.s  8
0x47d42  ldloc.s  7
0x47d44  ldlen
0x47d45  conv.i4
0x47d46  blt.s    loc_47D15
0x47d48  ldloc.1
0x47d49  ldc.i4.1
0x47d4a  bne.un.s loc_47DA7
0x47d4c  ldloc.s  5
0x47d4e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x47d53  brtrue.s loc_47D7A
0x47d55  ldloc.3
0x47d56  ldloc.2
0x47d57  ldloc.s  5
0x47d59  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ViewName()
0x47d5e  ldloc.s  5
0x47d60  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ParentFolderPath()
0x47d65  ldloc.s  5
0x47d67  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x47d6c  ldloc.s  5
0x47d6e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x47d73  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddExternalLogNode(string filePath, string name, string nodePath, bool allUsersExternalLog, string description)
0x47d78  br.s     loc_47DA7
0x47d7a  ldloc.s  5
0x47d7c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x47d81  ldloc.2
0x47d82  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_LogFilePath(string value)
0x47d87  ldloc.s  5
0x47d89  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x47d8e  ldloc.s  5
0x47d90  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x47d95  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x47d9a  ldarg.0
0x47d9b  ldloc.s  5
0x47d9d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x47da2  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x47da7  ldloc.s  4
0x47da9  brfalse.s loc_47DEC
0x47dab  ldloc.3
0x47dac  ldc.i4.3
0x47dad  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x47db2  ldarg.0
0x47db3  stloc.s  0xA
0x47db5  br.s     loc_47DC0
0x47db7  ldloc.s  0xA
0x47db9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ParentNode()
0x47dbe  stloc.s  0xA
0x47dc0  ldloc.s  0xA
0x47dc2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ParentNode()
0x47dc7  brtrue.s loc_47DB7
0x47dc9  ldloc.3
0x47dca  ldloc.s  0xA
0x47dcc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x47dd1  ldloc.s  0xA
0x47dd3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x47dd8  ldloc.3
0x47dd9  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x47dde  ldloc.3
0x47ddf  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x47de4  ldloc.s  0xA
0x47de6  ldc.i4.1
0x47de7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x47dec  ldloc.s  5
0x47dee  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x47df3  ldloc.0
0x47df4  ret
```
