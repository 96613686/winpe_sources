# ControlParameterEditor::.ctor_0

- ea: `0xfd840`
- end: `0xfdb09`
- name: `ControlParameterEditor::.ctor_0`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x36240`

## callees

- `0x51860`
- `0x518a0`
- `0x8ef40`
- `0xfa280`
- `0xfd270`
- `0xfd2b0`
- `0xfd840`

## string_xrefs

- `0xfd9d7`: `SqlDataSourceConfigureFilterForm_ParameterEditor_DefaultValue`
- `0xfd8eb`: `SqlDataSourceConfigureFilterForm_ControlParameterEditor_ControlIDLabel`
- `0xfd92c`: `ControlIDComboBox`

## pseudocode

```c

```

## disassembly

```asm
0xfd840  ldarg.0
0xfd841  ldarg.1
0xfd842  call     instance void ParameterEditor::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0xfd847  ldarg.0
0xfd848  ldarg.2
0xfd849  stfld    class [System.Web]System.Web.UI.Control ControlParameterEditor::_control
0xfd84e  ldarg.0
0xfd84f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xfd854  ldarg.0
0xfd855  ldc.i4   0xDC
0xfd85a  ldc.i4.s 0x2C
0xfd85c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xfd861  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xfd866  ldarg.0
0xfd867  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xfd86c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd871  ldarg.0
0xfd872  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0xfd877  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd87c  ldarg.0
0xfd87d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xfd882  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd887  ldarg.0
0xfd888  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xfd88d  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfd892  ldarg.0
0xfd893  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd898  ldc.i4.s 0xD
0xfd89a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xfd89f  ldarg.0
0xfd8a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd8a5  ldc.i4.0
0xfd8a6  ldc.i4.0
0xfd8a7  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xfd8ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xfd8b1  ldarg.0
0xfd8b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd8b7  ldstr    aControlidlabel// "ControlIDLabel"
0xfd8bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xfd8c1  ldarg.0
0xfd8c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd8c7  ldc.i4   0xDC
0xfd8cc  ldc.i4.s 0x10
0xfd8ce  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xfd8d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xfd8d8  ldarg.0
0xfd8d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd8de  ldc.i4.s 0xA
0xfd8e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xfd8e5  ldarg.0
0xfd8e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfd8eb  ldstr    aSqldatasourcec_55// "SqlDataSourceConfigureFilterForm_Contro"...
0xfd8f0  call     string System.Design.SR::GetString(string name)
0xfd8f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xfd8fa  ldarg.0
0xfd8fb  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd900  ldc.i4.s 0xD
0xfd902  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xfd907  ldarg.0
0xfd908  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd90d  ldc.i4.2
0xfd90e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0xfd913  ldarg.0
0xfd914  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd919  ldc.i4.0
0xfd91a  ldc.i4.s 0x17
0xfd91c  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xfd921  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xfd926  ldarg.0
0xfd927  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd92c  ldstr    aControlidcombo// "ControlIDComboBox"
0xfd931  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xfd936  ldarg.0
0xfd937  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd93c  ldc.i4   0xDC
0xfd941  ldc.i4.s 0x14
0xfd943  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xfd948  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xfd94d  ldarg.0
0xfd94e  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd953  ldc.i4.1
0xfd954  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_Sorted(bool)
0xfd959  ldarg.0
0xfd95a  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd95f  ldc.i4.s 0x14
0xfd961  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xfd966  ldarg.0
0xfd967  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfd96c  ldarg.0
0xfd96d  ldftn    instance void ControlParameterEditor::OnControlIDComboBoxSelectedIndexChanged(object s, class [mscorlib]System.EventArgs e)
0xfd973  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xfd978  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xfd97d  ldarg.0
0xfd97e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd983  ldc.i4.s 0xD
0xfd985  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xfd98a  ldarg.0
0xfd98b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd990  ldc.i4.0
0xfd991  ldc.i4.s 0x30
0xfd993  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xfd998  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xfd99d  ldarg.0
0xfd99e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd9a3  ldstr    aControldefault// "ControlDefaultValueLabel"
0xfd9a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xfd9ad  ldarg.0
0xfd9ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd9b3  ldc.i4   0xDC
0xfd9b8  ldc.i4.s 0x10
0xfd9ba  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xfd9bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xfd9c4  ldarg.0
0xfd9c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd9ca  ldc.i4.s 0x1E
0xfd9cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xfd9d1  ldarg.0
0xfd9d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfd9d7  ldstr    aSqldatasourcec_54// "SqlDataSourceConfigureFilterForm_Parame"...
0xfd9dc  call     string System.Design.SR::GetString(string name)
0xfd9e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xfd9e6  ldarg.0
0xfd9e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfd9ec  ldc.i4.s 0xD
0xfd9ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xfd9f3  ldarg.0
0xfd9f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfd9f9  ldc.i4.0
0xfd9fa  ldc.i4.s 0x44
0xfd9fc  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xfda01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xfda06  ldarg.0
0xfda07  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfda0c  ldstr    aControldefault_0// "ControlDefaultValueTextBox"
0xfda11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xfda16  ldarg.0
0xfda17  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfda1c  ldc.i4   0xDC
0xfda21  ldc.i4.s 0x14
0xfda23  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xfda28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xfda2d  ldarg.0
0xfda2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfda33  ldc.i4.s 0x28
0xfda35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xfda3a  ldarg.0
0xfda3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfda40  ldarg.0
0xfda41  ldftn    instance void ControlParameterEditor::OnDefaultValueTextBoxTextChanged(object s, class [mscorlib]System.EventArgs e)
0xfda47  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xfda4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0xfda51  ldarg.0
0xfda52  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xfda57  ldarg.0
0xfda58  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_controlIDLabel
0xfda5d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xfda62  ldarg.0
0xfda63  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xfda68  ldarg.0
0xfda69  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfda6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xfda73  ldarg.0
0xfda74  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xfda79  ldarg.0
0xfda7a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ControlParameterEditor::_defaultValueLabel
0xfda7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xfda84  ldarg.0
0xfda85  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xfda8a  ldarg.0
0xfda8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ControlParameterEditor::_defaultValueTextBox
0xfda90  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xfda95  ldarg.0
0xfda96  call     instance class [mscorlib]System.IServiceProvider ParameterEditor::get_ServiceProvider()
0xfda9b  brfalse.s loc_FDAFB
0xfda9d  ldarg.0
0xfda9e  call     instance class [mscorlib]System.IServiceProvider ParameterEditor::get_ServiceProvider()
0xfdaa3  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xfdaa8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfdaad  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xfdab2  castclass [System]System.ComponentModel.Design.IDesignerHost
0xfdab7  stloc.0
0xfdab8  ldloc.0
0xfdab9  brfalse.s loc_FDAFB
0xfdabb  ldloc.0
0xfdabc  ldarg.0
0xfdabd  ldfld    class [System.Web]System.Web.UI.Control ControlParameterEditor::_control
0xfdac2  call     class ControlItem[] ControlItem::GetControlItems(class [System]System.ComponentModel.Design.IDesignerHost host, class [System.Web]System.Web.UI.Control control)
0xfdac7  stloc.1
0xfdac8  ldloc.1
0xfdac9  stloc.2
0xfdaca  ldc.i4.0
0xfdacb  stloc.3
0xfdacc  br.s     loc_FDAEA
0xfdace  ldloc.2
0xfdacf  ldloc.3
0xfdad0  ldelem.ref
0xfdad1  stloc.s  4
0xfdad3  ldarg.0
0xfdad4  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfdad9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0xfdade  ldloc.s  4
0xfdae0  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0xfdae5  pop
0xfdae6  ldloc.3
0xfdae7  ldc.i4.1
0xfdae8  add
0xfdae9  stloc.3
0xfdaea  ldloc.3
0xfdaeb  ldloc.2
0xfdaec  ldlen
0xfdaed  conv.i4
0xfdaee  blt.s    loc_FDACE
0xfdaf0  ldarg.0
0xfdaf1  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox ControlParameterEditor::_controlIDComboBox
0xfdaf6  callvirt instance void System.Web.UI.Design.Util.AutoSizeComboBox::InvalidateDropDownWidth()
0xfdafb  ldarg.0
0xfdafc  ldc.i4.5
0xfdafd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xfdb02  ldarg.0
0xfdb03  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout()
0xfdb08  ret
```
