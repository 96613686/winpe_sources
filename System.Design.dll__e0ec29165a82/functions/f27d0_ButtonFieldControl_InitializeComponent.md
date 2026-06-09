# ButtonFieldControl::InitializeComponent

- ea: `0xf27d0`
- end: `0xf2ac6`
- name: `ButtonFieldControl::InitializeComponent`
- size: `758`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x8ef40`
- `0xf1df0`
- `0xf27d0`

## string_xrefs

- `0xf2952`: `Update`
- `0xf2926`: `Delete`
- `0xf28d1`: `DCFAdd_CommandName`

## pseudocode

```c

```

## disassembly

```asm
0xf27d0  ldarg.0
0xf27d1  call     instance void DataControlFieldControl::InitializeComponent()
0xf27d6  ldarg.0
0xf27d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf27dc  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_buttonTypeLabel
0xf27e1  ldarg.0
0xf27e2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf27e7  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_commandNameLabel
0xf27ec  ldarg.0
0xf27ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf27f2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_textLabel
0xf27f7  ldarg.0
0xf27f8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf27fd  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf2802  ldarg.0
0xf2803  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf2808  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf280d  ldarg.0
0xf280e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2813  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonFieldControl::_textBox
0xf2818  ldarg.0
0xf2819  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_buttonTypeLabel
0xf281e  ldstr    aDcfaddButtonty// "DCFAdd_ButtonType"
0xf2823  call     string System.Design.SR::GetString(string name)
0xf2828  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf282d  ldarg.0
0xf282e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_buttonTypeLabel
0xf2833  ldc.i4   0x100
0xf2838  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf283d  ldarg.0
0xf283e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_buttonTypeLabel
0xf2843  ldc.i4.0
0xf2844  ldc.i4.s 0x2B
0xf2846  ldc.i4   0x10E
0xf284b  ldc.i4.s 0x11
0xf284d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2852  ldarg.0
0xf2853  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf2858  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf285d  ldc.i4.2
0xf285e  stloc.0
0xf285f  ldloca.s 0
0xf2861  constrained. [System.Web]System.Web.UI.WebControls.ButtonType
0xf2867  callvirt instance string [mscorlib]System.Object::ToString()
0xf286c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf2871  pop
0xf2872  ldarg.0
0xf2873  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf2878  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf287d  ldc.i4.0
0xf287e  stloc.0
0xf287f  ldloca.s 0
0xf2881  constrained. [System.Web]System.Web.UI.WebControls.ButtonType
0xf2887  callvirt instance string [mscorlib]System.Object::ToString()
0xf288c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf2891  pop
0xf2892  ldarg.0
0xf2893  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf2898  ldc.i4.0
0xf2899  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_SelectedIndex(int32)
0xf289e  ldarg.0
0xf289f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf28a4  ldc.i4.2
0xf28a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0xf28aa  ldarg.0
0xf28ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf28b0  ldc.i4.1
0xf28b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf28b6  ldarg.0
0xf28b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf28bc  ldc.i4.0
0xf28bd  ldc.i4.s 0x3E
0xf28bf  ldc.i4   0x10E
0xf28c4  ldc.i4.s 0x14
0xf28c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf28cb  ldarg.0
0xf28cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_commandNameLabel
0xf28d1  ldstr    aDcfaddCommandn// "DCFAdd_CommandName"
0xf28d6  call     string System.Design.SR::GetString(string name)
0xf28db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf28e0  ldarg.0
0xf28e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_commandNameLabel
0xf28e6  ldc.i4   0x100
0xf28eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf28f0  ldarg.0
0xf28f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_commandNameLabel
0xf28f6  ldc.i4.0
0xf28f7  ldc.i4.s 0x56
0xf28f9  ldc.i4   0x10E
0xf28fe  ldc.i4.s 0x11
0xf2900  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2905  ldarg.0
0xf2906  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf290b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf2910  ldstr    aCancel// "Cancel"
0xf2915  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf291a  pop
0xf291b  ldarg.0
0xf291c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf2921  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf2926  ldstr    aDelete// "Delete"
0xf292b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf2930  pop
0xf2931  ldarg.0
0xf2932  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf2937  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf293c  ldstr    aEdit// "Edit"
0xf2941  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf2946  pop
0xf2947  ldarg.0
0xf2948  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf294d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf2952  ldstr    aUpdate// "Update"
0xf2957  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xf295c  pop
0xf295d  ldarg.0
0xf295e  ldfld    class [mscorlib]System.Type DataControlFieldControl::_controlType
0xf2963  ldtoken  [System.Web]System.Web.UI.WebControls.DetailsView
0xf2968  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf296d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf2972  brfalse.s loc_F29A2
0xf2974  ldarg.0
0xf2975  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf297a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf297f  ldc.i4.3
0xf2980  ldstr    aInsert// "Insert"
0xf2985  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Insert(int32, object)
0xf298a  ldarg.0
0xf298b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf2990  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf2995  ldc.i4.4
0xf2996  ldstr    aNew// "New"
0xf299b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Insert(int32, object)
0xf29a0  br.s     loc_F29CF
0xf29a2  ldarg.0
0xf29a3  ldfld    class [mscorlib]System.Type DataControlFieldControl::_controlType
0xf29a8  ldtoken  [System.Web]System.Web.UI.WebControls.GridView
0xf29ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf29b2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf29b7  brfalse.s loc_F29CF
0xf29b9  ldarg.0
0xf29ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf29bf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf29c4  ldc.i4.3
0xf29c5  ldstr    aSelect_1// "Select"
0xf29ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Insert(int32, object)
0xf29cf  ldarg.0
0xf29d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf29d5  ldc.i4.0
0xf29d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_SelectedIndex(int32)
0xf29db  ldarg.0
0xf29dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf29e1  ldc.i4.2
0xf29e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0xf29e7  ldarg.0
0xf29e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf29ed  ldc.i4.2
0xf29ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf29f3  ldarg.0
0xf29f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf29f9  ldc.i4.0
0xf29fa  ldc.i4.s 0x69
0xf29fc  ldc.i4   0x10E
0xf2a01  ldc.i4.s 0x14
0xf2a03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2a08  ldarg.0
0xf2a09  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_textLabel
0xf2a0e  ldstr    aDcfaddText// "DCFAdd_Text"
0xf2a13  call     string System.Design.SR::GetString(string name)
0xf2a18  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2a1d  ldarg.0
0xf2a1e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_textLabel
0xf2a23  ldc.i4   0x100
0xf2a28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf2a2d  ldarg.0
0xf2a2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_textLabel
0xf2a33  ldc.i4.0
0xf2a34  ldc.i4   0x81
0xf2a39  ldc.i4   0x10E
0xf2a3e  ldc.i4.s 0x11
0xf2a40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2a45  ldarg.0
0xf2a46  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonFieldControl::_textBox
0xf2a4b  ldc.i4.3
0xf2a4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2a51  ldarg.0
0xf2a52  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonFieldControl::_textBox
0xf2a57  ldstr    aDcfeditorButto// "DCFEditor_Button"
0xf2a5c  call     string System.Design.SR::GetString(string name)
0xf2a61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2a66  ldarg.0
0xf2a67  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonFieldControl::_textBox
0xf2a6c  ldc.i4.0
0xf2a6d  ldc.i4   0x94
0xf2a72  ldc.i4   0x10E
0xf2a77  ldc.i4.s 0x14
0xf2a79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2a7e  ldarg.0
0xf2a7f  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf2a84  ldc.i4.6
0xf2a85  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0xf2a8a  dup
0xf2a8b  ldc.i4.0
0xf2a8c  ldarg.0
0xf2a8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_buttonTypeLabel
0xf2a92  stelem.ref
0xf2a93  dup
0xf2a94  ldc.i4.1
0xf2a95  ldarg.0
0xf2a96  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_commandNameLabel
0xf2a9b  stelem.ref
0xf2a9c  dup
0xf2a9d  ldc.i4.2
0xf2a9e  ldarg.0
0xf2a9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ButtonFieldControl::_textLabel
0xf2aa4  stelem.ref
0xf2aa5  dup
0xf2aa6  ldc.i4.3
0xf2aa7  ldarg.0
0xf2aa8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_buttonTypeList
0xf2aad  stelem.ref
0xf2aae  dup
0xf2aaf  ldc.i4.4
0xf2ab0  ldarg.0
0xf2ab1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonFieldControl::_commandNameList
0xf2ab6  stelem.ref
0xf2ab7  dup
0xf2ab8  ldc.i4.5
0xf2ab9  ldarg.0
0xf2aba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonFieldControl::_textBox
0xf2abf  stelem.ref
0xf2ac0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.Control[])
0xf2ac5  ret
```
