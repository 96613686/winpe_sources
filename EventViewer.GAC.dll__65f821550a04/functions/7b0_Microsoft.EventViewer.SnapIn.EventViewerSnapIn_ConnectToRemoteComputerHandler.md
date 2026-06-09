# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ConnectToRemoteComputerHandler

- ea: `0x7b0`
- end: `0x8cd`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ConnectToRemoteComputerHandler`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6f0`

## callees

- `0x350`
- `0x360`
- `0x7b0`
- `0x8d0`
- `0x4780`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldc.i4.1
0x7b1  stloc.0
0x7b2  ldarg.3
0x7b3  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x7b8  stind.ref
0x7b9  ldarg.2
0x7ba  ldsfld   string [mscorlib]System.String::Empty
0x7bf  stind.ref
0x7c0  ldarg.0
0x7c1  ldsfld   string [mscorlib]System.String::Empty
0x7c6  call     instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::set_ErrorMessage(string value)
0x7cb  ldarg.1
0x7cc  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog
0x7d1  stloc.1
0x7d2  ldloc.1
0x7d3  brfalse  loc_8C0
0x7d8  ldloc.1
0x7d9  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_IsLocalComputer()
0x7de  brtrue.s loc_808
0x7e0  ldloc.1
0x7e1  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_ComputerName()
0x7e6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7eb  brfalse.s loc_7FA
0x7ed  ldarg.0
0x7ee  ldsfld   string [mscorlib]System.String::Empty
0x7f3  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0x7f8  br.s     loc_813
0x7fa  ldarg.0
0x7fb  ldloc.1
0x7fc  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_ComputerName()
0x801  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0x806  br.s     loc_813
0x808  ldarg.0
0x809  ldsfld   string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::localComputer
0x80e  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0x813  ldloc.1
0x814  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_IsAnotherUser()
0x819  brfalse.s loc_841
0x81b  ldarg.0
0x81c  ldloc.1
0x81d  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_UserDomain()
0x822  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userDomain
0x827  ldarg.0
0x828  ldloc.1
0x829  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_UserName()
0x82e  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userName
0x833  ldarg.0
0x834  ldloc.1
0x835  callvirt instance class [mscorlib]System.Security.SecureString [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_EncryptedPassword()
0x83a  stfld    class [mscorlib]System.Security.SecureString Microsoft.EventViewer.SnapIn.EventViewerSnapIn::encryptedPassword
0x83f  br.s     loc_856
0x841  ldarg.0
0x842  ldnull
0x843  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userDomain
0x848  ldarg.0
0x849  ldnull
0x84a  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userName
0x84f  ldarg.0
0x850  ldnull
0x851  stfld    class [mscorlib]System.Security.SecureString Microsoft.EventViewer.SnapIn.EventViewerSnapIn::encryptedPassword
0x856  ldarg.0
0x857  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapIn::get_RootNode()
0x85c  brfalse.s loc_8C0
0x85e  ldloc.1
0x85f  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::get_ShowErrorOnOk()
0x864  brfalse.s loc_871
0x866  ldarg.0
0x867  ldc.i4.1
0x868  ldc.i4.0
0x869  call     instance bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::RefreshViewer(bool expandNodeFlag, bool snapinInitialized)
0x86e  stloc.0
0x86f  br.s     loc_8B5
0x871  ldarg.0
0x872  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapIn::get_RootNode()
0x877  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x87c  ldsfld   string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::localComputer
0x881  ldarg.0
0x882  ldfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0x887  ldc.i4.4
0x888  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x88d  brfalse.s loc_897
0x88f  ldarg.0
0x890  ldfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0x895  br.s     loc_89C
0x897  ldsfld   string [mscorlib]System.String::Empty
0x89c  ldarg.0
0x89d  ldfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userDomain
0x8a2  ldarg.0
0x8a3  ldfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::userName
0x8a8  ldarg.0
0x8a9  ldfld    class [mscorlib]System.Security.SecureString Microsoft.EventViewer.SnapIn.EventViewerSnapIn::encryptedPassword
0x8ae  ldc.i4.1
0x8af  callvirt instance bool Microsoft.EventViewer.SnapIn.MMCRootNode::ConnectToRemoteComputer(string remoteMachine, string userDomain, string userName, class [mscorlib]System.Security.SecureString encryptedPassword, bool snapinInitialized)
0x8b4  stloc.0
0x8b5  ldloc.0
0x8b6  brtrue.s loc_8C0
0x8b8  ldarg.2
0x8b9  ldarg.0
0x8ba  call     instance string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::get_ErrorMessage()
0x8bf  stind.ref
0x8c0  ldarg.0
0x8c1  ldsfld   string [mscorlib]System.String::Empty
0x8c6  call     instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::set_ErrorMessage(string value)
0x8cb  ldloc.0
0x8cc  ret
```
