# ImageFieldControl::InitializeComponent

- ea: `0xf40a0`
- end: `0xf4310`
- name: `ImageFieldControl::InitializeComponent`
- size: `624`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8ef40`
- `0xf1da0`
- `0xf1df0`
- `0xf40a0`

## string_xrefs

- `0xf423a`: `DCFAdd_ReadOnly`
- `0xf418d`: `DCFAdd_LinkFormatString`

## pseudocode

```c

```

## disassembly

```asm
0xf40a0  ldarg.0
0xf40a1  call     instance void DataControlFieldControl::InitializeComponent()
0xf40a6  ldarg.0
0xf40a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf40ac  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf40b1  ldarg.0
0xf40b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf40b7  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf40bc  ldarg.0
0xf40bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf40c2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_imageUrlFieldLabel
0xf40c7  ldarg.0
0xf40c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xf40cd  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox ImageFieldControl::_readOnlyCheckBox
0xf40d2  ldarg.0
0xf40d3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf40d8  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_urlFormatBox
0xf40dd  ldarg.0
0xf40de  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf40e3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf40e8  ldarg.0
0xf40e9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf40ee  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf40f3  ldarg.0
0xf40f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_imageUrlFieldLabel
0xf40f9  ldstr    aDcfaddDatafiel// "DCFAdd_DataField"
0xf40fe  call     string System.Design.SR::GetString(string name)
0xf4103  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf4108  ldarg.0
0xf4109  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_imageUrlFieldLabel
0xf410e  ldc.i4   0x100
0xf4113  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf4118  ldarg.0
0xf4119  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_imageUrlFieldLabel
0xf411e  ldc.i4.0
0xf411f  ldc.i4.s 0x2B
0xf4121  ldc.i4   0x10E
0xf4126  ldc.i4.s 0x11
0xf4128  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf412d  ldarg.0
0xf412e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf4133  ldc.i4.2
0xf4134  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0xf4139  ldarg.0
0xf413a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf413f  ldc.i4.1
0xf4140  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf4145  ldarg.0
0xf4146  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf414b  ldc.i4.0
0xf414c  ldc.i4.s 0x3E
0xf414e  ldc.i4   0x10E
0xf4153  ldc.i4.s 0x14
0xf4155  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf415a  ldarg.0
0xf415b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf4160  ldc.i4.2
0xf4161  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf4166  ldarg.0
0xf4167  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf416c  ldc.i4.0
0xf416d  ldc.i4.s 0x3E
0xf416f  ldc.i4   0x10E
0xf4174  ldc.i4.s 0x14
0xf4176  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf417b  ldarg.0
0xf417c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf4181  ldc.i4.3
0xf4182  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf4187  ldarg.0
0xf4188  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf418d  ldstr    aDcfaddLinkform// "DCFAdd_LinkFormatString"
0xf4192  call     string System.Design.SR::GetString(string name)
0xf4197  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf419c  ldarg.0
0xf419d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf41a2  ldc.i4   0x100
0xf41a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf41ac  ldarg.0
0xf41ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf41b2  ldc.i4.0
0xf41b3  ldc.i4.s 0x56
0xf41b5  ldc.i4   0x10E
0xf41ba  ldc.i4.s 0x11
0xf41bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf41c1  ldarg.0
0xf41c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_urlFormatBox
0xf41c7  ldc.i4.4
0xf41c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf41cd  ldarg.0
0xf41ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_urlFormatBox
0xf41d3  ldc.i4.0
0xf41d4  ldc.i4.s 0x69
0xf41d6  ldc.i4   0x10E
0xf41db  ldc.i4.s 0x14
0xf41dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf41e2  ldarg.0
0xf41e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf41e8  ldc.i4.0
0xf41e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xf41ee  ldarg.0
0xf41ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf41f4  ldstr    aDcfaddExamplef// "DCFAdd_ExampleFormatString"
0xf41f9  call     string System.Design.SR::GetString(string name)
0xf41fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf4203  ldarg.0
0xf4204  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf4209  ldc.i4   0x100
0xf420e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf4213  ldarg.0
0xf4214  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf4219  ldc.i4.0
0xf421a  ldc.i4.s 0x7D
0xf421c  ldc.i4   0x10E
0xf4221  ldc.i4.s 0x11
0xf4223  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf4228  ldarg.0
0xf4229  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox ImageFieldControl::_readOnlyCheckBox
0xf422e  ldc.i4.5
0xf422f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf4234  ldarg.0
0xf4235  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox ImageFieldControl::_readOnlyCheckBox
0xf423a  ldstr    aDcfaddReadonly// "DCFAdd_ReadOnly"
0xf423f  call     string System.Design.SR::GetString(string name)
0xf4244  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf4249  ldarg.0
0xf424a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox ImageFieldControl::_readOnlyCheckBox
0xf424f  ldc.i4.0
0xf4250  ldc.i4   0x90
0xf4255  ldc.i4   0x10E
0xf425a  ldc.i4.s 0x14
0xf425c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf4261  ldarg.0
0xf4262  ldfld    bool DataControlFieldControl::_haveSchema
0xf4267  brfalse.s loc_F42A7
0xf4269  ldarg.0
0xf426a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf426f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xf4274  ldarg.0
0xf4275  call     instance string[] DataControlFieldControl::GetFieldSchemaNames()
0xf427a  stloc.0
0xf427b  ldloc.0
0xf427c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::AddRange(object[])
0xf4281  ldarg.0
0xf4282  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf4287  ldc.i4.0
0xf4288  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_SelectedIndex(int32)
0xf428d  ldarg.0
0xf428e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf4293  ldc.i4.1
0xf4294  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf4299  ldarg.0
0xf429a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf429f  ldc.i4.0
0xf42a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf42a5  br.s     loc_F42BF
0xf42a7  ldarg.0
0xf42a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf42ad  ldc.i4.0
0xf42ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf42b3  ldarg.0
0xf42b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf42b9  ldc.i4.1
0xf42ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xf42bf  ldarg.0
0xf42c0  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf42c5  ldc.i4.7
0xf42c6  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0xf42cb  dup
0xf42cc  ldc.i4.0
0xf42cd  ldarg.0
0xf42ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_imageUrlFieldLabel
0xf42d3  stelem.ref
0xf42d4  dup
0xf42d5  ldc.i4.1
0xf42d6  ldarg.0
0xf42d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_imageUrlFieldBox
0xf42dc  stelem.ref
0xf42dd  dup
0xf42de  ldc.i4.2
0xf42df  ldarg.0
0xf42e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ImageFieldControl::_imageUrlFieldList
0xf42e5  stelem.ref
0xf42e6  dup
0xf42e7  ldc.i4.3
0xf42e8  ldarg.0
0xf42e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox ImageFieldControl::_readOnlyCheckBox
0xf42ee  stelem.ref
0xf42ef  dup
0xf42f0  ldc.i4.4
0xf42f1  ldarg.0
0xf42f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatBoxLabel
0xf42f7  stelem.ref
0xf42f8  dup
0xf42f9  ldc.i4.5
0xf42fa  ldarg.0
0xf42fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ImageFieldControl::_urlFormatBox
0xf4300  stelem.ref
0xf4301  dup
0xf4302  ldc.i4.6
0xf4303  ldarg.0
0xf4304  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ImageFieldControl::_urlFormatExampleLabel
0xf4309  stelem.ref
0xf430a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.Control[])
0xf430f  ret
```
