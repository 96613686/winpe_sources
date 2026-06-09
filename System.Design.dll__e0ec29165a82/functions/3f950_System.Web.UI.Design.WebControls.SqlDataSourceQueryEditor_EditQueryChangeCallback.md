# System.Web.UI.Design.WebControls.SqlDataSourceQueryEditor::EditQueryChangeCallback

- ea: `0x3f950`
- end: `0x3fae0`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceQueryEditor::EditQueryChangeCallback`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3dee0`
- `0x3f950`
- `0x3fb50`
- `0x3fc60`
- `0x52b80`

## string_xrefs

- `0x3faa1`: `SelectCommand`
- `0x3fa79`: `DeleteCommand`
- `0x3fa8d`: `InsertCommand`
- `0x3fab5`: `UpdateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x3f950  ldarg.1
0x3f951  castclass [System.Web]System.Web.UI.Pair
0x3f956  ldfld    object [System.Web]System.Web.UI.Pair::First
0x3f95b  castclass [System.Web]System.Web.UI.WebControls.SqlDataSource
0x3f960  stloc.0
0x3f961  ldarg.1
0x3f962  castclass [System.Web]System.Web.UI.Pair
0x3f967  ldfld    object [System.Web]System.Web.UI.Pair::Second
0x3f96c  unbox.any [System.Web]System.Web.UI.DataSourceOperation
0x3f971  stloc.1
0x3f972  ldloc.0
0x3f973  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x3f978  stloc.2
0x3f979  ldloc.2
0x3f97a  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x3f97f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f984  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3f989  castclass [System]System.ComponentModel.Design.IDesignerHost
0x3f98e  stloc.3
0x3f98f  ldloc.3
0x3f990  ldloc.0
0x3f991  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x3f996  castclass System.Web.UI.Design.WebControls.SqlDataSourceDesigner
0x3f99b  stloc.s  4
0x3f99d  ldnull
0x3f99e  stloc.s  5
0x3f9a0  ldsfld   string [mscorlib]System.String::Empty
0x3f9a5  stloc.s  6
0x3f9a7  ldc.i4.0
0x3f9a8  stloc.s  7
0x3f9aa  ldloc.1
0x3f9ab  switch   loc_3F9C2, loc_3F9DC, loc_3F9F6, loc_3FA10
0x3f9c0  br.s     loc_3FA28
0x3f9c2  ldloc.0
0x3f9c3  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteParameters()
0x3f9c8  stloc.s  5
0x3f9ca  ldloc.0
0x3f9cb  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteCommand()
0x3f9d0  stloc.s  6
0x3f9d2  ldloc.0
0x3f9d3  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteCommandType()
0x3f9d8  stloc.s  7
0x3f9da  br.s     loc_3FA28
0x3f9dc  ldloc.0
0x3f9dd  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertParameters()
0x3f9e2  stloc.s  5
0x3f9e4  ldloc.0
0x3f9e5  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertCommand()
0x3f9ea  stloc.s  6
0x3f9ec  ldloc.0
0x3f9ed  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertCommandType()
0x3f9f2  stloc.s  7
0x3f9f4  br.s     loc_3FA28
0x3f9f6  ldloc.0
0x3f9f7  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectParameters()
0x3f9fc  stloc.s  5
0x3f9fe  ldloc.0
0x3f9ff  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectCommand()
0x3fa04  stloc.s  6
0x3fa06  ldloc.0
0x3fa07  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectCommandType()
0x3fa0c  stloc.s  7
0x3fa0e  br.s     loc_3FA28
0x3fa10  ldloc.0
0x3fa11  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateParameters()
0x3fa16  stloc.s  5
0x3fa18  ldloc.0
0x3fa19  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateCommand()
0x3fa1e  stloc.s  6
0x3fa20  ldloc.0
0x3fa21  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateCommandType()
0x3fa26  stloc.s  7
0x3fa28  ldloc.2
0x3fa29  ldloc.s  4
0x3fa2b  ldloc.0
0x3fa2c  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_ProviderName()
0x3fa31  ldloc.s  4
0x3fa33  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceDesigner::get_ConnectionString()
0x3fa38  ldloc.1
0x3fa39  ldloc.s  7
0x3fa3b  ldloc.s  6
0x3fa3d  ldloc.s  5
0x3fa3f  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceQueryEditorForm::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, class System.Web.UI.Design.WebControls.SqlDataSourceDesigner sqlDataSourceDesigner, string providerName, string connectionString, valuetype [System.Web]System.Web.UI.DataSourceOperation operation, valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType commandType, string command, class [mscorlib]System.Collections.IList originalParameters)
0x3fa44  stloc.s  8
0x3fa46  ldloc.2
0x3fa47  ldloc.s  8
0x3fa49  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult System.Web.UI.Design.Util.UIServiceHelper::ShowDialog(class [mscorlib]System.IServiceProvider serviceProvider, class [System.Windows.Forms]System.Windows.Forms.Form form)
0x3fa4e  stloc.s  9
0x3fa50  ldloc.s  9
0x3fa52  ldc.i4.1
0x3fa53  bne.un   loc_3FADE
0x3fa58  ldnull
0x3fa59  stloc.s  0xA
0x3fa5b  ldloc.1
0x3fa5c  switch   loc_3FA73, loc_3FA87, loc_3FA9B, loc_3FAAF
0x3fa71  br.s     loc_3FAC1
0x3fa73  ldloc.0
0x3fa74  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x3fa79  ldstr    aDeletecommand// "DeleteCommand"
0x3fa7e  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x3fa83  stloc.s  0xA
0x3fa85  br.s     loc_3FAC1
0x3fa87  ldloc.0
0x3fa88  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x3fa8d  ldstr    aInsertcommand// "InsertCommand"
0x3fa92  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x3fa97  stloc.s  0xA
0x3fa99  br.s     loc_3FAC1
0x3fa9b  ldloc.0
0x3fa9c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x3faa1  ldstr    aSelectcommand// "SelectCommand"
0x3faa6  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x3faab  stloc.s  0xA
0x3faad  br.s     loc_3FAC1
0x3faaf  ldloc.0
0x3fab0  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x3fab5  ldstr    aUpdatecommand// "UpdateCommand"
0x3faba  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x3fabf  stloc.s  0xA
0x3fac1  ldloc.s  0xA
0x3fac3  brfalse.s loc_3FADC
0x3fac5  ldloc.s  0xA
0x3fac7  ldloc.0
0x3fac8  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::ResetValue(object)
0x3facd  ldloc.s  0xA
0x3facf  ldloc.0
0x3fad0  ldloc.s  8
0x3fad2  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQueryEditorForm::get_Command()
0x3fad7  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x3fadc  ldc.i4.1
0x3fadd  ret
0x3fade  ldc.i4.0
0x3fadf  ret
```
