# System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::.ctor

- ea: `0x43790`
- end: `0x43f41`
- name: `System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::.ctor`
- size: `1969`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x45e10`

## callees

- `0x18b20`
- `0x18b30`
- `0x51a60`
- `0x51a90`
- `0x8ef40`
- `0xe3d40`
- `0xef310`

## string_xrefs

- `0x43e5c`: `Commands.bmp`
- `0x43838`: `TreeNodeCollectionEditor_Remove`
- `0x4384f`: `TreeNodeCollectionEditor_MoveUp`
- `0x43866`: `TreeNodeCollectionEditor_MoveDown`

## pseudocode

```c

```

## disassembly

```asm
0x43790  ldarg.0
0x43791  ldarg.1
0x43792  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x43797  call     instance void System.Web.UI.Design.WebControls.CollectionEditorDialog::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x4379c  ldarg.0
0x4379d  ldarg.1
0x4379e  stfld    class [System.Web]System.Web.UI.WebControls.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_webTreeView
0x437a3  ldarg.0
0x437a4  ldarg.2
0x437a5  stfld    class System.Web.UI.Design.WebControls.TreeViewDesigner System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewDesigner
0x437aa  ldarg.0
0x437ab  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x437b0  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x437b5  ldarg.0
0x437b6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x437bb  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x437c0  ldarg.0
0x437c1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::.ctor()
0x437c6  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x437cb  ldarg.0
0x437cc  ldarg.0
0x437cd  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.DesignerForm::get_ServiceProvider()
0x437d2  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x437d7  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_propertyGrid
0x437dc  ldarg.0
0x437dd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x437e2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_okButton
0x437e7  ldarg.0
0x437e8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x437ed  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_cancelButton
0x437f2  ldarg.0
0x437f3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x437f8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_propertiesLabel
0x437fd  ldarg.0
0x437fe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x43803  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_nodesLabel
0x43808  ldarg.0
0x43809  ldarg.0
0x4380a  ldstr    aTreenodecollec// "TreeNodeCollectionEditor_AddRoot"
0x4380f  call     string System.Design.SR::GetString(string name)
0x43814  ldc.i4.3
0x43815  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x4381a  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_addRootButton
0x4381f  ldarg.0
0x43820  ldarg.0
0x43821  ldstr    aTreenodecollec_0// "TreeNodeCollectionEditor_AddChild"
0x43826  call     string System.Design.SR::GetString(string name)
0x4382b  ldc.i4.2
0x4382c  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x43831  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_addChildButton
0x43836  ldarg.0
0x43837  ldarg.0
0x43838  ldstr    aTreenodecollec_1// "TreeNodeCollectionEditor_Remove"
0x4383d  call     string System.Design.SR::GetString(string name)
0x43842  ldc.i4.4
0x43843  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x43848  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_removeButton
0x4384d  ldarg.0
0x4384e  ldarg.0
0x4384f  ldstr    aTreenodecollec_2// "TreeNodeCollectionEditor_MoveUp"
0x43854  call     string System.Design.SR::GetString(string name)
0x43859  ldc.i4.5
0x4385a  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x4385f  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_moveUpButton
0x43864  ldarg.0
0x43865  ldarg.0
0x43866  ldstr    aTreenodecollec_3// "TreeNodeCollectionEditor_MoveDown"
0x4386b  call     string System.Design.SR::GetString(string name)
0x43870  ldc.i4.6
0x43871  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x43876  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_moveDownButton
0x4387b  ldarg.0
0x4387c  ldarg.0
0x4387d  ldstr    aTreenodecollec_4// "TreeNodeCollectionEditor_Indent"
0x43882  call     string System.Design.SR::GetString(string name)
0x43887  ldc.i4.1
0x43888  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x4388d  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_indentButton
0x43892  ldarg.0
0x43893  ldarg.0
0x43894  ldstr    aTreenodecollec_5// "TreeNodeCollectionEditor_Unindent"
0x43899  call     string System.Design.SR::GetString(string name)
0x4389e  ldc.i4.0
0x4389f  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x438a4  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_unindentButton
0x438a9  ldarg.0
0x438aa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator::.ctor()
0x438af  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_toolBarSeparator
0x438b4  ldarg.0
0x438b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x438ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x438bf  ldarg.0
0x438c0  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x438c5  ldarg.0
0x438c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x438cb  ldc.i4.s 0xF
0x438cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x438d2  ldarg.0
0x438d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x438d8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x438dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x438e2  ldarg.0
0x438e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x438e8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x438ed  ldarg.0
0x438ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x438f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x438f8  ldarg.0
0x438f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x438fe  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x43903  ldc.i4.1
0x43904  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Left(int32)
0x43909  ldarg.0
0x4390a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x4390f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x43914  ldc.i4.1
0x43915  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Right(int32)
0x4391a  ldarg.0
0x4391b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43920  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x43925  ldc.i4.1
0x43926  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Bottom(int32)
0x4392b  ldarg.0
0x4392c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43931  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x43936  ldc.i4.1
0x43937  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Top(int32)
0x4393c  ldarg.0
0x4393d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43942  ldc.i4.s 0xC
0x43944  ldc.i4.s 0x36
0x43946  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x4394b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x43950  ldarg.0
0x43951  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43956  ldstr    aTreeviewpanel// "_treeViewPanel"
0x4395b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x43960  ldarg.0
0x43961  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43966  ldc.i4   0xE3
0x4396b  ldc.i4   0xE9
0x43970  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x43975  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x4397a  ldarg.0
0x4397b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewPanel
0x43980  ldc.i4.1
0x43981  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x43986  ldarg.0
0x43987  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x4398c  ldc.i4.0
0x4398d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x43992  ldarg.0
0x43993  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x43998  ldc.i4.5
0x43999  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x4399e  ldarg.0
0x4399f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439a4  ldc.i4.m1
0x439a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageIndex(int32)
0x439aa  ldarg.0
0x439ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439b0  ldc.i4.0
0x439b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x439b6  ldarg.0
0x439b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439bc  ldc.i4.1
0x439bd  ldc.i4.1
0x439be  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x439c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x439c8  ldarg.0
0x439c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439ce  ldstr    aTreeview// "_treeView"
0x439d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x439d8  ldarg.0
0x439d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439de  ldc.i4.m1
0x439df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_SelectedImageIndex(int32)
0x439e4  ldarg.0
0x439e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439ea  ldc.i4.0
0x439eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x439f0  ldarg.0
0x439f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x439f6  ldarg.0
0x439f7  ldftn    instance void System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::OnTreeViewAfterSelect(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x439fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x43a02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x43a07  ldarg.0
0x43a08  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeView
0x43a0d  ldarg.0
0x43a0e  ldftn    instance void System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::OnTreeViewKeyDown(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0x43a14  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0x43a19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyDown(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0x43a1e  ldarg.0
0x43a1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43a24  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0x43a29  ldc.i4.8
0x43a2a  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x43a2f  dup
0x43a30  ldc.i4.0
0x43a31  ldarg.0
0x43a32  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_addRootButton
0x43a37  stelem.ref
0x43a38  dup
0x43a39  ldc.i4.1
0x43a3a  ldarg.0
0x43a3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_addChildButton
0x43a40  stelem.ref
0x43a41  dup
0x43a42  ldc.i4.2
0x43a43  ldarg.0
0x43a44  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_removeButton
0x43a49  stelem.ref
0x43a4a  dup
0x43a4b  ldc.i4.3
0x43a4c  ldarg.0
0x43a4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_toolBarSeparator
0x43a52  stelem.ref
0x43a53  dup
0x43a54  ldc.i4.4
0x43a55  ldarg.0
0x43a56  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_moveUpButton
0x43a5b  stelem.ref
0x43a5c  dup
0x43a5d  ldc.i4.5
0x43a5e  ldarg.0
0x43a5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_moveDownButton
0x43a64  stelem.ref
0x43a65  dup
0x43a66  ldc.i4.6
0x43a67  ldarg.0
0x43a68  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_unindentButton
0x43a6d  stelem.ref
0x43a6e  dup
0x43a6f  ldc.i4.7
0x43a70  ldarg.0
0x43a71  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_indentButton
0x43a76  stelem.ref
0x43a77  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0x43a7c  ldarg.0
0x43a7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43a82  ldc.i4.s 0xC
0x43a84  ldc.i4.s 0x1C
0x43a86  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x43a8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x43a90  ldarg.0
0x43a91  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43a96  ldc.i4.s 0xF
0x43a98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x43a9d  ldarg.0
0x43a9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43aa3  ldc.i4.0
0x43aa4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x43aa9  ldarg.0
0x43aaa  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43aaf  ldc.i4   0xE3
0x43ab4  ldc.i4.s 0x1A
0x43ab6  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x43abb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x43ac0  ldarg.0
0x43ac1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43ac6  ldc.i4.0
0x43ac7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_CanOverflow(bool)
0x43acc  ldarg.0
0x43acd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43ad2  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.Padding [System.Windows.Forms]System.Windows.Forms.Control::get_Padding()
0x43ad7  stloc.0
0x43ad8  ldloca.s 0
0x43ada  ldc.i4.2
0x43adb  call     instance void [System.Windows.Forms]System.Windows.Forms.Padding::set_Left(int32)
0x43ae0  ldarg.0
0x43ae1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43ae6  ldloc.0
0x43ae7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x43aec  ldarg.0
0x43aed  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43af2  ldstr    aTreeviewtoolba// "_treeViewToolBar"
0x43af7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x43afc  ldarg.0
0x43afd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43b02  ldc.i4.1
0x43b03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_RenderMode(valuetype [System.Windows.Forms]System.Windows.Forms.ToolStripRenderMode)
0x43b08  ldarg.0
0x43b09  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43b0e  ldc.i4.1
0x43b0f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_ShowItemToolTips(bool)
0x43b14  ldarg.0
0x43b15  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43b1a  ldc.i4.0
0x43b1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_GripStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ToolStripGripStyle)
0x43b20  ldarg.0
0x43b21  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43b26  ldc.i4.1
0x43b27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x43b2c  ldarg.0
0x43b2d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
0x43b32  ldc.i4.1
0x43b33  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_TabStop(bool)
0x43b38  ldarg.0
0x43b39  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.TreeNodeCollectionEditorDialog::_treeViewToolBar
  ... truncated ...
```
