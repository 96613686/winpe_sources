# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ConnectToRemoteComputer

- ea: `0x6f0`
- end: `0x7a4`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ConnectToRemoteComputer`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6d0`
- `0x2260`

## callees

- `0x6f0`
- `0x7b0`
- `0x8690`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldc.i4.0
0x6f1  stloc.0
0x6f2  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::.ctor()
0x6f7  stloc.1
0x6f8  ldloc.1
0x6f9  ldc.i4.0
0x6fa  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::set_OpenedBy(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ApplicationEnum)
0x6ff  ldloc.1
0x700  ldsfld   string [mscorlib]System.String::Empty
0x705  ldarg.1
0x706  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::Initialize(string, bool)
0x70b  ldloc.1
0x70c  ldstr    aEventviewercon// "EventViewerConnectToRemoteDialogDesc"
0x711  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x716  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::set_DescriptionText(string)
0x71b  ldloc.1
0x71c  ldarg.2
0x71d  ldc.i4.0
0x71e  ceq
0x720  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::set_ShowErrorOnOk(bool)
0x725  ldarg.0
0x726  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x72b  ldloc.1
0x72c  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form)
0x731  ldc.i4.1
0x732  bne.un.s loc_7A2
0x734  call     void [System.Windows.Forms]System.Windows.Forms.Application::DoEvents()
0x739  ldsfld   string [mscorlib]System.String::Empty
0x73e  stloc.2
0x73f  ldsfld   string [mscorlib]System.String::Empty
0x744  stloc.3
0x745  ldarg.0
0x746  ldloc.1
0x747  ldloca.s 3
0x749  ldloca.s 2
0x74b  call     instance bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ConnectToRemoteComputerHandler(object sender, [out] string& errorString, [out] string& caption)
0x750  brtrue.s loc_769
0x752  ldloc.3
0x753  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x758  brtrue.s loc_79B
0x75a  ldloc.2
0x75b  ldloc.3
0x75c  ldarg.0
0x75d  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x762  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayError(string caption, string text, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x767  br.s     loc_79B
0x769  ldc.i4.1
0x76a  stloc.0
0x76b  ldloc.1
0x76c  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_IsAnotherUser()
0x771  brfalse.s loc_77D
0x773  ldc.i4   0xED6
0x778  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint)
0x77d  ldloc.1
0x77e  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_IsLocalComputer()
0x783  brfalse.s loc_791
0x785  ldc.i4   0xEDD
0x78a  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint)
0x78f  br.s     loc_79B
0x791  ldc.i4   0xEE0
0x796  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint)
0x79b  ldarg.0
0x79c  ldc.i4.1
0x79d  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x7a2  ldloc.0
0x7a3  ret
```
