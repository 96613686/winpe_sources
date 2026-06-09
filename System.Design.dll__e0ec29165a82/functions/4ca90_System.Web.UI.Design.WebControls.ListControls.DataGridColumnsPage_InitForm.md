# System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::InitForm

- ea: `0x4ca90`
- end: `0x4d6e5`
- name: `System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::InitForm`
- size: `3157`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4e3a0`

## callees

- `0x51c00`
- `0x8ef40`
- `0xef300`
- `0xef310`
- `0x101dd0`
- `0x101e80`
- `0x102160`
- `0x102800`
- `0x103190`

## string_xrefs

- `0x4cfdc`: `Delete.ico`
- `0x4cf0b`: `MoveColumnUpButton`
- `0x4cf1b`: `DGCol_MoveColumnUpButtonDesc`
- `0x4cf94`: `MoveColumnDownButton`
- `0x4cfa4`: `DGCol_MoveColumnDownButtonDesc`
- `0x4d01e`: `DeleteColumnButton`
- `0x4d02e`: `DGCol_DeleteColumnButtonDesc`
- `0x4d36c`: `ColumnSortExprCombo`
- `0x4d558`: `DGCol_Templatize`
- `0x4d590`: `TemplatizeLink`

## pseudocode

```c

```

## disassembly

```asm
0x4ca90  ldarg.0
0x4ca91  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x4ca96  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4ca9b  newobj   instance void System.Web.UI.Design.Util.GroupLabel::.ctor()
0x4caa0  stloc.0
0x4caa1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4caa6  stloc.1
0x4caa7  ldarg.0
0x4caa8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x4caad  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4cab2  ldarg.0
0x4cab3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x4cab8  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cabd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4cac2  stloc.2
0x4cac3  ldarg.0
0x4cac4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x4cac9  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4cace  ldarg.0
0x4cacf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x4cad4  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::moveColumnUpButton
0x4cad9  ldarg.0
0x4cada  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x4cadf  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::moveColumnDownButton
0x4cae4  ldarg.0
0x4cae5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x4caea  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::deleteColumnButton
0x4caef  ldarg.0
0x4caf0  newobj   instance void System.Web.UI.Design.Util.GroupLabel::.ctor()
0x4caf5  stfld    class System.Web.UI.Design.Util.GroupLabel System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnPropsGroup
0x4cafa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4caff  stloc.3
0x4cb00  ldarg.0
0x4cb01  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x4cb06  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnHeaderTextEdit
0x4cb0b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4cb10  stloc.s  4
0x4cb12  ldarg.0
0x4cb13  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x4cb18  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnHeaderImageEdit
0x4cb1d  ldarg.0
0x4cb1e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x4cb23  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnHeaderImagePickerButton
0x4cb28  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4cb2d  stloc.s  5
0x4cb2f  ldarg.0
0x4cb30  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x4cb35  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnFooterTextEdit
0x4cb3a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x4cb3f  stloc.s  6
0x4cb41  ldarg.0
0x4cb42  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x4cb47  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnSortExprCombo
0x4cb4c  ldarg.0
0x4cb4d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x4cb52  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnVisibleCheck
0x4cb57  ldarg.0
0x4cb58  newobj   instance void BoundColumnEditor::.ctor()
0x4cb5d  stfld    class BoundColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::boundColumnEditor
0x4cb62  ldarg.0
0x4cb63  newobj   instance void ButtonColumnEditor::.ctor()
0x4cb68  stfld    class ButtonColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::buttonColumnEditor
0x4cb6d  ldarg.0
0x4cb6e  newobj   instance void HyperLinkColumnEditor::.ctor()
0x4cb73  stfld    class HyperLinkColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::hyperLinkColumnEditor
0x4cb78  ldarg.0
0x4cb79  newobj   instance void EditCommandColumnEditor::.ctor()
0x4cb7e  stfld    class EditCommandColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::editCommandColumnEditor
0x4cb83  ldarg.0
0x4cb84  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x4cb89  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::templatizeLink
0x4cb8e  ldarg.0
0x4cb8f  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4cb94  ldstr    aColumnnodesBmp// "ColumnNodes.bmp"
0x4cb99  call     class [System.Drawing]System.Drawing.Bitmap System.Drawing.BitmapSelector::CreateBitmap(class [mscorlib]System.Type type, string originalName)
0x4cb9e  stloc.s  7
0x4cba0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ImageList::.ctor()
0x4cba5  stloc.s  8
0x4cba7  ldloc.s  8
0x4cba9  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Magenta()
0x4cbae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList::set_TransparentColor(valuetype [System.Drawing]System.Drawing.Color)
0x4cbb3  ldloc.s  8
0x4cbb5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x4cbba  ldloc.s  7
0x4cbbc  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::AddStrip(class [System.Drawing]System.Drawing.Image)
0x4cbc1  pop
0x4cbc2  ldarg.0
0x4cbc3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cbc8  ldc.i4.4
0x4cbc9  ldc.i4.4
0x4cbca  ldc.i4   0x190
0x4cbcf  ldc.i4.s 0x10
0x4cbd1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cbd6  ldarg.0
0x4cbd7  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cbdc  ldstr    aDgcolAutogen// "DGCol_AutoGen"
0x4cbe1  call     string System.Design.SR::GetString(string name)
0x4cbe6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4cbeb  ldarg.0
0x4cbec  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cbf1  ldc.i4.0
0x4cbf2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4cbf7  ldarg.0
0x4cbf8  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cbfd  ldc.i4.s 0x10
0x4cbff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x4cc04  ldarg.0
0x4cc05  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cc0a  ldc.i4.3
0x4cc0b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x4cc10  ldarg.0
0x4cc11  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cc16  ldarg.0
0x4cc17  ldftn    instance void System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::OnCheckChangedAutoColumn(object source, class [mscorlib]System.EventArgs e)
0x4cc1d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4cc22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x4cc27  ldarg.0
0x4cc28  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::autoColumnCheck
0x4cc2d  ldstr    aAutocolumnchec// "AutoColumnCheckBox"
0x4cc32  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4cc37  ldloc.0
0x4cc38  ldc.i4.4
0x4cc39  ldc.i4.s 0x18
0x4cc3b  ldc.i4   0x1AF
0x4cc40  ldc.i4.s 0xE
0x4cc42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cc47  ldloc.0
0x4cc48  ldstr    aDgcolCollistgr// "DGCol_ColListGroup"
0x4cc4d  call     string System.Design.SR::GetString(string name)
0x4cc52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4cc57  ldloc.0
0x4cc58  ldc.i4.0
0x4cc59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x4cc5e  ldloc.0
0x4cc5f  ldc.i4.1
0x4cc60  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4cc65  ldloc.0
0x4cc66  ldstr    aColumnlistgrou// "ColumnListGroup"
0x4cc6b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4cc70  ldloc.1
0x4cc71  ldc.i4.s 0xC
0x4cc73  ldc.i4.s 0x28
0x4cc75  ldc.i4   0xB8
0x4cc7a  ldc.i4.s 0x10
0x4cc7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cc81  ldloc.1
0x4cc82  ldstr    aDgcolAvailable// "DGCol_AvailableCols"
0x4cc87  call     string System.Design.SR::GetString(string name)
0x4cc8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4cc91  ldloc.1
0x4cc92  ldc.i4.0
0x4cc93  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x4cc98  ldloc.1
0x4cc99  ldc.i4.2
0x4cc9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4cc9f  ldloc.1
0x4cca0  ldstr    aAvailablecolum// "AvailableColumnsLabel"
0x4cca5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4ccaa  ldarg.0
0x4ccab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4ccb0  ldc.i4.s 0xC
0x4ccb2  ldc.i4.s 0x3A
0x4ccb4  ldc.i4   0xAA
0x4ccb9  ldc.i4.s 0x58
0x4ccbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4ccc0  ldarg.0
0x4ccc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4ccc6  ldloc.s  8
0x4ccc8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x4cccd  ldarg.0
0x4ccce  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4ccd3  ldc.i4.5
0x4ccd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_Indent(int32)
0x4ccd9  ldarg.0
0x4ccda  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4ccdf  ldc.i4.0
0x4cce0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x4cce5  ldarg.0
0x4cce6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4cceb  ldc.i4.3
0x4ccec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4ccf1  ldarg.0
0x4ccf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4ccf7  ldarg.0
0x4ccf8  ldftn    instance void System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::OnSelChangedAvailableColumns(object source, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x4ccfe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x4cd03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x4cd08  ldarg.0
0x4cd09  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4cd0e  ldstr    aAvailablecolum_0// "AvailableColumnsTree"
0x4cd13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4cd18  ldarg.0
0x4cd19  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd1e  ldc.i4   0xBB
0x4cd23  ldc.i4.s 0x52
0x4cd25  ldc.i4.s 0x1F
0x4cd27  ldc.i4.s 0x18
0x4cd29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cd2e  ldarg.0
0x4cd2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd34  ldstr    asc_1307F8// ">"
0x4cd39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4cd3e  ldarg.0
0x4cd3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd44  ldc.i4.4
0x4cd45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4cd4a  ldarg.0
0x4cd4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd50  ldc.i4.3
0x4cd51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x4cd56  ldarg.0
0x4cd57  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd5c  ldarg.0
0x4cd5d  ldftn    instance void System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::OnClickAddColumn(object source, class [mscorlib]System.EventArgs e)
0x4cd63  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4cd68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x4cd6d  ldarg.0
0x4cd6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd73  ldstr    aAddcolumnbutto// "AddColumnButton"
0x4cd78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4cd7d  ldarg.0
0x4cd7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::addColumnButton
0x4cd83  ldstr    aDgcolAddcolbut// "DGCol_AddColButtonDesc"
0x4cd88  call     string System.Design.SR::GetString(string name)
0x4cd8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x4cd92  ldloc.2
0x4cd93  ldc.i4   0xE2
0x4cd98  ldc.i4.s 0x28
0x4cd9a  ldc.i4   0xC8
0x4cd9f  ldc.i4.s 0xE
0x4cda1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cda6  ldloc.2
0x4cda7  ldstr    aDgcolSelectedc// "DGCol_SelectedCols"
0x4cdac  call     string System.Design.SR::GetString(string name)
0x4cdb1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4cdb6  ldloc.2
0x4cdb7  ldc.i4.0
0x4cdb8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x4cdbd  ldloc.2
0x4cdbe  ldc.i4.5
0x4cdbf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4cdc4  ldloc.2
0x4cdc5  ldstr    aSelectedcolumn// "SelectedColumnsLabel"
0x4cdca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4cdcf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x4cdd4  stloc.s  9
0x4cdd6  ldloc.s  9
0x4cdd8  ldc.i4   0xB0
0x4cddd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Width(int32)
0x4cde2  ldarg.0
0x4cde3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4cde8  ldc.i4   0xDE
0x4cded  ldc.i4.s 0x3A
0x4cdef  ldc.i4   0xB4
0x4cdf4  ldc.i4.s 0x58
0x4cdf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x4cdfb  ldarg.0
0x4cdfc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce01  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x4ce06  ldloc.s  9
0x4ce08  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader)
0x4ce0d  pop
0x4ce0e  ldarg.0
0x4ce0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce14  ldloc.s  8
0x4ce16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_SmallImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x4ce1b  ldarg.0
0x4ce1c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce21  ldc.i4.1
0x4ce22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x4ce27  ldarg.0
0x4ce28  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce2d  ldc.i4.0
0x4ce2e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x4ce33  ldarg.0
0x4ce34  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce39  ldc.i4.0
0x4ce3a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_LabelWrap(bool)
0x4ce3f  ldarg.0
0x4ce40  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce45  ldc.i4.0
0x4ce46  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x4ce4b  ldarg.0
0x4ce4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce51  ldc.i4.0
0x4ce52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x4ce57  ldarg.0
0x4ce58  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce5d  ldc.i4.6
0x4ce5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4ce63  ldarg.0
0x4ce64  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce69  ldarg.0
0x4ce6a  ldftn    instance void System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::OnSelIndexChangedSelColumnsList(object source, class [mscorlib]System.EventArgs e)
0x4ce70  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4ce75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x4ce7a  ldarg.0
0x4ce7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selColumnsList
0x4ce80  ldarg.0
0x4ce81  ldftn    instance void System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::OnSelColumnsListKeyDown(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
  ... truncated ...
```
