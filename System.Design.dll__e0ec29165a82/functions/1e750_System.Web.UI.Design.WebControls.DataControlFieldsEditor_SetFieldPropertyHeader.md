# System.Web.UI.Design.WebControls.DataControlFieldsEditor::SetFieldPropertyHeader

- ea: `0x1e750`
- end: `0x1e8f3`
- name: `System.Web.UI.Design.WebControls.DataControlFieldsEditor::SetFieldPropertyHeader`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1e5a0`

## callees

- `0x1cab0`
- `0x1cac0`
- `0x1e750`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x1e836`: `DCFEditor_Node_HyperLink`
- `0x1e86b`: `DCFEditor_Node_Command`
- `0x1e89d`: `DCFEditor_Node_Template`

## pseudocode

```c

```

## disassembly

```asm
0x1e750  ldstr    aDcfeditorField// "DCFEditor_FieldProps"
0x1e755  call     string System.Design.SR::GetString(string name)
0x1e75a  stloc.0
0x1e75b  ldarg.0
0x1e75c  ldfld    class FieldItem System.Web.UI.Design.WebControls.DataControlFieldsEditor::_currentFieldItem
0x1e761  brfalse  loc_1E8E6
0x1e766  ldarg.0
0x1e767  call     instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::EnterLoadingMode()
0x1e76c  ldarg.0
0x1e76d  ldfld    class FieldItem System.Web.UI.Design.WebControls.DataControlFieldsEditor::_currentFieldItem
0x1e772  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e777  stloc.1
0x1e778  ldloc.1
0x1e779  ldtoken  CheckBoxFieldItem
0x1e77e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e783  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e788  brfalse.s loc_1E7AD
0x1e78a  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e78f  ldc.i4.1
0x1e790  newarr   [mscorlib]System.Object
0x1e795  dup
0x1e796  ldc.i4.0
0x1e797  ldstr    aDcfeditorNodeC// "DCFEditor_Node_CheckBox"
0x1e79c  call     string System.Design.SR::GetString(string name)
0x1e7a1  stelem.ref
0x1e7a2  call     string System.Design.SR::GetString(string name, object[] args)
0x1e7a7  stloc.0
0x1e7a8  br       loc_1E8E0
0x1e7ad  ldloc.1
0x1e7ae  ldtoken  BoundFieldItem
0x1e7b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e7b8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e7bd  brfalse.s loc_1E7E2
0x1e7bf  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e7c4  ldc.i4.1
0x1e7c5  newarr   [mscorlib]System.Object
0x1e7ca  dup
0x1e7cb  ldc.i4.0
0x1e7cc  ldstr    aDcfeditorNodeB// "DCFEditor_Node_Bound"
0x1e7d1  call     string System.Design.SR::GetString(string name)
0x1e7d6  stelem.ref
0x1e7d7  call     string System.Design.SR::GetString(string name, object[] args)
0x1e7dc  stloc.0
0x1e7dd  br       loc_1E8E0
0x1e7e2  ldloc.1
0x1e7e3  ldtoken  ButtonFieldItem
0x1e7e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e7ed  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e7f2  brfalse.s loc_1E817
0x1e7f4  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e7f9  ldc.i4.1
0x1e7fa  newarr   [mscorlib]System.Object
0x1e7ff  dup
0x1e800  ldc.i4.0
0x1e801  ldstr    aDcfeditorNodeB_0// "DCFEditor_Node_Button"
0x1e806  call     string System.Design.SR::GetString(string name)
0x1e80b  stelem.ref
0x1e80c  call     string System.Design.SR::GetString(string name, object[] args)
0x1e811  stloc.0
0x1e812  br       loc_1E8E0
0x1e817  ldloc.1
0x1e818  ldtoken  HyperLinkFieldItem
0x1e81d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e822  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e827  brfalse.s loc_1E84C
0x1e829  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e82e  ldc.i4.1
0x1e82f  newarr   [mscorlib]System.Object
0x1e834  dup
0x1e835  ldc.i4.0
0x1e836  ldstr    aDcfeditorNodeH// "DCFEditor_Node_HyperLink"
0x1e83b  call     string System.Design.SR::GetString(string name)
0x1e840  stelem.ref
0x1e841  call     string System.Design.SR::GetString(string name, object[] args)
0x1e846  stloc.0
0x1e847  br       loc_1E8E0
0x1e84c  ldloc.1
0x1e84d  ldtoken  CommandFieldItem
0x1e852  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e857  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e85c  brfalse.s loc_1E87E
0x1e85e  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e863  ldc.i4.1
0x1e864  newarr   [mscorlib]System.Object
0x1e869  dup
0x1e86a  ldc.i4.0
0x1e86b  ldstr    aDcfeditorNodeC_0// "DCFEditor_Node_Command"
0x1e870  call     string System.Design.SR::GetString(string name)
0x1e875  stelem.ref
0x1e876  call     string System.Design.SR::GetString(string name, object[] args)
0x1e87b  stloc.0
0x1e87c  br.s     loc_1E8E0
0x1e87e  ldloc.1
0x1e87f  ldtoken  TemplateFieldItem
0x1e884  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e889  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e88e  brfalse.s loc_1E8B0
0x1e890  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e895  ldc.i4.1
0x1e896  newarr   [mscorlib]System.Object
0x1e89b  dup
0x1e89c  ldc.i4.0
0x1e89d  ldstr    aDcfeditorNodeT// "DCFEditor_Node_Template"
0x1e8a2  call     string System.Design.SR::GetString(string name)
0x1e8a7  stelem.ref
0x1e8a8  call     string System.Design.SR::GetString(string name, object[] args)
0x1e8ad  stloc.0
0x1e8ae  br.s     loc_1E8E0
0x1e8b0  ldloc.1
0x1e8b1  ldtoken  ImageFieldItem
0x1e8b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e8bb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e8c0  brfalse.s loc_1E8E0
0x1e8c2  ldstr    aDcfeditorField_0// "DCFEditor_FieldPropsFormat"
0x1e8c7  ldc.i4.1
0x1e8c8  newarr   [mscorlib]System.Object
0x1e8cd  dup
0x1e8ce  ldc.i4.0
0x1e8cf  ldstr    aDcfeditorNodeI_0// "DCFEditor_Node_Image"
0x1e8d4  call     string System.Design.SR::GetString(string name)
0x1e8d9  stelem.ref
0x1e8da  call     string System.Design.SR::GetString(string name, object[] args)
0x1e8df  stloc.0
0x1e8e0  ldarg.0
0x1e8e1  call     instance void System.Web.UI.Design.WebControls.DataControlFieldsEditor::ExitLoadingMode()
0x1e8e6  ldarg.0
0x1e8e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.DataControlFieldsEditor::_selFieldLabel
0x1e8ec  ldloc.0
0x1e8ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1e8f2  ret
```
