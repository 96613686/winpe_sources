# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetAction

- ea: `0x4c40`
- end: `0x4cc9`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetAction`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x4c40`
- `0x4cd0`
- `0x4d20`
- `0x8010`
- `0x8380`
- `0x9070`

## string_xrefs

- `0x4c78`: `This action for result control should not be coming`

## pseudocode

```c

```

## disassembly

```asm
0x4c40  ldnull
0x4c41  stloc.0
0x4c42  ldarg.2
0x4c43  ldnull
0x4c44  stind.ref
0x4c45  ldc.i4.0
0x4c46  stloc.1
0x4c47  ldarg.1
0x4c48  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x4c4d  stloc.2
0x4c4e  ldloc.2
0x4c4f  ldc.i4.6
0x4c50  beq.s    loc_4C59
0x4c52  ldloc.2
0x4c53  ldc.i4.s 0x17
0x4c55  beq.s    loc_4C6A
0x4c57  br.s     loc_4C78
0x4c59  ldarg.1
0x4c5a  call     class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetPropertiesAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4c5f  stloc.0
0x4c60  ldloc.0
0x4c61  brfalse.s loc_4C91
0x4c63  ldarg.2
0x4c64  ldloc.0
0x4c65  stind.ref
0x4c66  ldc.i4.1
0x4c67  stloc.1
0x4c68  br.s     loc_4C91
0x4c6a  ldarg.1
0x4c6b  call     class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetOpenItemAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4c70  stloc.0
0x4c71  ldarg.2
0x4c72  ldloc.0
0x4c73  stind.ref
0x4c74  ldc.i4.1
0x4c75  stloc.1
0x4c76  br.s     loc_4C91
0x4c78  ldstr    aThisActionForR// "This action for result control should n"...
0x4c7d  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string)
0x4c82  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x4c87  callvirt instance string [mscorlib]System.Object::ToString()
0x4c8c  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string)
0x4c91  ldloc.1
0x4c92  brfalse.s loc_4CBB
0x4c94  ldarg.2
0x4c95  ldind.ref
0x4c96  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x4c9b  stloc.0
0x4c9c  ldloc.0
0x4c9d  brfalse.s loc_4CBB
0x4c9f  ldarg.0
0x4ca0  ldloca.s 0
0x4ca2  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x4ca7  ldloc.0
0x4ca8  ldarg.1
0x4ca9  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x4cae  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForAction(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x4cb3  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x4cb8  ldarg.2
0x4cb9  ldloc.0
0x4cba  stind.ref
0x4cbb  ldloc.1
0x4cbc  brfalse.s loc_4CC0
0x4cbe  ldloc.1
0x4cbf  ret
0x4cc0  ldarg.0
0x4cc1  ldarg.1
0x4cc2  ldarg.2
0x4cc3  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::GetAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action, [out] class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem& actionOut)
0x4cc8  ret
```
