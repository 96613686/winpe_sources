# Microsoft.EventViewer.SnapIn.MMCEventsResultView::RemoveSharedDetailControl

- ea: `0x5310`
- end: `0x53f7`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::RemoveSharedDetailControl`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5790`

## callees

- `0x5310`

## pseudocode

```c

```

## disassembly

```asm
0x5310  ldarg.0
0x5311  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5316  brfalse  loc_53F6
0x531b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x5320  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x5325  pop
0x5326  ldarg.0
0x5327  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x532c  ldarg.0
0x532d  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5332  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Remove(class [System.Windows.Forms]System.Windows.Forms.Control)
0x5337  ldarg.0
0x5338  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x533d  ldarg.0
0x533e  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::MouseClickHandler(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0x5344  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0x5349  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::remove_MouseClick(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0x534e  ldarg.0
0x534f  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5354  ldarg.0
0x5355  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::MouseClickHandler(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0x535b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0x5360  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::remove_MouseUp(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0x5365  ldarg.0
0x5366  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x536b  ldarg.0
0x536c  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::FilterCleared(object sender, class [mscorlib]System.EventArgs e)
0x5372  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x5377  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_FilterCleared(class [mscorlib]System.EventHandler)
0x537c  ldarg.0
0x537d  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5382  ldarg.0
0x5383  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::ShowContextMenu(object obj, class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuArgs e)
0x5389  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuHandler::.ctor(object, native int)
0x538e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_ShowContextMenu(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuHandler)
0x5393  ldarg.0
0x5394  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5399  ldarg.0
0x539a  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::EventSelectionHandler(object sender, class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs e)
0x53a0  newobj   instance void class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs>::.ctor(object, native int)
0x53a5  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_ItemSelectionChanged(class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs>)
0x53aa  ldarg.0
0x53ab  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x53b0  ldarg.0
0x53b1  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::ActionsChangedHandler(object sender, class [mscorlib]System.EventArgs e)
0x53b7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x53bc  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_ActionsChanged(class [mscorlib]System.EventHandler)
0x53c1  ldarg.0
0x53c2  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x53c7  ldarg.0
0x53c8  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::ViewConfigChanged(object sender, class [mscorlib]System.EventArgs args)
0x53ce  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x53d3  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_ViewConfigChanged(class [mscorlib]System.EventHandler)
0x53d8  ldarg.0
0x53d9  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x53de  ldarg.0
0x53df  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateDescriptionHandler(object sender, class [mscorlib]System.EventArgs e)
0x53e5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x53ea  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::remove_UpdateDescription(class [mscorlib]System.EventHandler)
0x53ef  ldarg.0
0x53f0  ldnull
0x53f1  stfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x53f6  ret
```
