# System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::InitializeComponent

- ea: `0x44b90`
- end: `0x453f9`
- name: `System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::InitializeComponent`
- size: `2153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x44710`

## callees

- `0x51a60`
- `0x51a90`
- `0x8ef40`
- `0xe3d40`

## string_xrefs

- `0x45152`: `_moveBindingUpButton`
- `0x451c1`: `_moveBindingDownButton`
- `0x45230`: `_deleteBindingButton`

## pseudocode

```c

```

## disassembly

```asm
0x44b90  ldarg.0
0x44b91  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x44b96  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44b9b  ldarg.0
0x44b9c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x44ba1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44ba6  ldarg.0
0x44ba7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0x44bac  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44bb1  ldarg.0
0x44bb2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44bb7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44bbc  ldarg.0
0x44bbd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x44bc2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44bc7  ldarg.0
0x44bc8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44bcd  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44bd2  ldarg.0
0x44bd3  ldarg.0
0x44bd4  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.DesignerForm::get_ServiceProvider()
0x44bd9  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x44bde  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44be3  ldarg.0
0x44be4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x44be9  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaTreeView
0x44bee  ldarg.0
0x44bef  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44bf4  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingUpButton
0x44bf9  ldarg.0
0x44bfa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44bff  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingDownButton
0x44c04  ldarg.0
0x44c05  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44c0a  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_deleteBindingButton
0x44c0f  ldarg.0
0x44c10  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x44c15  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_autogenerateBindingsCheckBox
0x44c1a  ldarg.0
0x44c1b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44c20  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44c25  ldarg.0
0x44c26  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x44c2b  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44c30  ldarg.0
0x44c31  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x44c36  ldarg.0
0x44c37  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44c3c  ldc.i4.s 0xD
0x44c3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44c43  ldarg.0
0x44c44  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44c49  ldc.i4.s 0xC
0x44c4b  ldc.i4.s 0xC
0x44c4d  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44c52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44c57  ldarg.0
0x44c58  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44c5d  ldstr    aSchemalabel// "_schemaLabel"
0x44c62  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44c67  ldarg.0
0x44c68  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44c6d  ldc.i4   0xC4
0x44c72  ldc.i4.s 0xE
0x44c74  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x44c79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x44c7e  ldarg.0
0x44c7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x44c84  ldc.i4.s 0xA
0x44c86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44c8b  ldarg.0
0x44c8c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44c91  ldc.i4.s 0xE
0x44c93  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44c98  ldarg.0
0x44c99  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44c9e  ldc.i4.s 0xC
0x44ca0  ldc.i4   0xBA
0x44ca5  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44caa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44caf  ldarg.0
0x44cb0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44cb5  ldstr    aBindingslabel// "_bindingsLabel"
0x44cba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44cbf  ldarg.0
0x44cc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44cc5  ldc.i4   0xC4
0x44cca  ldc.i4.s 0xE
0x44ccc  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x44cd1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x44cd6  ldarg.0
0x44cd7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x44cdc  ldc.i4.s 0x19
0x44cde  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44ce3  ldarg.0
0x44ce4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44ce9  ldc.i4.s 0xE
0x44ceb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44cf0  ldarg.0
0x44cf1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44cf6  ldc.i4.s 0xC
0x44cf8  ldc.i4   0xCA
0x44cfd  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44d02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44d07  ldarg.0
0x44d08  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44d0d  ldstr    aBindingslistvi// "_bindingsListView"
0x44d12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44d17  ldarg.0
0x44d18  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44d1d  ldc.i4   0xA4
0x44d22  ldc.i4.s 0x70
0x44d24  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x44d29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x44d2e  ldarg.0
0x44d2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44d34  ldc.i4.s 0x1E
0x44d36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44d3b  ldarg.0
0x44d3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44d41  ldarg.0
0x44d42  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnBindingsListViewSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x44d48  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44d4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x44d52  ldarg.0
0x44d53  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsListView
0x44d58  ldarg.0
0x44d59  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnBindingsListViewGotFocus(object sender, class [mscorlib]System.EventArgs e)
0x44d5f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44d64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_GotFocus(class [mscorlib]System.EventHandler)
0x44d69  ldarg.0
0x44d6a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44d6f  ldc.i4.s 0xA
0x44d71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44d76  ldarg.0
0x44d77  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44d7c  ldc.i4.3
0x44d7d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x44d82  ldarg.0
0x44d83  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44d88  ldc.i4   0x85
0x44d8d  ldc.i4   0x9A
0x44d92  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44d97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44d9c  ldarg.0
0x44d9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44da2  ldstr    aAddbindingbutt// "_addBindingButton"
0x44da7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44dac  ldarg.0
0x44dad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44db2  ldc.i4.s 0x4B
0x44db4  ldc.i4.s 0x17
0x44db6  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x44dbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x44dc0  ldarg.0
0x44dc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44dc6  ldc.i4.s 0x14
0x44dc8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44dcd  ldarg.0
0x44dce  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x44dd3  ldarg.0
0x44dd4  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnAddBindingButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x44dda  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44ddf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x44de4  ldarg.0
0x44de5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44dea  ldc.i4.s 9
0x44dec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44df1  ldarg.0
0x44df2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44df7  ldc.i4   0xE5
0x44dfc  ldc.i4.s 0xC
0x44dfe  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44e03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44e08  ldarg.0
0x44e09  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44e0e  ldstr    aPropertieslabe// "_propertiesLabel"
0x44e13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44e18  ldarg.0
0x44e19  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44e1e  ldc.i4   0x10A
0x44e23  ldc.i4.s 0xE
0x44e25  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x44e2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x44e2f  ldarg.0
0x44e30  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x44e35  ldc.i4.s 0x32
0x44e37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44e3c  ldarg.0
0x44e3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e42  ldc.i4.s 0xA
0x44e44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44e49  ldarg.0
0x44e4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e4f  ldc.i4.3
0x44e50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x44e55  ldarg.0
0x44e56  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e5b  ldc.i4   0x154
0x44e60  ldc.i4   0x15A
0x44e65  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44e6a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44e6f  ldarg.0
0x44e70  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e75  ldstr    aCancelbutton// "_cancelButton"
0x44e7a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44e7f  ldarg.0
0x44e80  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e85  ldc.i4.s 0x41
0x44e87  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44e8c  ldarg.0
0x44e8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x44e92  ldarg.0
0x44e93  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnCancelButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x44e99  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44e9e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x44ea3  ldarg.0
0x44ea4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44ea9  ldc.i4.s 0xA
0x44eab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44eb0  ldarg.0
0x44eb1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44eb6  ldc.i4.3
0x44eb7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x44ebc  ldarg.0
0x44ebd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44ec2  ldc.i4   0x104
0x44ec7  ldc.i4   0x15A
0x44ecc  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44ed1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44ed6  ldarg.0
0x44ed7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44edc  ldstr    aOkbutton// "_okButton"
0x44ee1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44ee6  ldarg.0
0x44ee7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44eec  ldc.i4.s 0x3C
0x44eee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44ef3  ldarg.0
0x44ef4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x44ef9  ldarg.0
0x44efa  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnOKButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x44f00  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44f05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x44f0a  ldarg.0
0x44f0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f10  ldc.i4.s 0xA
0x44f12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44f17  ldarg.0
0x44f18  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f1d  ldc.i4.3
0x44f1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x44f23  ldarg.0
0x44f24  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f29  ldc.i4   0x1A4
0x44f2e  ldc.i4   0x15A
0x44f33  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x44f38  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x44f3d  ldarg.0
0x44f3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f43  ldstr    aApplybutton// "_applyButton"
0x44f48  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x44f4d  ldarg.0
0x44f4e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f53  ldc.i4.s 0x3C
0x44f55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x44f5a  ldarg.0
0x44f5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f60  ldarg.0
0x44f61  ldftn    instance void System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::OnApplyButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x44f67  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x44f6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x44f71  ldarg.0
0x44f72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x44f77  ldc.i4.0
0x44f78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x44f7d  ldarg.0
0x44f7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44f83  ldc.i4.s 0xB
0x44f85  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x44f8a  ldarg.0
0x44f8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44f90  ldc.i4.1
0x44f91  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_CommandsVisibleIfAvailable(bool)
0x44f96  ldarg.0
0x44f97  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44f9c  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_HSplit()
0x44fa1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x44fa6  ldarg.0
0x44fa7  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44fac  ldc.i4.0
0x44fad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_LargeButtons(bool)
0x44fb2  ldarg.0
0x44fb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44fb8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ScrollBar()
0x44fbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_LineColor(valuetype [System.Drawing]System.Drawing.Color)
0x44fc2  ldarg.0
0x44fc3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertyGrid
0x44fc8  ldc.i4   0xE5
0x44fcd  ldc.i4.s 0x1C
  ... truncated ...
```
