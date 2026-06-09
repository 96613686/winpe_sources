# System.Web.UI.Design.WebControls.DataControlFieldsEditor::InitializeComponent

- ea: `0x1cd60`
- end: `0x1d6bf`
- name: `System.Web.UI.Design.WebControls.DataControlFieldsEditor::InitializeComponent`
- size: `2399`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c870`

## callees

- `0x51a60`
- `0x51a90`
- `0xe3d40`
- `0xf7900`
- `0xf7930`

## string_xrefs

- `0x1d3bc`: `_refreshSchemaLink`
- `0x1d0c2`: `_moveFieldUpButton`
- `0x1d123`: `_moveFieldDownButton`
- `0x1d1ee`: `_deleteFieldButton`
- `0x1d439`: `_templatizeLink`

## pseudocode

```c

```

## disassembly

```asm
0x1cd60  ldarg.0
0x1cd61  newobj   instance void TreeViewWithEnter::.ctor()
0x1cd66  stfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1cd6b  ldarg.0
0x1cd6c  newobj   instance void ListViewWithEnter::.ctor()
0x1cd71  stfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cd76  ldarg.0
0x1cd77  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cd7c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1cd81  ldarg.0
0x1cd82  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cd87  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1cd8c  ldarg.0
0x1cd8d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cd92  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1cd97  ldarg.0
0x1cd98  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cd9d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1cda2  ldarg.0
0x1cda3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cda8  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_addFieldButton
0x1cdad  ldarg.0
0x1cdae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cdb3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_deleteFieldButton
0x1cdb8  ldarg.0
0x1cdb9  ldarg.0
0x1cdba  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.DesignerForm::get_ServiceProvider()
0x1cdbf  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x1cdc4  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.DataControlFieldsEditor::_currentFieldProps
0x1cdc9  ldarg.0
0x1cdca  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x1cdcf  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.DataControlFieldsEditor::_autoFieldCheck
0x1cdd4  ldarg.0
0x1cdd5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x1cdda  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.DataControlFieldsEditor::_refreshSchemaLink
0x1cddf  ldarg.0
0x1cde0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x1cde5  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.DataControlFieldsEditor::_templatizeLink
0x1cdea  ldarg.0
0x1cdeb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1cdf0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldLabel
0x1cdf5  ldarg.0
0x1cdf6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1cdfb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsLabel
0x1ce00  ldarg.0
0x1ce01  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ce06  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsLabel
0x1ce0b  ldarg.0
0x1ce0c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1ce11  ldarg.0
0x1ce12  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce17  ldc.i4.0
0x1ce18  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x1ce1d  ldarg.0
0x1ce1e  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce23  ldc.i4.m1
0x1ce24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageIndex(int32)
0x1ce29  ldarg.0
0x1ce2a  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce2f  ldc.i4.s 0xF
0x1ce31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_Indent(int32)
0x1ce36  ldarg.0
0x1ce37  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce3c  ldc.i4.s 0xC
0x1ce3e  ldc.i4.s 0x1C
0x1ce40  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1ce45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1ce4a  ldarg.0
0x1ce4b  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce50  ldstr    aAvailablefield// "_availableFieldsTree"
0x1ce55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1ce5a  ldarg.0
0x1ce5b  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce60  ldc.i4.m1
0x1ce61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_SelectedImageIndex(int32)
0x1ce66  ldarg.0
0x1ce67  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce6c  ldc.i4   0xC4
0x1ce71  ldc.i4.s 0x74
0x1ce73  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1ce78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x1ce7d  ldarg.0
0x1ce7e  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce83  ldc.i4.1
0x1ce84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1ce89  ldarg.0
0x1ce8a  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ce8f  ldarg.0
0x1ce90  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnAvailableFieldsDoubleClick(object source, class [System.Windows.Forms]System.Windows.Forms.TreeNodeMouseClickEventArgs e)
0x1ce96  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeNodeMouseClickEventHandler::.ctor(object, native int)
0x1ce9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_NodeMouseDoubleClick(class [System.Windows.Forms]System.Windows.Forms.TreeNodeMouseClickEventHandler)
0x1cea0  ldarg.0
0x1cea1  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1cea6  ldarg.0
0x1cea7  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnSelChangedAvailableFields(object source, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x1cead  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x1ceb2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x1ceb7  ldarg.0
0x1ceb8  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1cebd  ldarg.0
0x1cebe  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnAvailableFieldsGotFocus(object source, class [mscorlib]System.EventArgs e)
0x1cec4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1cec9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_GotFocus(class [mscorlib]System.EventHandler)
0x1cece  ldarg.0
0x1cecf  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1ced4  ldarg.0
0x1ced5  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnAvailableFieldsKeyPress(object source, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0x1cedb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0x1cee0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0x1cee5  ldarg.0
0x1cee6  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1ceeb  ldc.i4.7
0x1ceec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x1cef1  ldarg.0
0x1cef2  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cef7  ldc.i4.0
0x1cef8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x1cefd  ldarg.0
0x1cefe  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf03  ldc.i4.0
0x1cf04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x1cf09  ldarg.0
0x1cf0a  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf0f  ldc.i4.0
0x1cf10  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_LabelWrap(bool)
0x1cf15  ldarg.0
0x1cf16  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf1b  ldc.i4.s 0xC
0x1cf1d  ldc.i4   0xC5
0x1cf22  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1cf27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1cf2c  ldarg.0
0x1cf2d  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf32  ldc.i4.0
0x1cf33  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x1cf38  ldarg.0
0x1cf39  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf3e  ldstr    aSelfieldslist// "_selFieldsList"
0x1cf43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cf48  ldarg.0
0x1cf49  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf4e  ldc.i4   0xA4
0x1cf53  ldc.i4.s 0x70
0x1cf55  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1cf5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x1cf5f  ldarg.0
0x1cf60  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf65  ldc.i4.4
0x1cf66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1cf6b  ldarg.0
0x1cf6c  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf71  ldc.i4.1
0x1cf72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x1cf77  ldarg.0
0x1cf78  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf7d  ldarg.0
0x1cf7e  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnSelFieldsListKeyDown(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0x1cf84  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0x1cf89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyDown(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0x1cf8e  ldarg.0
0x1cf8f  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cf94  ldarg.0
0x1cf95  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnSelIndexChangedSelFieldsList(object source, class [mscorlib]System.EventArgs e)
0x1cf9b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1cfa0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x1cfa5  ldarg.0
0x1cfa6  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cfab  ldarg.0
0x1cfac  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnClickDeleteField(object source, class [mscorlib]System.EventArgs e)
0x1cfb2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1cfb7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_ItemActivate(class [mscorlib]System.EventHandler)
0x1cfbc  ldarg.0
0x1cfbd  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1cfc2  ldarg.0
0x1cfc3  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnSelFieldsListGotFocus(object source, class [mscorlib]System.EventArgs e)
0x1cfc9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1cfce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_GotFocus(class [mscorlib]System.EventHandler)
0x1cfd3  ldarg.0
0x1cfd4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1cfd9  ldc.i4.s 0xA
0x1cfdb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x1cfe0  ldarg.0
0x1cfe1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1cfe6  ldc.i4.1
0x1cfe7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x1cfec  ldarg.0
0x1cfed  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1cff2  ldc.i4.3
0x1cff3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x1cff8  ldarg.0
0x1cff9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1cffe  ldc.i4   0x154
0x1d003  ldc.i4   0x15E
0x1d008  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1d00d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1d012  ldarg.0
0x1d013  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1d018  ldstr    aOkbutton// "_okButton"
0x1d01d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1d022  ldarg.0
0x1d023  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1d028  ldc.i4.s 0x64
0x1d02a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1d02f  ldarg.0
0x1d030  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1d035  ldarg.0
0x1d036  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnClickOK(object source, class [mscorlib]System.EventArgs e)
0x1d03c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1d041  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1d046  ldarg.0
0x1d047  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d04c  ldc.i4.s 0xA
0x1d04e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x1d053  ldarg.0
0x1d054  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d059  ldc.i4.2
0x1d05a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x1d05f  ldarg.0
0x1d060  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d065  ldc.i4.3
0x1d066  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x1d06b  ldarg.0
0x1d06c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d071  ldc.i4   0x1A4
0x1d076  ldc.i4   0x15E
0x1d07b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1d080  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1d085  ldarg.0
0x1d086  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d08b  ldstr    aCancelbutton// "_cancelButton"
0x1d090  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1d095  ldarg.0
0x1d096  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d09b  ldc.i4.s 0x65
0x1d09d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1d0a2  ldarg.0
0x1d0a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d0a8  ldc.i4   0xBA
0x1d0ad  ldc.i4   0xC5
0x1d0b2  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1d0b7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1d0bc  ldarg.0
0x1d0bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d0c2  ldstr    aMovefieldupbut// "_moveFieldUpButton"
0x1d0c7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1d0cc  ldarg.0
0x1d0cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d0d2  ldc.i4.s 0x1A
0x1d0d4  ldc.i4.s 0x17
0x1d0d6  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1d0db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x1d0e0  ldarg.0
0x1d0e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d0e6  ldc.i4.5
0x1d0e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1d0ec  ldarg.0
0x1d0ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d0f2  ldarg.0
0x1d0f3  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnClickMoveFieldUp(object source, class [mscorlib]System.EventArgs e)
0x1d0f9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1d0fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1d103  ldarg.0
0x1d104  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d109  ldc.i4   0xBA
0x1d10e  ldc.i4   0xDD
0x1d113  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1d118  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1d11d  ldarg.0
0x1d11e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d123  ldstr    aMovefielddownb// "_moveFieldDownButton"
0x1d128  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1d12d  ldarg.0
0x1d12e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d133  ldc.i4.s 0x1A
0x1d135  ldc.i4.s 0x17
0x1d137  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1d13c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x1d141  ldarg.0
0x1d142  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d147  ldc.i4.6
0x1d148  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1d14d  ldarg.0
0x1d14e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d153  ldarg.0
0x1d154  ldftn    instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::OnClickMoveFieldDown(object source, class [mscorlib]System.EventArgs e)
0x1d15a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1d15f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1d164  ldarg.0
0x1d165  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_addFieldButton
0x1d16a  ldc.i4.3
0x1d16b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x1d170  ldarg.0
0x1d171  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_addFieldButton
0x1d176  ldc.i4.s 0x7B
0x1d178  ldc.i4   0x96
0x1d17d  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x1d182  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x1d187  ldarg.0
0x1d188  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_addFieldButton
0x1d18d  ldstr    aAddfieldbutton// "_addFieldButton"
  ... truncated ...
```
