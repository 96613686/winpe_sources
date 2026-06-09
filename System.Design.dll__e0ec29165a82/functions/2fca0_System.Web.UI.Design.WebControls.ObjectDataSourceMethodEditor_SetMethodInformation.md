# System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::SetMethodInformation

- ea: `0x2fca0`
- end: `0x2fe57`
- name: `System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::SetMethodInformation`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x2d850`

## callees

- `0x2ef10`
- `0x2f7a0`
- `0x2fca0`
- `0x51860`
- `0x8ef40`
- `0xfa1c0`

## string_xrefs

- `0x2fcd1`: `ObjectDataSourceMethodEditor_DeleteHelpLabel`
- `0x2fd16`: `ObjectDataSourceMethodEditor_UpdateHelpLabel`

## pseudocode

```c

```

## disassembly

```asm
0x2fca0  ldarg.0
0x2fca1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_signatureTextBox
0x2fca6  ldsfld   string [mscorlib]System.String::Empty
0x2fcab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2fcb0  ldarg.s  4
0x2fcb2  ldc.i4.1
0x2fcb3  sub
0x2fcb4  switch   loc_2FCF9, loc_2FD10, loc_2FCE2, loc_2FCCB
0x2fcc9  br.s     loc_2FD25
0x2fccb  ldarg.0
0x2fccc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_helpLabel
0x2fcd1  ldstr    aObjectdatasour_17// "ObjectDataSourceMethodEditor_DeleteHelp"...
0x2fcd6  call     string System.Design.SR::GetString(string name)
0x2fcdb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2fce0  br.s     loc_2FD25
0x2fce2  ldarg.0
0x2fce3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_helpLabel
0x2fce8  ldstr    aObjectdatasour_18// "ObjectDataSourceMethodEditor_InsertHelp"...
0x2fced  call     string System.Design.SR::GetString(string name)
0x2fcf2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2fcf7  br.s     loc_2FD25
0x2fcf9  ldarg.0
0x2fcfa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_helpLabel
0x2fcff  ldstr    aObjectdatasour_19// "ObjectDataSourceMethodEditor_SelectHelp"...
0x2fd04  call     string System.Design.SR::GetString(string name)
0x2fd09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2fd0e  br.s     loc_2FD25
0x2fd10  ldarg.0
0x2fd11  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_helpLabel
0x2fd16  ldstr    aObjectdatasour_20// "ObjectDataSourceMethodEditor_UpdateHelp"...
0x2fd1b  call     string System.Design.SR::GetString(string name)
0x2fd20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2fd25  ldarg.0
0x2fd26  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fd2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::BeginUpdate()
0x2fd30  ldarg.0
0x2fd31  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fd36  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x2fd3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Clear()
0x2fd40  ldnull
0x2fd41  stloc.0
0x2fd42  ldc.i4.0
0x2fd43  stloc.1
0x2fd44  ldarg.1
0x2fd45  stloc.2
0x2fd46  ldc.i4.0
0x2fd47  stloc.3
0x2fd48  br       loc_2FE0C
0x2fd4d  ldloc.2
0x2fd4e  ldloc.3
0x2fd4f  ldelem.ref
0x2fd50  stloc.s  4
0x2fd52  ldarg.0
0x2fd53  ldloc.s  4
0x2fd55  ldarg.s  4
0x2fd57  call     instance bool System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::FilterMethod(class [mscorlib]System.Reflection.MethodInfo methodInfo, valuetype [System]System.ComponentModel.DataObjectMethodType methodType)
0x2fd5c  brfalse  loc_2FE08
0x2fd61  ldc.i4.0
0x2fd62  stloc.s  5
0x2fd64  ldloc.s  4
0x2fd66  ldtoken  [System]System.ComponentModel.DataObjectMethodAttribute
0x2fd6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fd70  ldc.i4.1
0x2fd71  call     class [mscorlib]System.Attribute [mscorlib]System.Attribute::GetCustomAttribute(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Type, bool)
0x2fd76  isinst   [System]System.ComponentModel.DataObjectMethodAttribute
0x2fd7b  stloc.s  6
0x2fd7d  ldloc.s  6
0x2fd7f  brfalse.s loc_2FDA6
0x2fd81  ldloc.s  6
0x2fd83  callvirt instance valuetype [System]System.ComponentModel.DataObjectMethodType [System]System.ComponentModel.DataObjectMethodAttribute::get_MethodType()
0x2fd88  ldarg.s  4
0x2fd8a  bne.un.s loc_2FDA6
0x2fd8c  ldloc.1
0x2fd8d  brtrue.s loc_2FD9F
0x2fd8f  ldarg.0
0x2fd90  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fd95  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x2fd9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Clear()
0x2fd9f  ldc.i4.1
0x2fda0  stloc.1
0x2fda1  ldc.i4.1
0x2fda2  stloc.s  5
0x2fda4  br.s     loc_2FDAC
0x2fda6  ldloc.1
0x2fda7  brtrue.s loc_2FDAC
0x2fda9  ldc.i4.1
0x2fdaa  stloc.s  5
0x2fdac  ldloc.s  4
0x2fdae  ldarg.2
0x2fdaf  ldarg.3
0x2fdb0  ldarg.s  5
0x2fdb2  call     bool System.Web.UI.Design.WebControls.ObjectDataSourceDesigner::IsMatchingMethod(class [mscorlib]System.Reflection.MethodInfo method, string methodName, class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Type dataObjectType)
0x2fdb7  stloc.s  7
0x2fdb9  ldloc.s  5
0x2fdbb  ldloc.s  7
0x2fdbd  or
0x2fdbe  brfalse.s loc_2FE08
0x2fdc0  ldloc.s  4
0x2fdc2  newobj   instance void MethodItem::.ctor(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x2fdc7  stloc.s  8
0x2fdc9  ldarg.0
0x2fdca  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fdcf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x2fdd4  ldloc.s  8
0x2fdd6  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Add(object)
0x2fddb  pop
0x2fddc  ldloc.s  7
0x2fdde  brfalse.s loc_2FDE5
0x2fde0  ldloc.s  8
0x2fde2  stloc.0
0x2fde3  br.s     loc_2FE08
0x2fde5  ldloc.s  6
0x2fde7  brfalse.s loc_2FE08
0x2fde9  ldloc.s  6
0x2fdeb  callvirt instance valuetype [System]System.ComponentModel.DataObjectMethodType [System]System.ComponentModel.DataObjectMethodAttribute::get_MethodType()
0x2fdf0  ldarg.s  4
0x2fdf2  bne.un.s loc_2FE08
0x2fdf4  ldloc.s  6
0x2fdf6  callvirt instance bool [System]System.ComponentModel.DataObjectMethodAttribute::get_IsDefault()
0x2fdfb  brfalse.s loc_2FE08
0x2fdfd  ldarg.2
0x2fdfe  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2fe03  brtrue.s loc_2FE08
0x2fe05  ldloc.s  8
0x2fe07  stloc.0
0x2fe08  ldloc.3
0x2fe09  ldc.i4.1
0x2fe0a  add
0x2fe0b  stloc.3
0x2fe0c  ldloc.3
0x2fe0d  ldloc.2
0x2fe0e  ldlen
0x2fe0f  conv.i4
0x2fe10  blt      loc_2FD4D
0x2fe15  ldarg.s  4
0x2fe17  ldc.i4.1
0x2fe18  beq.s    loc_2FE31
0x2fe1a  ldarg.0
0x2fe1b  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fe20  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x2fe25  ldc.i4.0
0x2fe26  ldnull
0x2fe27  newobj   instance void MethodItem::.ctor(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x2fe2c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::Insert(int32, object)
0x2fe31  ldarg.0
0x2fe32  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fe37  callvirt instance void System.Web.UI.Design.Util.AutoSizeComboBox::InvalidateDropDownWidth()
0x2fe3c  ldarg.0
0x2fe3d  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fe42  ldloc.0
0x2fe43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_SelectedItem(object)
0x2fe48  leave.s  loc_2FE56
0x2fe4a  ldarg.0
0x2fe4b  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::_methodComboBox
0x2fe50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::EndUpdate()
0x2fe55  endfinally
0x2fe56  ret
```
