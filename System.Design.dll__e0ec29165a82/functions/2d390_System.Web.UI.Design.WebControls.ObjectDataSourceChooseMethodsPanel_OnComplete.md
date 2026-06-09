# System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::OnComplete

- ea: `0x2d390`
- end: `0x2d678`
- name: `System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::OnComplete`
- size: `744`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe310`
- `0xe350`
- `0x119b0`
- `0x2ce60`
- `0x2ce70`
- `0x2ce80`
- `0x2ce90`
- `0x2cea0`
- `0x2ceb0`
- `0x2cec0`
- `0x2d390`
- `0x2f110`
- `0x2f400`

## string_xrefs

- `0x2d3cc`: `DeleteMethod`
- `0x2d4ec`: `UpdateMethod`

## pseudocode

```c

```

## disassembly

```asm
0x2d390  ldarg.0
0x2d391  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_DeleteMethodInfo()
0x2d396  stloc.2
0x2d397  ldloc.2
0x2d398  ldnull
0x2d399  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d39e  brtrue.s loc_2D3A8
0x2d3a0  ldloc.2
0x2d3a1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2d3a6  br.s     loc_2D3AD
0x2d3a8  ldsfld   string [mscorlib]System.String::Empty
0x2d3ad  stloc.1
0x2d3ae  ldarg.0
0x2d3af  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d3b4  callvirt instance string [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_DeleteMethod()
0x2d3b9  ldloc.1
0x2d3ba  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d3bf  brfalse.s loc_2D3F0
0x2d3c1  ldarg.0
0x2d3c2  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d3c7  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x2d3cc  ldstr    aDeletemethod// "DeleteMethod"
0x2d3d1  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x2d3d6  stloc.0
0x2d3d7  ldloc.0
0x2d3d8  ldarg.0
0x2d3d9  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d3de  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x2d3e3  ldloc.0
0x2d3e4  ldarg.0
0x2d3e5  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d3ea  ldloc.1
0x2d3eb  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x2d3f0  ldarg.0
0x2d3f1  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_InsertMethodInfo()
0x2d3f6  stloc.2
0x2d3f7  ldloc.2
0x2d3f8  ldnull
0x2d3f9  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d3fe  brtrue.s loc_2D408
0x2d400  ldloc.2
0x2d401  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2d406  br.s     loc_2D40D
0x2d408  ldsfld   string [mscorlib]System.String::Empty
0x2d40d  stloc.1
0x2d40e  ldarg.0
0x2d40f  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d414  callvirt instance string [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_InsertMethod()
0x2d419  ldloc.1
0x2d41a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d41f  brfalse.s loc_2D450
0x2d421  ldarg.0
0x2d422  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d427  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x2d42c  ldstr    aInsertmethod// "InsertMethod"
0x2d431  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x2d436  stloc.0
0x2d437  ldloc.0
0x2d438  ldarg.0
0x2d439  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d43e  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x2d443  ldloc.0
0x2d444  ldarg.0
0x2d445  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d44a  ldloc.1
0x2d44b  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x2d450  ldarg.0
0x2d451  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_SelectMethodInfo()
0x2d456  stloc.2
0x2d457  ldloc.2
0x2d458  ldnull
0x2d459  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d45e  brtrue.s loc_2D468
0x2d460  ldloc.2
0x2d461  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2d466  br.s     loc_2D46D
0x2d468  ldsfld   string [mscorlib]System.String::Empty
0x2d46d  stloc.1
0x2d46e  ldarg.0
0x2d46f  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d474  callvirt instance string [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_SelectMethod()
0x2d479  ldloc.1
0x2d47a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d47f  brfalse.s loc_2D4B0
0x2d481  ldarg.0
0x2d482  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d487  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x2d48c  ldstr    aSelectmethod// "SelectMethod"
0x2d491  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x2d496  stloc.0
0x2d497  ldloc.0
0x2d498  ldarg.0
0x2d499  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d49e  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x2d4a3  ldloc.0
0x2d4a4  ldarg.0
0x2d4a5  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d4aa  ldloc.1
0x2d4ab  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x2d4b0  ldarg.0
0x2d4b1  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_UpdateMethodInfo()
0x2d4b6  stloc.2
0x2d4b7  ldloc.2
0x2d4b8  ldnull
0x2d4b9  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d4be  brtrue.s loc_2D4C8
0x2d4c0  ldloc.2
0x2d4c1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2d4c6  br.s     loc_2D4CD
0x2d4c8  ldsfld   string [mscorlib]System.String::Empty
0x2d4cd  stloc.1
0x2d4ce  ldarg.0
0x2d4cf  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d4d4  callvirt instance string [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_UpdateMethod()
0x2d4d9  ldloc.1
0x2d4da  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d4df  brfalse.s loc_2D510
0x2d4e1  ldarg.0
0x2d4e2  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d4e7  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x2d4ec  ldstr    aUpdatemethod// "UpdateMethod"
0x2d4f1  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x2d4f6  stloc.0
0x2d4f7  ldloc.0
0x2d4f8  ldarg.0
0x2d4f9  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d4fe  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x2d503  ldloc.0
0x2d504  ldarg.0
0x2d505  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d50a  ldloc.1
0x2d50b  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x2d510  ldarg.0
0x2d511  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d516  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_SelectParameters()
0x2d51b  callvirt instance void [System.Web]System.Web.UI.StateManagedCollection::Clear()
0x2d520  ldarg.0
0x2d521  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_SelectMethodInfo()
0x2d526  stloc.2
0x2d527  ldnull
0x2d528  stloc.3
0x2d529  ldloc.2
0x2d52a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x2d52f  newobj   instance void System.Web.UI.Design.TypeSchema::.ctor(class [mscorlib]System.Type type)
0x2d534  stloc.s  5
0x2d536  ldloc.s  5
0x2d538  brfalse.s loc_2D556
0x2d53a  ldloc.s  5
0x2d53c  callvirt instance class System.Web.UI.Design.IDataSourceViewSchema[] System.Web.UI.Design.IDataSourceSchema::GetViews()
0x2d541  stloc.s  6
0x2d543  ldloc.s  6
0x2d545  brfalse.s loc_2D556
0x2d547  ldloc.s  6
0x2d549  ldlen
0x2d54a  brfalse.s loc_2D556
0x2d54c  ldloc.s  6
0x2d54e  ldc.i4.0
0x2d54f  ldelem.ref
0x2d550  callvirt instance class System.Web.UI.Design.IDataSourceFieldSchema[] System.Web.UI.Design.IDataSourceViewSchema::GetFields()
0x2d555  stloc.3
0x2d556  leave.s  loc_2D55C
0x2d558  stloc.s  7
0x2d55a  leave.s  loc_2D55C
0x2d55c  ldarg.0
0x2d55d  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d562  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_DeleteParameters()
0x2d567  ldarg.0
0x2d568  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_DeleteMethodInfo()
0x2d56d  ldarg.0
0x2d56e  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_DeleteMethodDataObjectType()
0x2d573  call     void System.Web.UI.Design.WebControls.ObjectDataSourceDesigner::MergeParameters(class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Reflection.MethodInfo methodInfo, class [mscorlib]System.Type dataObjectType)
0x2d578  ldarg.0
0x2d579  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d57e  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_InsertParameters()
0x2d583  ldarg.0
0x2d584  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_InsertMethodInfo()
0x2d589  ldarg.0
0x2d58a  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_InsertMethodDataObjectType()
0x2d58f  call     void System.Web.UI.Design.WebControls.ObjectDataSourceDesigner::MergeParameters(class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Reflection.MethodInfo methodInfo, class [mscorlib]System.Type dataObjectType)
0x2d594  ldarg.0
0x2d595  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d59a  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_UpdateParameters()
0x2d59f  ldarg.0
0x2d5a0  call     instance class [mscorlib]System.Reflection.MethodInfo System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_UpdateMethodInfo()
0x2d5a5  ldarg.0
0x2d5a6  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_UpdateMethodDataObjectType()
0x2d5ab  call     void System.Web.UI.Design.WebControls.ObjectDataSourceDesigner::MergeParameters(class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Reflection.MethodInfo methodInfo, class [mscorlib]System.Type dataObjectType)
0x2d5b0  ldsfld   string [mscorlib]System.String::Empty
0x2d5b5  stloc.s  4
0x2d5b7  ldarg.0
0x2d5b8  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_DeleteMethodDataObjectType()
0x2d5bd  ldnull
0x2d5be  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d5c3  brfalse.s loc_2D5D4
0x2d5c5  ldarg.0
0x2d5c6  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_DeleteMethodDataObjectType()
0x2d5cb  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d5d0  stloc.s  4
0x2d5d2  br.s     loc_2D60C
0x2d5d4  ldarg.0
0x2d5d5  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_InsertMethodDataObjectType()
0x2d5da  ldnull
0x2d5db  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d5e0  brfalse.s loc_2D5F1
0x2d5e2  ldarg.0
0x2d5e3  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_InsertMethodDataObjectType()
0x2d5e8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d5ed  stloc.s  4
0x2d5ef  br.s     loc_2D60C
0x2d5f1  ldarg.0
0x2d5f2  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_UpdateMethodDataObjectType()
0x2d5f7  ldnull
0x2d5f8  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d5fd  brfalse.s loc_2D60C
0x2d5ff  ldarg.0
0x2d600  call     instance class [mscorlib]System.Type System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::get_UpdateMethodDataObjectType()
0x2d605  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d60a  stloc.s  4
0x2d60c  ldarg.0
0x2d60d  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d612  callvirt instance string [System.Web]System.Web.UI.WebControls.ObjectDataSource::get_DataObjectTypeName()
0x2d617  ldloc.s  4
0x2d619  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d61e  brfalse.s loc_2D650
0x2d620  ldarg.0
0x2d621  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d626  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x2d62b  ldstr    aDataobjecttype// "DataObjectTypeName"
0x2d630  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x2d635  stloc.0
0x2d636  ldloc.0
0x2d637  ldarg.0
0x2d638  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d63d  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x2d642  ldloc.0
0x2d643  ldarg.0
0x2d644  ldfld    class [System.Web]System.Web.UI.WebControls.ObjectDataSource System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSource
0x2d649  ldloc.s  4
0x2d64b  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x2d650  ldloc.2
0x2d651  ldnull
0x2d652  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d657  brfalse.s loc_2D677
0x2d659  ldarg.0
0x2d65a  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceDesigner System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_objectDataSourceDesigner
0x2d65f  ldloc.2
0x2d660  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_ReflectedType()
0x2d665  ldloc.2
0x2d666  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2d66b  ldloc.2
0x2d66c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x2d671  ldc.i4.1
0x2d672  callvirt instance void System.Web.UI.Design.WebControls.ObjectDataSourceDesigner::RefreshSchema(class [mscorlib]System.Type objectType, string methodName, class [mscorlib]System.Type schemaType, bool preferSilent)
0x2d677  ret
```
