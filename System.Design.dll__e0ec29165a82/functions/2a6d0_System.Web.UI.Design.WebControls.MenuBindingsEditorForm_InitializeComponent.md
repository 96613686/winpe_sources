# System.Web.UI.Design.WebControls.MenuBindingsEditorForm::InitializeComponent

- ea: `0x2a6d0`
- end: `0x2aef0`
- name: `System.Web.UI.Design.WebControls.MenuBindingsEditorForm::InitializeComponent`
- size: `2080`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2a370`

## callees

- `0x51a60`
- `0x51a90`
- `0x8ef40`
- `0xe3d40`

## string_xrefs

- `0x2ac8a`: `_moveBindingUpButton`
- `0x2acf9`: `_moveBindingDownButton`
- `0x2ad68`: `_deleteBindingButton`

## pseudocode

```c

```

## disassembly

```asm
0x2a6d0  ldarg.0
0x2a6d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2a6d6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a6db  ldarg.0
0x2a6dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2a6e1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a6e6  ldarg.0
0x2a6e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0x2a6ec  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a6f1  ldarg.0
0x2a6f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a6f7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a6fc  ldarg.0
0x2a6fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2a702  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a707  ldarg.0
0x2a708  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a70d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a712  ldarg.0
0x2a713  ldarg.0
0x2a714  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.DesignerForm::get_ServiceProvider()
0x2a719  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x2a71e  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2a723  ldarg.0
0x2a724  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x2a729  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaTreeView
0x2a72e  ldarg.0
0x2a72f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a734  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingUpButton
0x2a739  ldarg.0
0x2a73a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a73f  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingDownButton
0x2a744  ldarg.0
0x2a745  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a74a  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_deleteBindingButton
0x2a74f  ldarg.0
0x2a750  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a755  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2a75a  ldarg.0
0x2a75b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2a760  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2a765  ldarg.0
0x2a766  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2a76b  ldarg.0
0x2a76c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a771  ldc.i4.s 0xD
0x2a773  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a778  ldarg.0
0x2a779  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a77e  ldc.i4.s 0xC
0x2a780  ldc.i4.s 0xC
0x2a782  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a787  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a78c  ldarg.0
0x2a78d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a792  ldstr    aSchemalabel// "_schemaLabel"
0x2a797  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a79c  ldarg.0
0x2a79d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a7a2  ldc.i4   0xC4
0x2a7a7  ldc.i4.s 0xE
0x2a7a9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2a7ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2a7b3  ldarg.0
0x2a7b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2a7b9  ldc.i4.s 0xA
0x2a7bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a7c0  ldarg.0
0x2a7c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a7c6  ldc.i4.s 0xE
0x2a7c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a7cd  ldarg.0
0x2a7ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a7d3  ldc.i4.s 0xC
0x2a7d5  ldc.i4   0xBA
0x2a7da  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a7df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a7e4  ldarg.0
0x2a7e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a7ea  ldstr    aBindingslabel// "_bindingsLabel"
0x2a7ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a7f4  ldarg.0
0x2a7f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a7fa  ldc.i4   0xC4
0x2a7ff  ldc.i4.s 0xE
0x2a801  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2a806  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2a80b  ldarg.0
0x2a80c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2a811  ldc.i4.s 0x19
0x2a813  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a818  ldarg.0
0x2a819  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a81e  ldc.i4.s 0xE
0x2a820  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a825  ldarg.0
0x2a826  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a82b  ldc.i4.s 0xC
0x2a82d  ldc.i4   0xCA
0x2a832  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a837  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a83c  ldarg.0
0x2a83d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a842  ldstr    aBindingslistvi// "_bindingsListView"
0x2a847  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a84c  ldarg.0
0x2a84d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a852  ldc.i4   0xA4
0x2a857  ldc.i4   0x87
0x2a85c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2a861  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2a866  ldarg.0
0x2a867  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a86c  ldc.i4.s 0x1E
0x2a86e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a873  ldarg.0
0x2a874  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a879  ldarg.0
0x2a87a  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnBindingsListViewSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x2a880  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2a885  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x2a88a  ldarg.0
0x2a88b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsListView
0x2a890  ldarg.0
0x2a891  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnBindingsListViewGotFocus(object sender, class [mscorlib]System.EventArgs e)
0x2a897  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2a89c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_GotFocus(class [mscorlib]System.EventHandler)
0x2a8a1  ldarg.0
0x2a8a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8a7  ldc.i4.s 0xA
0x2a8a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a8ae  ldarg.0
0x2a8af  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8b4  ldc.i4.3
0x2a8b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x2a8ba  ldarg.0
0x2a8bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8c0  ldc.i4   0x85
0x2a8c5  ldc.i4   0x9A
0x2a8ca  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a8cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a8d4  ldarg.0
0x2a8d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8da  ldstr    aAddbindingbutt// "_addBindingButton"
0x2a8df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a8e4  ldarg.0
0x2a8e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8ea  ldc.i4.s 0x4B
0x2a8ec  ldc.i4.s 0x17
0x2a8ee  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2a8f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2a8f8  ldarg.0
0x2a8f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a8fe  ldc.i4.s 0x14
0x2a900  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a905  ldarg.0
0x2a906  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2a90b  ldarg.0
0x2a90c  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnAddBindingButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x2a912  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2a917  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x2a91c  ldarg.0
0x2a91d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a922  ldc.i4.s 9
0x2a924  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a929  ldarg.0
0x2a92a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a92f  ldc.i4   0xE5
0x2a934  ldc.i4.s 0xC
0x2a936  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a93b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a940  ldarg.0
0x2a941  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a946  ldstr    aPropertieslabe// "_propertiesLabel"
0x2a94b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a950  ldarg.0
0x2a951  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a956  ldc.i4   0x10A
0x2a95b  ldc.i4.s 0xE
0x2a95d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2a962  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2a967  ldarg.0
0x2a968  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2a96d  ldc.i4.s 0x32
0x2a96f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a974  ldarg.0
0x2a975  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a97a  ldc.i4.s 0xA
0x2a97c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a981  ldarg.0
0x2a982  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a987  ldc.i4.3
0x2a988  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x2a98d  ldarg.0
0x2a98e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a993  ldc.i4   0x154
0x2a998  ldc.i4   0x15A
0x2a99d  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2a9a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2a9a7  ldarg.0
0x2a9a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a9ad  ldstr    aCancelbutton// "_cancelButton"
0x2a9b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2a9b7  ldarg.0
0x2a9b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a9bd  ldc.i4.s 0x41
0x2a9bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2a9c4  ldarg.0
0x2a9c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2a9ca  ldarg.0
0x2a9cb  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnCancelButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x2a9d1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2a9d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x2a9db  ldarg.0
0x2a9dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2a9e1  ldc.i4.s 0xA
0x2a9e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2a9e8  ldarg.0
0x2a9e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2a9ee  ldc.i4.3
0x2a9ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x2a9f4  ldarg.0
0x2a9f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2a9fa  ldc.i4   0x104
0x2a9ff  ldc.i4   0x15A
0x2aa04  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2aa09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2aa0e  ldarg.0
0x2aa0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2aa14  ldstr    aOkbutton// "_okButton"
0x2aa19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2aa1e  ldarg.0
0x2aa1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2aa24  ldc.i4.s 0x3C
0x2aa26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2aa2b  ldarg.0
0x2aa2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2aa31  ldarg.0
0x2aa32  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnOKButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x2aa38  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2aa3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x2aa42  ldarg.0
0x2aa43  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa48  ldc.i4.s 0xA
0x2aa4a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2aa4f  ldarg.0
0x2aa50  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa55  ldc.i4.3
0x2aa56  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x2aa5b  ldarg.0
0x2aa5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa61  ldc.i4   0x1A4
0x2aa66  ldc.i4   0x15A
0x2aa6b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2aa70  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2aa75  ldarg.0
0x2aa76  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa7b  ldstr    aApplybutton// "_applyButton"
0x2aa80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2aa85  ldarg.0
0x2aa86  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa8b  ldc.i4.s 0x3C
0x2aa8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2aa92  ldarg.0
0x2aa93  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aa98  ldarg.0
0x2aa99  ldftn    instance void System.Web.UI.Design.WebControls.MenuBindingsEditorForm::OnApplyButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x2aa9f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2aaa4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x2aaa9  ldarg.0
0x2aaaa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2aaaf  ldc.i4.0
0x2aab0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x2aab5  ldarg.0
0x2aab6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2aabb  ldc.i4.s 0xB
0x2aabd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2aac2  ldarg.0
0x2aac3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2aac8  ldc.i4.1
0x2aac9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_CommandsVisibleIfAvailable(bool)
0x2aace  ldarg.0
0x2aacf  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2aad4  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_HSplit()
0x2aad9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x2aade  ldarg.0
0x2aadf  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2aae4  ldc.i4.0
0x2aae5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_LargeButtons(bool)
0x2aaea  ldarg.0
0x2aaeb  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2aaf0  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ScrollBar()
0x2aaf5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_LineColor(valuetype [System.Drawing]System.Drawing.Color)
0x2aafa  ldarg.0
0x2aafb  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertyGrid
0x2ab00  ldc.i4   0xE5
0x2ab05  ldc.i4.s 0x1C
0x2ab07  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2ab0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2ab11  ldarg.0
  ... truncated ...
```
