# Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException_0

- ea: `0x91b0`
- end: `0x9293`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException_0`
- size: `227`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5400`
- `0x54a0`
- `0x5710`
- `0x57a0`
- `0x5960`
- `0x5a50`
- `0x5bf0`
- `0x97f0`

## callees

- `0x18e0`
- `0x91b0`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x91b0  ldc.i4.0
0x91b1  stloc.0
0x91b2  ldarg.0
0x91b3  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ActionForException()
0x91b8  stloc.2
0x91b9  ldloc.2
0x91ba  switch   loc_91D0, loc_9211, loc_9204
0x91cb  br       loc_9291
0x91d0  ldc.i4.1
0x91d1  stloc.0
0x91d2  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x91d7  stloc.1
0x91d8  ldloc.1
0x91d9  ldarg.0
0x91da  callvirt instance string [mscorlib]System.Exception::get_Message()
0x91df  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x91e4  ldloc.1
0x91e5  ldc.i4.s 0x10
0x91e7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x91ec  ldloc.1
0x91ed  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x91f2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x91f7  ldarg.2
0x91f8  ldloc.1
0x91f9  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x91fe  pop
0x91ff  br       loc_9291
0x9204  ldarg.0
0x9205  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::TraceException()
0x920a  ldc.i4.1
0x920b  stloc.0
0x920c  br       loc_9291
0x9211  ldc.i4.0
0x9212  stloc.0
0x9213  ldarg.1
0x9214  brfalse.s loc_925F
0x9216  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::.ctor()
0x921b  stloc.3
0x921c  ldloc.3
0x921d  ldtoken  Microsoft.EventViewer.SnapIn.MessageViewEx
0x9222  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9227  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_ViewType(class [mscorlib]System.Type)
0x922c  ldloc.3
0x922d  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x9232  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_Title(string)
0x9237  ldloc.3
0x9238  ldarg.0
0x9239  callvirt instance string [mscorlib]System.Exception::get_Message()
0x923e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_BodyText(string)
0x9243  ldloc.3
0x9244  ldc.i4.1
0x9245  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_IconId(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewIcon)
0x924a  ldloc.3
0x924b  ldarg.1
0x924c  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x9251  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_DisplayName(string)
0x9256  ldarg.1
0x9257  ldloc.3
0x9258  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ChangeToMessageViewDescription(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription mvd)
0x925d  br.s     loc_9291
0x925f  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x9264  stloc.s  4
0x9266  ldloc.s  4
0x9268  ldarg.0
0x9269  callvirt instance string [mscorlib]System.Exception::get_Message()
0x926e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x9273  ldloc.s  4
0x9275  ldc.i4.s 0x10
0x9277  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x927c  ldloc.s  4
0x927e  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x9283  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x9288  ldarg.2
0x9289  ldloc.s  4
0x928b  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x9290  pop
0x9291  ldloc.0
0x9292  ret
```
