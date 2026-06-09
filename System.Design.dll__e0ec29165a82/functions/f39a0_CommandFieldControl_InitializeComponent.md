# CommandFieldControl::InitializeComponent

- ea: `0xf39a0`
- end: `0xf3dbd`
- name: `CommandFieldControl::InitializeComponent`
- size: `1053`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x8ef40`
- `0xf1df0`
- `0xf39a0`

## string_xrefs

- `0xf3ab7`: `DCFAdd_CommandButtons`
- `0xf3af1`: `DCFAdd_Delete`
- `0xf3b06`: `DCFAdd_DeleteDesc`
- `0xf3c2f`: `DCFAdd_EditUpdate`
- `0xf3c44`: `DCFAdd_EditUpdateDesc`

## pseudocode

```c

```

## disassembly

```asm
0xf39a0  ldarg.0
0xf39a1  call     instance void DataControlFieldControl::InitializeComponent()
0xf39a6  ldarg.0
0xf39a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf39ac  stfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_buttonTypeLabel
0xf39b1  ldarg.0
0xf39b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf39b7  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf39bc  ldarg.0
0xf39bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf39c2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_commandButtonsLabel
0xf39c7  ldarg.0
0xf39c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf39cd  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf39d2  ldarg.0
0xf39d3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf39d8  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf39dd  ldarg.0
0xf39de  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf39e3  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf39e8  ldarg.0
0xf39e9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf39ee  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf39f3  ldarg.0
0xf39f4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf39f9  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf39fe  ldarg.0
0xf39ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_buttonTypeLabel
0xf3a04  ldstr    aDcfaddButtonty// "DCFAdd_ButtonType"
0xf3a09  call     string System.Design.SR::GetString(string name)
0xf3a0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3a13  ldarg.0
0xf3a14  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_buttonTypeLabel
0xf3a19  ldc.i4   0x100
0xf3a1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3a23  ldarg.0
0xf3a24  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_buttonTypeLabel
0xf3a29  ldc.i4.0
0xf3a2a  ldc.i4.s 0x2B
0xf3a2c  ldc.i4   0x10E
0xf3a31  ldc.i4.s 0x11
0xf3a33  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3a38  ldarg.0
0xf3a39  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3a3e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf3a43  ldc.i4.2
0xf3a44  stloc.0
0xf3a45  ldloca.s 0
0xf3a47  constrained. [System.Web]System.Web.UI.WebControls.ButtonType
0xf3a4d  callvirt instance string [mscorlib]System.Object::ToString()
0xf3a52  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf3a57  pop
0xf3a58  ldarg.0
0xf3a59  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3a5e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf3a63  ldc.i4.0
0xf3a64  stloc.0
0xf3a65  ldloca.s 0
0xf3a67  constrained. [System.Web]System.Web.UI.WebControls.ButtonType
0xf3a6d  callvirt instance string [mscorlib]System.Object::ToString()
0xf3a72  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf3a77  pop
0xf3a78  ldarg.0
0xf3a79  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3a7e  ldc.i4.0
0xf3a7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_SelectedIndex(int32)
0xf3a84  ldarg.0
0xf3a85  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3a8a  ldc.i4.2
0xf3a8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0xf3a90  ldarg.0
0xf3a91  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3a96  ldc.i4.1
0xf3a97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3a9c  ldarg.0
0xf3a9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3aa2  ldc.i4.0
0xf3aa3  ldc.i4.s 0x3E
0xf3aa5  ldc.i4   0x10E
0xf3aaa  ldc.i4.s 0x14
0xf3aac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3ab1  ldarg.0
0xf3ab2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_commandButtonsLabel
0xf3ab7  ldstr    aDcfaddCommandb// "DCFAdd_CommandButtons"
0xf3abc  call     string System.Design.SR::GetString(string name)
0xf3ac1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3ac6  ldarg.0
0xf3ac7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_commandButtonsLabel
0xf3acc  ldc.i4   0x100
0xf3ad1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3ad6  ldarg.0
0xf3ad7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_commandButtonsLabel
0xf3adc  ldc.i4.0
0xf3add  ldc.i4.s 0x56
0xf3adf  ldc.i4   0x10E
0xf3ae4  ldc.i4.s 0x11
0xf3ae6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3aeb  ldarg.0
0xf3aec  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3af1  ldstr    aDcfaddDelete// "DCFAdd_Delete"
0xf3af6  call     string System.Design.SR::GetString(string name)
0xf3afb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3b00  ldarg.0
0xf3b01  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3b06  ldstr    aDcfaddDeletede// "DCFAdd_DeleteDesc"
0xf3b0b  call     string System.Design.SR::GetString(string name)
0xf3b10  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf3b15  ldarg.0
0xf3b16  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3b1b  ldc.i4.1
0xf3b1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3b21  ldarg.0
0xf3b22  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3b27  ldc.i4.1
0xf3b28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3b2d  ldarg.0
0xf3b2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3b33  ldc.i4.2
0xf3b34  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3b39  ldarg.0
0xf3b3a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_deleteBox
0xf3b3f  ldc.i4.8
0xf3b40  ldc.i4.s 0x69
0xf3b42  ldc.i4.s 0x7D
0xf3b44  ldc.i4.s 0x14
0xf3b46  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3b4b  ldarg.0
0xf3b4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b51  ldstr    aDcfaddSelect// "DCFAdd_Select"
0xf3b56  call     string System.Design.SR::GetString(string name)
0xf3b5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3b60  ldarg.0
0xf3b61  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b66  ldstr    aDcfaddSelectde// "DCFAdd_SelectDesc"
0xf3b6b  call     string System.Design.SR::GetString(string name)
0xf3b70  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf3b75  ldarg.0
0xf3b76  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b7b  ldc.i4.1
0xf3b7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3b81  ldarg.0
0xf3b82  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b87  ldc.i4.1
0xf3b88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3b8d  ldarg.0
0xf3b8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b93  ldc.i4.4
0xf3b94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3b99  ldarg.0
0xf3b9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3b9f  ldc.i4.8
0xf3ba0  ldc.i4.s 0x7D
0xf3ba2  ldc.i4.s 0x7D
0xf3ba4  ldc.i4.s 0x14
0xf3ba6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3bab  ldarg.0
0xf3bac  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3bb1  ldstr    aDcfaddShowcanc// "DCFAdd_ShowCancel"
0xf3bb6  call     string System.Design.SR::GetString(string name)
0xf3bbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3bc0  ldarg.0
0xf3bc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3bc6  ldstr    aDcfaddShowcanc_0// "DCFAdd_ShowCancelDesc"
0xf3bcb  call     string System.Design.SR::GetString(string name)
0xf3bd0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf3bd5  ldarg.0
0xf3bd6  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3bdb  ldc.i4.1
0xf3bdc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3be1  ldarg.0
0xf3be2  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3be7  ldc.i4.1
0xf3be8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3bed  ldarg.0
0xf3bee  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3bf3  ldc.i4.0
0xf3bf4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xf3bf9  ldarg.0
0xf3bfa  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3bff  ldc.i4.1
0xf3c00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0xf3c05  ldarg.0
0xf3c06  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3c0b  ldc.i4.6
0xf3c0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3c11  ldarg.0
0xf3c12  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_cancelBox
0xf3c17  ldc.i4.8
0xf3c18  ldc.i4   0x91
0xf3c1d  ldc.i4   0x10E
0xf3c22  ldc.i4.s 0x2C
0xf3c24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3c29  ldarg.0
0xf3c2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c2f  ldstr    aDcfaddEditupda// "DCFAdd_EditUpdate"
0xf3c34  call     string System.Design.SR::GetString(string name)
0xf3c39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3c3e  ldarg.0
0xf3c3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c44  ldstr    aDcfaddEditupda_0// "DCFAdd_EditUpdateDesc"
0xf3c49  call     string System.Design.SR::GetString(string name)
0xf3c4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf3c53  ldarg.0
0xf3c54  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c59  ldc.i4.1
0xf3c5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3c5f  ldarg.0
0xf3c60  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c65  ldc.i4.1
0xf3c66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3c6b  ldarg.0
0xf3c6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c71  ldc.i4.3
0xf3c72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3c77  ldarg.0
0xf3c78  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c7d  ldarg.0
0xf3c7e  ldftn    instance void CommandFieldControl::OnCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0xf3c84  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf3c89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0xf3c8e  ldarg.0
0xf3c8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_updateBox
0xf3c94  ldc.i4   0x8B
0xf3c99  ldc.i4.s 0x69
0xf3c9b  ldc.i4.s 0x7D
0xf3c9d  ldc.i4.s 0x14
0xf3c9f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3ca4  ldarg.0
0xf3ca5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3caa  ldstr    aDcfaddNewinser// "DCFAdd_NewInsert"
0xf3caf  call     string System.Design.SR::GetString(string name)
0xf3cb4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf3cb9  ldarg.0
0xf3cba  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3cbf  ldstr    aDcfaddNewinser_0// "DCFAdd_NewInsertDesc"
0xf3cc4  call     string System.Design.SR::GetString(string name)
0xf3cc9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf3cce  ldarg.0
0xf3ccf  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3cd4  ldc.i4.1
0xf3cd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3cda  ldarg.0
0xf3cdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3ce0  ldc.i4.1
0xf3ce1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf3ce6  ldarg.0
0xf3ce7  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3cec  ldc.i4.5
0xf3ced  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf3cf2  ldarg.0
0xf3cf3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3cf8  ldarg.0
0xf3cf9  ldftn    instance void CommandFieldControl::OnCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0xf3cff  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf3d04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0xf3d09  ldarg.0
0xf3d0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3d0f  ldc.i4.8
0xf3d10  ldc.i4.s 0x7D
0xf3d12  ldc.i4.s 0x7D
0xf3d14  ldc.i4.s 0x14
0xf3d16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf3d1b  ldarg.0
0xf3d1c  ldfld    class [mscorlib]System.Type DataControlFieldControl::_controlType
0xf3d21  ldtoken  [System.Web]System.Web.UI.WebControls.GridView
0xf3d26  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf3d2b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf3d30  brfalse.s loc_F3D40
0xf3d32  ldarg.0
0xf3d33  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_insertBox
0xf3d38  ldc.i4.0
0xf3d39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf3d3e  br.s     loc_F3D63
0xf3d40  ldarg.0
0xf3d41  ldfld    class [mscorlib]System.Type DataControlFieldControl::_controlType
0xf3d46  ldtoken  [System.Web]System.Web.UI.WebControls.DetailsView
0xf3d4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf3d50  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf3d55  brfalse.s loc_F3D63
0xf3d57  ldarg.0
0xf3d58  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox CommandFieldControl::_selectBox
0xf3d5d  ldc.i4.0
0xf3d5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf3d63  ldarg.0
0xf3d64  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf3d69  ldc.i4.8
0xf3d6a  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0xf3d6f  dup
0xf3d70  ldc.i4.0
0xf3d71  ldarg.0
0xf3d72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CommandFieldControl::_buttonTypeLabel
0xf3d77  stelem.ref
0xf3d78  dup
0xf3d79  ldc.i4.1
0xf3d7a  ldarg.0
0xf3d7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox CommandFieldControl::_buttonTypeList
0xf3d80  stelem.ref
0xf3d81  dup
0xf3d82  ldc.i4.2
0xf3d83  ldarg.0
  ... truncated ...
```
