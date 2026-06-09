# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::InitializeComponent

- ea: `0x4fd0`
- end: `0x50ba`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::InitializeComponent`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b60`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldarg.0
0x4fd1  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::.ctor()
0x4fd6  stfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4fdb  ldarg.0
0x4fdc  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x4fe1  ldarg.0
0x4fe2  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4fe7  ldc.i4.5
0x4fe8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x4fed  ldarg.0
0x4fee  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4ff3  ldc.i4.0
0x4ff4  ldc.i4.0
0x4ff5  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x4ffa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x4fff  ldarg.0
0x5000  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x5005  ldstr    aFolderviewctl1// "folderViewCtl1"
0x500a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x500f  ldarg.0
0x5010  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x5015  ldc.i4   0x199
0x501a  ldc.i4   0x187
0x501f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x5024  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x5029  ldarg.0
0x502a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x502f  ldc.i4.0
0x5030  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x5035  ldarg.0
0x5036  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x503b  ldarg.0
0x503c  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsFolderView::NavigateNode(object sender, class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NodeSelectEventArgs e)
0x5042  newobj   instance void class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NodeSelectEventArgs>::.ctor(object, native int)
0x5047  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::add_NavigateToNode(class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NodeSelectEventArgs>)
0x504c  ldarg.0
0x504d  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x5052  ldarg.0
0x5053  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsFolderView::ItemSelectionHandler(object sender, class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs e)
0x5059  newobj   instance void class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs>::.ctor(object, native int)
0x505e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::add_ItemSelectionChanged(class [mscorlib]System.EventHandler`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ItemSelectionDataArgs>)
0x5063  ldarg.0
0x5064  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x5069  ldarg.0
0x506a  ldftn    instance void Microsoft.EventViewer.SnapIn.MMCEventsFolderView::ShowContextMenu(object obj, class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuArgs e)
0x5070  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuHandler::.ctor(object, native int)
0x5075  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::add_ShowContextMenu(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowContextMenuHandler)
0x507a  ldarg.0
0x507b  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x5080  ldarg.0
0x5081  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x5086  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x508b  ldarg.0
0x508c  ldstr    aMmceventsfolde// "MMCEventsFolderView"
0x5091  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x5096  ldarg.0
0x5097  ldc.i4   0x199
0x509c  ldc.i4   0x187
0x50a1  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x50a6  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x50ab  ldarg.0
0x50ac  ldc.i4.5
0x50ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x50b2  ldarg.0
0x50b3  ldc.i4.0
0x50b4  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x50b9  ret
```
