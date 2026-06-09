# System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::.ctor

- ea: `0x2bde0`
- end: `0x2c591`
- name: `System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::.ctor`
- size: `1969`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2bac0`

## callees

- `0x18b20`
- `0x18b30`
- `0x51a60`
- `0x51a90`
- `0x8ef40`
- `0xe3d40`
- `0xef310`

## string_xrefs

- `0x2be88`: `MenuItemCollectionEditor_Remove`
- `0x2be9f`: `MenuItemCollectionEditor_MoveUp`
- `0x2beb6`: `MenuItemCollectionEditor_MoveDown`
- `0x2c4ac`: `Commands.bmp`

## pseudocode

```c

```

## disassembly

```asm
0x2bde0  ldarg.0
0x2bde1  ldarg.1
0x2bde2  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x2bde7  call     instance void System.Web.UI.Design.WebControls.CollectionEditorDialog::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x2bdec  ldarg.0
0x2bded  ldarg.1
0x2bdee  stfld    class [System.Web]System.Web.UI.WebControls.Menu System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_webMenu
0x2bdf3  ldarg.0
0x2bdf4  ldarg.2
0x2bdf5  stfld    class System.Web.UI.Design.WebControls.MenuDesigner System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_menuDesigner
0x2bdfa  ldarg.0
0x2bdfb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x2be00  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2be05  ldarg.0
0x2be06  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x2be0b  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2be10  ldarg.0
0x2be11  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::.ctor()
0x2be16  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2be1b  ldarg.0
0x2be1c  ldarg.0
0x2be1d  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.DesignerForm::get_ServiceProvider()
0x2be22  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x2be27  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_propertyGrid
0x2be2c  ldarg.0
0x2be2d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2be32  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_okButton
0x2be37  ldarg.0
0x2be38  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2be3d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_cancelButton
0x2be42  ldarg.0
0x2be43  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2be48  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_propertiesLabel
0x2be4d  ldarg.0
0x2be4e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2be53  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_nodesLabel
0x2be58  ldarg.0
0x2be59  ldarg.0
0x2be5a  ldstr    aMenuitemcollec_0// "MenuItemCollectionEditor_AddRoot"
0x2be5f  call     string System.Design.SR::GetString(string name)
0x2be64  ldc.i4.3
0x2be65  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2be6a  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_addRootButton
0x2be6f  ldarg.0
0x2be70  ldarg.0
0x2be71  ldstr    aMenuitemcollec_1// "MenuItemCollectionEditor_AddChild"
0x2be76  call     string System.Design.SR::GetString(string name)
0x2be7b  ldc.i4.2
0x2be7c  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2be81  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_addChildButton
0x2be86  ldarg.0
0x2be87  ldarg.0
0x2be88  ldstr    aMenuitemcollec_2// "MenuItemCollectionEditor_Remove"
0x2be8d  call     string System.Design.SR::GetString(string name)
0x2be92  ldc.i4.4
0x2be93  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2be98  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_removeButton
0x2be9d  ldarg.0
0x2be9e  ldarg.0
0x2be9f  ldstr    aMenuitemcollec_3// "MenuItemCollectionEditor_MoveUp"
0x2bea4  call     string System.Design.SR::GetString(string name)
0x2bea9  ldc.i4.5
0x2beaa  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2beaf  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_moveUpButton
0x2beb4  ldarg.0
0x2beb5  ldarg.0
0x2beb6  ldstr    aMenuitemcollec_4// "MenuItemCollectionEditor_MoveDown"
0x2bebb  call     string System.Design.SR::GetString(string name)
0x2bec0  ldc.i4.6
0x2bec1  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2bec6  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_moveDownButton
0x2becb  ldarg.0
0x2becc  ldarg.0
0x2becd  ldstr    aMenuitemcollec_5// "MenuItemCollectionEditor_Indent"
0x2bed2  call     string System.Design.SR::GetString(string name)
0x2bed7  ldc.i4.1
0x2bed8  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2bedd  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_indentButton
0x2bee2  ldarg.0
0x2bee3  ldarg.0
0x2bee4  ldstr    aMenuitemcollec_6// "MenuItemCollectionEditor_Unindent"
0x2bee9  call     string System.Design.SR::GetString(string name)
0x2beee  ldc.i4.0
0x2beef  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.CollectionEditorDialog::CreatePushButton(string toolTipText, int32 imageIndex)
0x2bef4  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_unindentButton
0x2bef9  ldarg.0
0x2befa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator::.ctor()
0x2beff  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_toolBarSeparator
0x2bf04  ldarg.0
0x2bf05  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf0a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2bf0f  ldarg.0
0x2bf10  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2bf15  ldarg.0
0x2bf16  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf1b  ldc.i4.s 0xF
0x2bf1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2bf22  ldarg.0
0x2bf23  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf28  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x2bf2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x2bf32  ldarg.0
0x2bf33  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf38  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2bf3d  ldarg.0
0x2bf3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2bf43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2bf48  ldarg.0
0x2bf49  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf4e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x2bf53  ldc.i4.1
0x2bf54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Left(int32)
0x2bf59  ldarg.0
0x2bf5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf5f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x2bf64  ldc.i4.1
0x2bf65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Right(int32)
0x2bf6a  ldarg.0
0x2bf6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf70  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x2bf75  ldc.i4.1
0x2bf76  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Bottom(int32)
0x2bf7b  ldarg.0
0x2bf7c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf81  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x2bf86  ldc.i4.1
0x2bf87  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Top(int32)
0x2bf8c  ldarg.0
0x2bf8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bf92  ldc.i4.s 0xC
0x2bf94  ldc.i4.s 0x36
0x2bf96  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2bf9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2bfa0  ldarg.0
0x2bfa1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bfa6  ldstr    aTreeviewpanel// "_treeViewPanel"
0x2bfab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2bfb0  ldarg.0
0x2bfb1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bfb6  ldc.i4   0xE3
0x2bfbb  ldc.i4   0xE9
0x2bfc0  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2bfc5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2bfca  ldarg.0
0x2bfcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewPanel
0x2bfd0  ldc.i4.1
0x2bfd1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2bfd6  ldarg.0
0x2bfd7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2bfdc  ldc.i4.0
0x2bfdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x2bfe2  ldarg.0
0x2bfe3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2bfe8  ldc.i4.5
0x2bfe9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x2bfee  ldarg.0
0x2bfef  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2bff4  ldc.i4.m1
0x2bff5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageIndex(int32)
0x2bffa  ldarg.0
0x2bffb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c000  ldc.i4.0
0x2c001  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x2c006  ldarg.0
0x2c007  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c00c  ldc.i4.1
0x2c00d  ldc.i4.1
0x2c00e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2c013  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2c018  ldarg.0
0x2c019  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c01e  ldstr    aTreeview// "_treeView"
0x2c023  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2c028  ldarg.0
0x2c029  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c02e  ldc.i4.m1
0x2c02f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_SelectedImageIndex(int32)
0x2c034  ldarg.0
0x2c035  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c03a  ldc.i4.0
0x2c03b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2c040  ldarg.0
0x2c041  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c046  ldarg.0
0x2c047  ldftn    instance void System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::OnTreeViewAfterSelect(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x2c04d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x2c052  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x2c057  ldarg.0
0x2c058  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeView
0x2c05d  ldarg.0
0x2c05e  ldftn    instance void System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::OnTreeViewKeyDown(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0x2c064  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0x2c069  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyDown(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0x2c06e  ldarg.0
0x2c06f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c074  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0x2c079  ldc.i4.8
0x2c07a  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x2c07f  dup
0x2c080  ldc.i4.0
0x2c081  ldarg.0
0x2c082  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_addRootButton
0x2c087  stelem.ref
0x2c088  dup
0x2c089  ldc.i4.1
0x2c08a  ldarg.0
0x2c08b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_addChildButton
0x2c090  stelem.ref
0x2c091  dup
0x2c092  ldc.i4.2
0x2c093  ldarg.0
0x2c094  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_removeButton
0x2c099  stelem.ref
0x2c09a  dup
0x2c09b  ldc.i4.3
0x2c09c  ldarg.0
0x2c09d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_toolBarSeparator
0x2c0a2  stelem.ref
0x2c0a3  dup
0x2c0a4  ldc.i4.4
0x2c0a5  ldarg.0
0x2c0a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_moveUpButton
0x2c0ab  stelem.ref
0x2c0ac  dup
0x2c0ad  ldc.i4.5
0x2c0ae  ldarg.0
0x2c0af  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_moveDownButton
0x2c0b4  stelem.ref
0x2c0b5  dup
0x2c0b6  ldc.i4.6
0x2c0b7  ldarg.0
0x2c0b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_unindentButton
0x2c0bd  stelem.ref
0x2c0be  dup
0x2c0bf  ldc.i4.7
0x2c0c0  ldarg.0
0x2c0c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripButton System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_indentButton
0x2c0c6  stelem.ref
0x2c0c7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0x2c0cc  ldarg.0
0x2c0cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c0d2  ldc.i4.s 0xC
0x2c0d4  ldc.i4.s 0x1C
0x2c0d6  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2c0db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2c0e0  ldarg.0
0x2c0e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c0e6  ldc.i4.s 0xF
0x2c0e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2c0ed  ldarg.0
0x2c0ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c0f3  ldc.i4.0
0x2c0f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x2c0f9  ldarg.0
0x2c0fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c0ff  ldc.i4   0xE3
0x2c104  ldc.i4.s 0x1A
0x2c106  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2c10b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2c110  ldarg.0
0x2c111  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c116  ldc.i4.0
0x2c117  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_CanOverflow(bool)
0x2c11c  ldarg.0
0x2c11d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c122  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.Padding [System.Windows.Forms]System.Windows.Forms.Control::get_Padding()
0x2c127  stloc.0
0x2c128  ldloca.s 0
0x2c12a  ldc.i4.2
0x2c12b  call     instance void [System.Windows.Forms]System.Windows.Forms.Padding::set_Left(int32)
0x2c130  ldarg.0
0x2c131  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c136  ldloc.0
0x2c137  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x2c13c  ldarg.0
0x2c13d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c142  ldstr    aTreeviewtoolba// "_treeViewToolBar"
0x2c147  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2c14c  ldarg.0
0x2c14d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c152  ldc.i4.1
0x2c153  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_RenderMode(valuetype [System.Windows.Forms]System.Windows.Forms.ToolStripRenderMode)
0x2c158  ldarg.0
0x2c159  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c15e  ldc.i4.1
0x2c15f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_ShowItemToolTips(bool)
0x2c164  ldarg.0
0x2c165  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c16a  ldc.i4.0
0x2c16b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_GripStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ToolStripGripStyle)
0x2c170  ldarg.0
0x2c171  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c176  ldc.i4.1
0x2c177  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2c17c  ldarg.0
0x2c17d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
0x2c182  ldc.i4.1
0x2c183  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_TabStop(bool)
0x2c188  ldarg.0
0x2c189  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Web.UI.Design.WebControls.MenuItemCollectionEditorDialog::_treeViewToolBar
  ... truncated ...
```
