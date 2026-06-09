# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::UpdateActions

- ea: `0x4d70`
- end: `0x4dbf`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::UpdateActions`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4d70`
- `0x7cf0`
- `0x8120`

## pseudocode

```c

```

## disassembly

```asm
0x4d70  ldarg.0
0x4d71  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4d76  callvirt instance class [mscorlib]System.Collections.ICollection [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::get_Actions()
0x4d7b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4d80  stloc.0
0x4d81  br.s     loc_4D96
0x4d83  ldloc.0
0x4d84  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d89  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x4d8e  stloc.1
0x4d8f  ldarg.0
0x4d90  ldloc.1
0x4d91  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4d96  ldloc.0
0x4d97  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d9c  brtrue.s loc_4D83
0x4d9e  leave.s  loc_4DB1
0x4da0  ldloc.0
0x4da1  isinst   [mscorlib]System.IDisposable
0x4da6  stloc.2
0x4da7  ldloc.2
0x4da8  brfalse.s loc_4DB0
0x4daa  ldloc.2
0x4dab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4db0  endfinally
0x4db1  ldarg.0
0x4db2  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::UpdateActions()
0x4db7  ldarg.0
0x4db8  ldc.i4.1
0x4db9  stfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::actionsInitialized
0x4dbe  ret
```
