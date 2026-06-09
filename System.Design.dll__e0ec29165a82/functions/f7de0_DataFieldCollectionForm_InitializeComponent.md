# DataFieldCollectionForm::InitializeComponent

- ea: `0xf7de0`
- end: `0xf8625`
- name: `DataFieldCollectionForm::InitializeComponent`
- size: `2117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xf7b10`

## callees

- `0x52b10`
- `0x8ef40`
- `0xef300`
- `0xf7de0`

## string_xrefs

- `0xf7feb`: `DataFieldCollection_MoveRight`
- `0xf8000`: `DataFieldCollection_MoveRightDesc`
- `0xf8070`: `DataFieldCollection_MoveLeft`
- `0xf8085`: `DataFieldCollection_MoveLeftDesc`
- `0xf8171`: `DataFieldCollection_MoveUp`
- `0xf8186`: `DataFieldCollection_MoveUpDesc`
- `0xf8210`: `DataFieldCollection_MoveDown`
- `0xf8225`: `DataFieldCollection_MoveDownDesc`

## pseudocode

```c

```

## disassembly

```asm
0xf7de0  ldc.i4   0xD9
0xf7de5  stloc.0
0xf7de6  ldc.i4   0x16C
0xf7deb  stloc.1
0xf7dec  ldarg.0
0xf7ded  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xf7df2  ldarg.0
0xf7df3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7df8  ldc.i4.1
0xf7df9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xf7dfe  ldarg.0
0xf7dff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e04  ldc.i4.0
0xf7e05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0xf7e0a  ldarg.0
0xf7e0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e10  ldc.i4.0
0xf7e11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf7e16  ldarg.0
0xf7e17  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e1c  ldstr    aDatafieldcolle// "DataFieldCollectionAvailableFields"
0xf7e21  call     string System.Design.SR::GetString(string name)
0xf7e26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf7e2b  ldarg.0
0xf7e2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e31  ldc.i4   0x87
0xf7e36  ldc.i4.s 0xF
0xf7e38  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf7e3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0xf7e42  ldarg.0
0xf7e43  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e48  ldc.i4   0x87
0xf7e4d  ldc.i4.s 0x1E
0xf7e4f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf7e54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MaximumSize(valuetype [System.Drawing]System.Drawing.Size)
0xf7e59  ldarg.0
0xf7e5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::fieldLabel
0xf7e5f  ldc.i4.0
0xf7e60  ldc.i4.0
0xf7e61  ldc.i4   0x87
0xf7e66  ldc.i4.s 0xF
0xf7e68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf7e6d  ldarg.0
0xf7e6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7e73  ldc.i4.1
0xf7e74  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xf7e79  ldarg.0
0xf7e7a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7e7f  ldc.i4.0
0xf7e80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0xf7e85  ldarg.0
0xf7e86  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7e8b  ldstr    aDatafieldcolle_0// "DataFieldCollectionSelectedFields"
0xf7e90  call     string System.Design.SR::GetString(string name)
0xf7e95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf7e9a  ldarg.0
0xf7e9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7ea0  ldc.i4   0x87
0xf7ea5  ldc.i4.s 0xF
0xf7ea7  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf7eac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0xf7eb1  ldarg.0
0xf7eb2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7eb7  ldc.i4   0x87
0xf7ebc  ldc.i4.s 0x1E
0xf7ebe  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf7ec3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MaximumSize(valuetype [System.Drawing]System.Drawing.Size)
0xf7ec8  ldarg.0
0xf7ec9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label DataFieldCollectionForm::selectedFieldsLabel
0xf7ece  ldc.i4   0xAD
0xf7ed3  ldc.i4.0
0xf7ed4  ldc.i4   0x87
0xf7ed9  ldc.i4.s 0xF
0xf7edb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf7ee0  ldarg.0
0xf7ee1  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7ee6  ldc.i4.1
0xf7ee7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf7eec  ldarg.0
0xf7eed  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7ef2  ldc.i4.0
0xf7ef3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AllowDrop(bool)
0xf7ef8  ldarg.0
0xf7ef9  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7efe  ldarg.0
0xf7eff  ldftn    instance void DataFieldCollectionForm::OnFieldsSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0xf7f05  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf7f0a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xf7f0f  ldarg.0
0xf7f10  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7f15  ldarg.0
0xf7f16  ldftn    instance void DataFieldCollectionForm::OnDoubleClickField(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xf7f1c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xf7f21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseDoubleClick(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xf7f26  ldarg.0
0xf7f27  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7f2c  ldarg.0
0xf7f2d  ldftn    instance void DataFieldCollectionForm::OnKeyPressField(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0xf7f33  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0xf7f38  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0xf7f3d  ldarg.0
0xf7f3e  ldfld    class ListBoxWithEnter DataFieldCollectionForm::fieldsList
0xf7f43  ldc.i4.0
0xf7f44  ldc.i4.0
0xf7f45  ldc.i4   0x87
0xf7f4a  ldc.i4   0x82
0xf7f4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf7f54  ldarg.0
0xf7f55  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7f5a  ldc.i4.3
0xf7f5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf7f60  ldarg.0
0xf7f61  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7f66  ldc.i4.0
0xf7f67  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AllowDrop(bool)
0xf7f6c  ldarg.0
0xf7f6d  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7f72  ldarg.0
0xf7f73  ldftn    instance void DataFieldCollectionForm::OnSelectedFieldsSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0xf7f79  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf7f7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xf7f83  ldarg.0
0xf7f84  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7f89  ldarg.0
0xf7f8a  ldftn    instance void DataFieldCollectionForm::OnDoubleClickSelectedField(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xf7f90  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xf7f95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseDoubleClick(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xf7f9a  ldarg.0
0xf7f9b  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7fa0  ldarg.0
0xf7fa1  ldftn    instance void DataFieldCollectionForm::OnKeyPressSelectedField(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0xf7fa7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0xf7fac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0xf7fb1  ldarg.0
0xf7fb2  ldfld    class ListBoxWithEnter DataFieldCollectionForm::selectedFieldsList
0xf7fb7  ldc.i4.0
0xf7fb8  ldc.i4.0
0xf7fb9  ldc.i4   0x87
0xf7fbe  ldc.i4   0x82
0xf7fc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf7fc8  ldarg.0
0xf7fc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf7fce  ldc.i4.s 0x64
0xf7fd0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf7fd5  ldarg.0
0xf7fd6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf7fdb  ldstr    asc_1307F8// ">"
0xf7fe0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf7fe5  ldarg.0
0xf7fe6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf7feb  ldstr    aDatafieldcolle_1// "DataFieldCollection_MoveRight"
0xf7ff0  call     string System.Design.SR::GetString(string name)
0xf7ff5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf7ffa  ldarg.0
0xf7ffb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf8000  ldstr    aDatafieldcolle_2// "DataFieldCollection_MoveRightDesc"
0xf8005  call     string System.Design.SR::GetString(string name)
0xf800a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf800f  ldarg.0
0xf8010  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf8015  ldarg.0
0xf8016  ldftn    instance void DataFieldCollectionForm::OnMoveRight(object sender, class [mscorlib]System.EventArgs e)
0xf801c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf8021  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xf8026  ldarg.0
0xf8027  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf802c  ldc.i4.0
0xf802d  ldc.i4.s 0x2A
0xf802f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xf8034  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xf8039  ldarg.0
0xf803a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf803f  ldc.i4.s 0x1A
0xf8041  ldc.i4.s 0x17
0xf8043  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf8048  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xf804d  ldarg.0
0xf804e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf8053  ldc.i4.s 0x65
0xf8055  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf805a  ldarg.0
0xf805b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf8060  ldstr    asc_13BC3E// "<"
0xf8065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf806a  ldarg.0
0xf806b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf8070  ldstr    aDatafieldcolle_3// "DataFieldCollection_MoveLeft"
0xf8075  call     string System.Design.SR::GetString(string name)
0xf807a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf807f  ldarg.0
0xf8080  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf8085  ldstr    aDatafieldcolle_4// "DataFieldCollection_MoveLeftDesc"
0xf808a  call     string System.Design.SR::GetString(string name)
0xf808f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf8094  ldarg.0
0xf8095  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf809a  ldarg.0
0xf809b  ldftn    instance void DataFieldCollectionForm::OnMoveLeft(object sender, class [mscorlib]System.EventArgs e)
0xf80a1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf80a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xf80ab  ldarg.0
0xf80ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf80b1  ldc.i4.0
0xf80b2  ldc.i4.s 0x41
0xf80b4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xf80b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xf80be  ldarg.0
0xf80bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf80c4  ldc.i4.s 0x1A
0xf80c6  ldc.i4.s 0x17
0xf80c8  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf80cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xf80d2  ldarg.0
0xf80d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel DataFieldCollectionForm::moveLeftRightPanel
0xf80d8  ldc.i4.2
0xf80d9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf80de  ldarg.0
0xf80df  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel DataFieldCollectionForm::moveLeftRightPanel
0xf80e4  ldc.i4.6
0xf80e5  ldc.i4.0
0xf80e6  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xf80eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xf80f0  ldarg.0
0xf80f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel DataFieldCollectionForm::moveLeftRightPanel
0xf80f6  ldc.i4.s 0x1C
0xf80f8  ldc.i4   0x82
0xf80fd  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf8102  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xf8107  ldarg.0
0xf8108  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel DataFieldCollectionForm::moveLeftRightPanel
0xf810d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf8112  ldarg.0
0xf8113  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveLeft
0xf8118  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xf811d  ldarg.0
0xf811e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel DataFieldCollectionForm::moveLeftRightPanel
0xf8123  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf8128  ldarg.0
0xf8129  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveRight
0xf812e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xf8133  ldarg.0
0xf8134  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf8139  ldc.i4   0xC8
0xf813e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf8143  ldarg.0
0xf8144  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf8149  ldstr    aSortupIco// "SortUp.ico"
0xf814e  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0xf8153  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0xf8158  stloc.2
0xf8159  ldloc.2
0xf815a  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0xf815f  ldarg.0
0xf8160  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf8165  ldloc.2
0xf8166  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0xf816b  ldarg.0
0xf816c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf8171  ldstr    aDatafieldcolle_5// "DataFieldCollection_MoveUp"
0xf8176  call     string System.Design.SR::GetString(string name)
0xf817b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf8180  ldarg.0
0xf8181  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf8186  ldstr    aDatafieldcolle_6// "DataFieldCollection_MoveUpDesc"
0xf818b  call     string System.Design.SR::GetString(string name)
0xf8190  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xf8195  ldarg.0
0xf8196  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf819b  ldarg.0
0xf819c  ldftn    instance void DataFieldCollectionForm::OnMoveUp(object sender, class [mscorlib]System.EventArgs e)
0xf81a2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf81a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xf81ac  ldarg.0
0xf81ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf81b2  ldc.i4.0
0xf81b3  ldc.i4.0
0xf81b4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xf81b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xf81be  ldarg.0
0xf81bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveUp
0xf81c4  ldc.i4.s 0x1A
0xf81c6  ldc.i4.s 0x17
0xf81c8  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xf81cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xf81d2  ldarg.0
0xf81d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveDown
0xf81d8  ldc.i4   0xC9
0xf81dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf81e2  ldarg.0
0xf81e3  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf81e8  ldstr    aSortdownIco// "SortDown.ico"
0xf81ed  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0xf81f2  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0xf81f7  stloc.3
0xf81f8  ldloc.3
0xf81f9  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0xf81fe  ldarg.0
0xf81ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button DataFieldCollectionForm::moveDown
0xf8204  ldloc.3
0xf8205  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
  ... truncated ...
```
