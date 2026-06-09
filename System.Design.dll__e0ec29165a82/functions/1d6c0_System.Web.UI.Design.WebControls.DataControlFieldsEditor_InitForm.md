# System.Web.UI.Design.WebControls.DataControlFieldsEditor::InitForm

- ea: `0x1d6c0`
- end: `0x1d965`
- name: `System.Web.UI.Design.WebControls.DataControlFieldsEditor::InitForm`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1c870`

## callees

- `0xe170`
- `0x1bf80`
- `0x1d6c0`
- `0x584f0`
- `0x8ef40`
- `0xef300`
- `0xef310`

## string_xrefs

- `0x1d78f`: `DCFEditor_MoveFieldUpDesc`
- `0x1d7a4`: `DCFEditor_MoveFieldUpName`
- `0x1d7e8`: `DCFEditor_MoveFieldDownDesc`
- `0x1d7fd`: `DCFEditor_MoveFieldDownName`
- `0x1d812`: `Delete.ico`
- `0x1d841`: `DCFEditor_DeleteFieldDesc`
- `0x1d856`: `DCFEditor_DeleteFieldName`
- `0x1d86b`: `DCFEditor_Templatize`

## pseudocode

```c

```

## disassembly

```asm
0x1d6c0  ldarg.0
0x1d6c1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d6c6  ldstr    aFieldnodesBmp// "FieldNodes.bmp"
0x1d6cb  call     class [System.Drawing]System.Drawing.Bitmap System.Drawing.BitmapSelector::CreateBitmap(class [mscorlib]System.Type type, string originalName)
0x1d6d0  stloc.0
0x1d6d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ImageList::.ctor()
0x1d6d6  stloc.1
0x1d6d7  ldloc.1
0x1d6d8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Magenta()
0x1d6dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList::set_TransparentColor(valuetype [System.Drawing]System.Drawing.Color)
0x1d6e2  ldloc.1
0x1d6e3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x1d6e8  ldloc.0
0x1d6e9  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::AddStrip(class [System.Drawing]System.Drawing.Image)
0x1d6ee  pop
0x1d6ef  ldarg.0
0x1d6f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.DataControlFieldsEditor::_autoFieldCheck
0x1d6f5  ldstr    aDcfeditorAutog// "DCFEditor_AutoGen"
0x1d6fa  call     string System.Design.SR::GetString(string name)
0x1d6ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d704  ldarg.0
0x1d705  ldfld    class TreeViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsTree
0x1d70a  ldloc.1
0x1d70b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x1d710  ldarg.0
0x1d711  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_addFieldButton
0x1d716  ldstr    aDcfeditorAdd// "DCFEditor_Add"
0x1d71b  call     string System.Design.SR::GetString(string name)
0x1d720  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d725  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x1d72a  stloc.2
0x1d72b  ldloc.2
0x1d72c  ldarg.0
0x1d72d  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1d732  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x1d737  ldc.i4.4
0x1d738  sub
0x1d739  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Width(int32)
0x1d73e  ldarg.0
0x1d73f  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1d744  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x1d749  ldloc.2
0x1d74a  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader)
0x1d74f  pop
0x1d750  ldarg.0
0x1d751  ldfld    class ListViewWithEnter System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsList
0x1d756  ldloc.1
0x1d757  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_SmallImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x1d75c  ldarg.0
0x1d75d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d762  ldstr    aSortupIco// "SortUp.ico"
0x1d767  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x1d76c  stloc.3
0x1d76d  ldloc.3
0x1d76e  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x1d773  stloc.s  4
0x1d775  ldloc.s  4
0x1d777  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x1d77c  ldarg.0
0x1d77d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d782  ldloc.s  4
0x1d784  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x1d789  ldarg.0
0x1d78a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d78f  ldstr    aDcfeditorMovef// "DCFEditor_MoveFieldUpDesc"
0x1d794  call     string System.Design.SR::GetString(string name)
0x1d799  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x1d79e  ldarg.0
0x1d79f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldUpButton
0x1d7a4  ldstr    aDcfeditorMovef_0// "DCFEditor_MoveFieldUpName"
0x1d7a9  call     string System.Design.SR::GetString(string name)
0x1d7ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x1d7b3  ldarg.0
0x1d7b4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d7b9  ldstr    aSortdownIco// "SortDown.ico"
0x1d7be  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x1d7c3  stloc.s  5
0x1d7c5  ldloc.s  5
0x1d7c7  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x1d7cc  stloc.s  6
0x1d7ce  ldloc.s  6
0x1d7d0  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x1d7d5  ldarg.0
0x1d7d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d7db  ldloc.s  6
0x1d7dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x1d7e2  ldarg.0
0x1d7e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d7e8  ldstr    aDcfeditorMovef_1// "DCFEditor_MoveFieldDownDesc"
0x1d7ed  call     string System.Design.SR::GetString(string name)
0x1d7f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x1d7f7  ldarg.0
0x1d7f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_moveFieldDownButton
0x1d7fd  ldstr    aDcfeditorMovef_2// "DCFEditor_MoveFieldDownName"
0x1d802  call     string System.Design.SR::GetString(string name)
0x1d807  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x1d80c  ldarg.0
0x1d80d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d812  ldstr    aDeleteIco// "Delete.ico"
0x1d817  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x1d81c  stloc.s  7
0x1d81e  ldloc.s  7
0x1d820  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x1d825  stloc.s  8
0x1d827  ldloc.s  8
0x1d829  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x1d82e  ldarg.0
0x1d82f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_deleteFieldButton
0x1d834  ldloc.s  8
0x1d836  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x1d83b  ldarg.0
0x1d83c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_deleteFieldButton
0x1d841  ldstr    aDcfeditorDelet// "DCFEditor_DeleteFieldDesc"
0x1d846  call     string System.Design.SR::GetString(string name)
0x1d84b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x1d850  ldarg.0
0x1d851  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_deleteFieldButton
0x1d856  ldstr    aDcfeditorDelet_0// "DCFEditor_DeleteFieldName"
0x1d85b  call     string System.Design.SR::GetString(string name)
0x1d860  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x1d865  ldarg.0
0x1d866  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.DataControlFieldsEditor::_templatizeLink
0x1d86b  ldstr    aDcfeditorTempl// "DCFEditor_Templatize"
0x1d870  call     string System.Design.SR::GetString(string name)
0x1d875  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d87a  ldarg.0
0x1d87b  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.DataControlFieldsEditor::_refreshSchemaLink
0x1d880  ldstr    aDatasourcedesi// "DataSourceDesigner_RefreshSchemaNoHotke"...
0x1d885  call     string System.Design.SR::GetString(string name)
0x1d88a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d88f  ldarg.0
0x1d890  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.DataControlFieldsEditor::_refreshSchemaLink
0x1d895  ldarg.0
0x1d896  ldfld    class System.Web.UI.Design.WebControls.DataBoundControlDesigner System.Web.UI.Design.WebControls.DataControlFieldsEditor::_controlDesigner
0x1d89b  callvirt instance class System.Web.UI.Design.IDataSourceDesigner System.Web.UI.Design.WebControls.DataBoundControlDesigner::get_DataSourceDesigner()
0x1d8a0  brfalse.s loc_1D8B4
0x1d8a2  ldarg.0
0x1d8a3  ldfld    class System.Web.UI.Design.WebControls.DataBoundControlDesigner System.Web.UI.Design.WebControls.DataControlFieldsEditor::_controlDesigner
0x1d8a8  callvirt instance class System.Web.UI.Design.IDataSourceDesigner System.Web.UI.Design.WebControls.DataBoundControlDesigner::get_DataSourceDesigner()
0x1d8ad  callvirt instance bool System.Web.UI.Design.IDataSourceDesigner::get_CanRefreshSchema()
0x1d8b2  br.s     loc_1D8B5
0x1d8b4  ldc.i4.0
0x1d8b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x1d8ba  ldarg.0
0x1d8bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_okButton
0x1d8c0  ldstr    aOkcaption// "OKCaption"
0x1d8c5  call     string System.Design.SR::GetString(string name)
0x1d8ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d8cf  ldarg.0
0x1d8d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.DataControlFieldsEditor::_cancelButton
0x1d8d5  ldstr    aCancelcaption// "CancelCaption"
0x1d8da  call     string System.Design.SR::GetString(string name)
0x1d8df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d8e4  ldarg.0
0x1d8e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldLabel
0x1d8ea  ldstr    aDcfeditorField// "DCFEditor_FieldProps"
0x1d8ef  call     string System.Design.SR::GetString(string name)
0x1d8f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d8f9  ldarg.0
0x1d8fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_availableFieldsLabel
0x1d8ff  ldstr    aDcfeditorAvail// "DCFEditor_AvailableFields"
0x1d904  call     string System.Design.SR::GetString(string name)
0x1d909  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d90e  ldarg.0
0x1d90f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldsLabel
0x1d914  ldstr    aDcfeditorSelec// "DCFEditor_SelectedFields"
0x1d919  call     string System.Design.SR::GetString(string name)
0x1d91e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d923  ldarg.0
0x1d924  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.DataControlFieldsEditor::_currentFieldProps
0x1d929  ldarg.0
0x1d92a  ldfld    class System.Web.UI.Design.WebControls.DataBoundControlDesigner System.Web.UI.Design.WebControls.DataControlFieldsEditor::_controlDesigner
0x1d92f  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1d934  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x1d939  callvirt instance void [System]System.ComponentModel.Component::set_Site(class [System]System.ComponentModel.ISite)
0x1d93e  ldarg.0
0x1d93f  ldstr    aDcfeditorText// "DCFEditor_Text"
0x1d944  call     string System.Design.SR::GetString(string name)
0x1d949  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1d94e  ldarg.0
0x1d94f  ldarg.0
0x1d950  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d955  ldstr    aDatacontrolfie// "DataControlFieldsEditor.ico"
0x1d95a  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x1d95f  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_Icon(class [System.Drawing]System.Drawing.Icon)
0x1d964  ret
```
