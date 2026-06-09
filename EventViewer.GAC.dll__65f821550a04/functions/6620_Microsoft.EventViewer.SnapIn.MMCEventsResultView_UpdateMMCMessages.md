# Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateMMCMessages

- ea: `0x6620`
- end: `0x66bb`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateMMCMessages`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5a40`
- `0x64e0`

## callees

- `0x65d0`
- `0x6620`
- `0x7cb0`
- `0xa910`

## pseudocode

```c

```

## disassembly

```asm
0x6620  ldarg.0
0x6621  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6626  brfalse  loc_66BA
0x662b  ldarg.0
0x662c  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x6631  brfalse  loc_66BA
0x6636  ldarg.0
0x6637  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x663c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6641  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x6646  pop
0x6647  ldarg.0
0x6648  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x664d  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_NewEventsForQuery()
0x6652  brfalse.s loc_6685
0x6654  ldarg.0
0x6655  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x665a  ldnull
0x665b  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResultSetChangedDesc()
0x6660  ldc.i4.1
0x6661  newarr   [mscorlib]System.Object
0x6666  dup
0x6667  ldc.i4.0
0x6668  ldarg.0
0x6669  ldarg.0
0x666a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x666f  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_Message()
0x6674  call     instance string Microsoft.EventViewer.SnapIn.MMCEventsResultView::AdjustMessage(string message)
0x6679  stelem.ref
0x667a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x667f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::set_DescriptionBarText(string)
0x6684  ret
0x6685  ldarg.0
0x6686  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x668b  ldarg.0
0x668c  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6691  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_Message()
0x6696  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x669b  brtrue.s loc_66B0
0x669d  ldarg.0
0x669e  ldarg.0
0x669f  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x66a4  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_Message()
0x66a9  call     instance string Microsoft.EventViewer.SnapIn.MMCEventsResultView::AdjustMessage(string message)
0x66ae  br.s     loc_66B5
0x66b0  ldsfld   string [mscorlib]System.String::Empty
0x66b5  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::set_DescriptionBarText(string)
0x66ba  ret
```
