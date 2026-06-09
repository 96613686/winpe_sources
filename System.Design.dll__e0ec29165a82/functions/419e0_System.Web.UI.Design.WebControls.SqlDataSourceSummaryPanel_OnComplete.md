# System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::OnComplete

- ea: `0x419e0`
- end: `0x41cb1`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::OnComplete`
- size: `721`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3e400`
- `0x3edb0`
- `0x3f8a0`
- `0x3f8b0`
- `0x3f8c0`
- `0x419e0`
- `0x584f0`

## string_xrefs

- `0x41afb`: `SelectCommand`
- `0x41a0f`: `DeleteCommand`
- `0x41a85`: `InsertCommand`
- `0x41b71`: `UpdateCommand`
- `0x41a45`: `DeleteCommandType`
- `0x41abb`: `InsertCommandType`
- `0x41b31`: `SelectCommandType`
- `0x41ba7`: `UpdateCommandType`

## pseudocode

```c

```

## disassembly

```asm
0x419e0  ldarg.0
0x419e1  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x419e6  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x419eb  castclass [System.Web]System.Web.UI.WebControls.SqlDataSource
0x419f0  stloc.1
0x419f1  ldloc.1
0x419f2  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteCommand()
0x419f7  ldarg.0
0x419f8  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_deleteQuery
0x419fd  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41a02  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x41a07  brfalse.s loc_41A2C
0x41a09  ldloc.1
0x41a0a  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41a0f  ldstr    aDeletecommand// "DeleteCommand"
0x41a14  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41a19  stloc.0
0x41a1a  ldloc.0
0x41a1b  ldloc.1
0x41a1c  ldarg.0
0x41a1d  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_deleteQuery
0x41a22  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41a27  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41a2c  ldloc.1
0x41a2d  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteCommandType()
0x41a32  ldarg.0
0x41a33  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_deleteQuery
0x41a38  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41a3d  beq.s    loc_41A67
0x41a3f  ldloc.1
0x41a40  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41a45  ldstr    aDeletecommandt// "DeleteCommandType"
0x41a4a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41a4f  stloc.0
0x41a50  ldloc.0
0x41a51  ldloc.1
0x41a52  ldarg.0
0x41a53  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_deleteQuery
0x41a58  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41a5d  box      [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType
0x41a62  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41a67  ldloc.1
0x41a68  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertCommand()
0x41a6d  ldarg.0
0x41a6e  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_insertQuery
0x41a73  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41a78  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x41a7d  brfalse.s loc_41AA2
0x41a7f  ldloc.1
0x41a80  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41a85  ldstr    aInsertcommand// "InsertCommand"
0x41a8a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41a8f  stloc.0
0x41a90  ldloc.0
0x41a91  ldloc.1
0x41a92  ldarg.0
0x41a93  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_insertQuery
0x41a98  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41a9d  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41aa2  ldloc.1
0x41aa3  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertCommandType()
0x41aa8  ldarg.0
0x41aa9  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_insertQuery
0x41aae  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41ab3  beq.s    loc_41ADD
0x41ab5  ldloc.1
0x41ab6  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41abb  ldstr    aInsertcommandt// "InsertCommandType"
0x41ac0  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41ac5  stloc.0
0x41ac6  ldloc.0
0x41ac7  ldloc.1
0x41ac8  ldarg.0
0x41ac9  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_insertQuery
0x41ace  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41ad3  box      [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType
0x41ad8  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41add  ldloc.1
0x41ade  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectCommand()
0x41ae3  ldarg.0
0x41ae4  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41ae9  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41aee  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x41af3  brfalse.s loc_41B18
0x41af5  ldloc.1
0x41af6  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41afb  ldstr    aSelectcommand// "SelectCommand"
0x41b00  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41b05  stloc.0
0x41b06  ldloc.0
0x41b07  ldloc.1
0x41b08  ldarg.0
0x41b09  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41b0e  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41b13  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41b18  ldloc.1
0x41b19  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectCommandType()
0x41b1e  ldarg.0
0x41b1f  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41b24  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41b29  beq.s    loc_41B53
0x41b2b  ldloc.1
0x41b2c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41b31  ldstr    aSelectcommandt// "SelectCommandType"
0x41b36  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41b3b  stloc.0
0x41b3c  ldloc.0
0x41b3d  ldloc.1
0x41b3e  ldarg.0
0x41b3f  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41b44  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41b49  box      [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType
0x41b4e  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41b53  ldloc.1
0x41b54  callvirt instance string [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateCommand()
0x41b59  ldarg.0
0x41b5a  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_updateQuery
0x41b5f  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41b64  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x41b69  brfalse.s loc_41B8E
0x41b6b  ldloc.1
0x41b6c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41b71  ldstr    aUpdatecommand// "UpdateCommand"
0x41b76  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41b7b  stloc.0
0x41b7c  ldloc.0
0x41b7d  ldloc.1
0x41b7e  ldarg.0
0x41b7f  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_updateQuery
0x41b84  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41b89  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41b8e  ldloc.1
0x41b8f  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateCommandType()
0x41b94  ldarg.0
0x41b95  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_updateQuery
0x41b9a  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41b9f  beq.s    loc_41BC9
0x41ba1  ldloc.1
0x41ba2  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x41ba7  ldstr    aUpdatecommandt// "UpdateCommandType"
0x41bac  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x41bb1  stloc.0
0x41bb2  ldloc.0
0x41bb3  ldloc.1
0x41bb4  ldarg.0
0x41bb5  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_updateQuery
0x41bba  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41bbf  box      [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType
0x41bc4  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x41bc9  ldarg.0
0x41bca  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41bcf  ldarg.0
0x41bd0  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41bd5  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41bda  ldloc.1
0x41bdb  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_SelectParameters()
0x41be0  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CopyList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IList dest)
0x41be5  ldarg.0
0x41be6  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41beb  ldarg.0
0x41bec  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_insertQuery
0x41bf1  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41bf6  ldloc.1
0x41bf7  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_InsertParameters()
0x41bfc  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CopyList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IList dest)
0x41c01  ldarg.0
0x41c02  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41c07  ldarg.0
0x41c08  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_updateQuery
0x41c0d  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41c12  ldloc.1
0x41c13  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_UpdateParameters()
0x41c18  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CopyList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IList dest)
0x41c1d  ldarg.0
0x41c1e  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41c23  ldarg.0
0x41c24  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_deleteQuery
0x41c29  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41c2e  ldloc.1
0x41c2f  callvirt instance class [System.Web]System.Web.UI.WebControls.ParameterCollection [System.Web]System.Web.UI.WebControls.SqlDataSource::get_DeleteParameters()
0x41c34  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CopyList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IList dest)
0x41c39  newobj   instance void [System.Web]System.Web.UI.WebControls.ParameterCollection::.ctor()
0x41c3e  stloc.2
0x41c3f  ldarg.0
0x41c40  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41c45  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41c4a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x41c4f  stloc.3
0x41c50  br.s     loc_41C68
0x41c52  ldloc.3
0x41c53  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x41c58  castclass [System.Web]System.Web.UI.WebControls.Parameter
0x41c5d  stloc.s  4
0x41c5f  ldloc.2
0x41c60  ldloc.s  4
0x41c62  callvirt instance int32 [System.Web]System.Web.UI.WebControls.ParameterCollection::Add(class [System.Web]System.Web.UI.WebControls.Parameter)
0x41c67  pop
0x41c68  ldloc.3
0x41c69  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41c6e  brtrue.s loc_41C52
0x41c70  leave.s  loc_41C86
0x41c72  ldloc.3
0x41c73  isinst   [mscorlib]System.IDisposable
0x41c78  stloc.s  5
0x41c7a  ldloc.s  5
0x41c7c  brfalse.s loc_41C85
0x41c7e  ldloc.s  5
0x41c80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41c85  endfinally
0x41c86  ldarg.0
0x41c87  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41c8c  ldarg.0
0x41c8d  ldfld    class System.ComponentModel.Design.Data.DesignerDataConnection System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_dataConnection
0x41c92  ldarg.0
0x41c93  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41c98  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41c9d  ldarg.0
0x41c9e  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41ca3  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41ca8  ldloc.2
0x41ca9  ldc.i4.1
0x41caa  callvirt instance bool System.Web.UI.Design.WebControls.SqlDataSourceDesigner::RefreshSchema(class System.ComponentModel.Design.Data.DesignerDataConnection connection, string commandText, valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType commandType, class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, bool preferSilent)
0x41caf  pop
0x41cb0  ret
```
