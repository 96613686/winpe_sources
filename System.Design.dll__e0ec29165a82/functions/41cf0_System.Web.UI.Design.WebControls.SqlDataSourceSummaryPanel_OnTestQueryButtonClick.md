# System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::OnTestQueryButtonClick

- ea: `0x41cf0`
- end: `0x41f65`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::OnTestQueryButtonClick`
- size: `629`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x3e0b0`
- `0x3e480`
- `0x3e570`
- `0x3e590`
- `0x3f0d0`
- `0x3f8a0`
- `0x3f8b0`
- `0x3f8c0`
- `0x41cf0`
- `0x52b80`
- `0x52bb0`
- `0x52bf0`
- `0x54220`
- `0x70ed0`
- `0x8ef40`

## string_xrefs

- `0x41e05`: `SqlDataSourceSummaryPanel_CouldNotCreateConnection`
- `0x41e25`: `SqlDataSourceSummaryPanel_CouldNotCreateConnection`

## pseudocode

```c

```

## disassembly

```asm
0x41cf0  newobj   instance void [System.Web]System.Web.UI.WebControls.ParameterCollection::.ctor()
0x41cf5  stloc.0
0x41cf6  ldarg.0
0x41cf7  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41cfc  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Parameters()
0x41d01  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x41d06  stloc.3
0x41d07  br.s     loc_41D65
0x41d09  ldloc.3
0x41d0a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x41d0f  castclass [System.Web]System.Web.UI.WebControls.Parameter
0x41d14  stloc.s  4
0x41d16  ldloc.s  4
0x41d18  callvirt instance valuetype [System.Data]System.Data.DbType [System.Web]System.Web.UI.WebControls.Parameter::get_DbType()
0x41d1d  ldc.i4.s 0xD
0x41d1f  bne.un.s loc_41D44
0x41d21  ldloc.0
0x41d22  ldloc.s  4
0x41d24  callvirt instance string [System.Web]System.Web.UI.WebControls.Parameter::get_Name()
0x41d29  ldloc.s  4
0x41d2b  callvirt instance valuetype [mscorlib]System.TypeCode [System.Web]System.Web.UI.WebControls.Parameter::get_Type()
0x41d30  ldloc.s  4
0x41d32  callvirt instance string [System.Web]System.Web.UI.WebControls.Parameter::get_DefaultValue()
0x41d37  newobj   instance void [System.Web]System.Web.UI.WebControls.Parameter::.ctor(string, valuetype [mscorlib]System.TypeCode, string)
0x41d3c  callvirt instance int32 [System.Web]System.Web.UI.WebControls.ParameterCollection::Add(class [System.Web]System.Web.UI.WebControls.Parameter)
0x41d41  pop
0x41d42  br.s     loc_41D65
0x41d44  ldloc.0
0x41d45  ldloc.s  4
0x41d47  callvirt instance string [System.Web]System.Web.UI.WebControls.Parameter::get_Name()
0x41d4c  ldloc.s  4
0x41d4e  callvirt instance valuetype [System.Data]System.Data.DbType [System.Web]System.Web.UI.WebControls.Parameter::get_DbType()
0x41d53  ldloc.s  4
0x41d55  callvirt instance string [System.Web]System.Web.UI.WebControls.Parameter::get_DefaultValue()
0x41d5a  newobj   instance void [System.Web]System.Web.UI.WebControls.Parameter::.ctor(string, valuetype [System.Data]System.Data.DbType, string)
0x41d5f  callvirt instance int32 [System.Web]System.Web.UI.WebControls.ParameterCollection::Add(class [System.Web]System.Web.UI.WebControls.Parameter)
0x41d64  pop
0x41d65  ldloc.3
0x41d66  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41d6b  brtrue.s loc_41D09
0x41d6d  leave.s  loc_41D83
0x41d6f  ldloc.3
0x41d70  isinst   [mscorlib]System.IDisposable
0x41d75  stloc.s  5
0x41d77  ldloc.s  5
0x41d79  brfalse.s loc_41D82
0x41d7b  ldloc.s  5
0x41d7d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41d82  endfinally
0x41d83  ldloc.0
0x41d84  callvirt instance int32 [System.Web]System.Web.UI.StateManagedCollection::get_Count()
0x41d89  ldc.i4.0
0x41d8a  ble.s    loc_41DAF
0x41d8c  ldarg.0
0x41d8d  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41d92  ldloc.0
0x41d93  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceParameterValueEditorForm::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters)
0x41d98  stloc.s  6
0x41d9a  ldarg.0
0x41d9b  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41da0  ldloc.s  6
0x41da2  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult System.Web.UI.Design.Util.UIServiceHelper::ShowDialog(class [mscorlib]System.IServiceProvider serviceProvider, class [System.Windows.Forms]System.Windows.Forms.Form form)
0x41da7  stloc.s  7
0x41da9  ldloc.s  7
0x41dab  ldc.i4.2
0x41dac  bne.un.s loc_41DAF
0x41dae  ret
0x41daf  ldarg.0
0x41db0  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_resultsGridView
0x41db5  ldnull
0x41db6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_DataSource(object)
0x41dbb  ldnull
0x41dbc  stloc.1
0x41dbd  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x41dc2  stloc.2
0x41dc3  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x41dc8  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x41dcd  ldarg.0
0x41dce  ldfld    class System.ComponentModel.Design.Data.DesignerDataConnection System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_dataConnection
0x41dd3  callvirt instance string System.ComponentModel.Design.Data.DesignerDataConnection::get_ProviderName()
0x41dd8  call     class [System.Data]System.Data.Common.DbProviderFactory System.Web.UI.Design.WebControls.SqlDataSourceDesigner::GetDbProviderFactory(string providerName)
0x41ddd  stloc.s  8
0x41ddf  ldnull
0x41de0  stloc.s  9
0x41de2  ldarg.0
0x41de3  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41de8  ldarg.0
0x41de9  ldfld    class System.ComponentModel.Design.Data.DesignerDataConnection System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_dataConnection
0x41dee  call     class [System.Data]System.Data.Common.DbConnection System.Web.UI.Design.WebControls.SqlDataSourceDesigner::GetDesignTimeConnection(class [mscorlib]System.IServiceProvider serviceProvider, class System.ComponentModel.Design.Data.DesignerDataConnection connection)
0x41df3  stloc.s  9
0x41df5  leave.s  loc_41E1B
0x41df7  stloc.s  0xC
0x41df9  ldloc.s  9
0x41dfb  brtrue.s loc_41E19
0x41dfd  ldarg.0
0x41dfe  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41e03  ldloc.s  0xC
0x41e05  ldstr    aSqldatasources_12// "SqlDataSourceSummaryPanel_CouldNotCreat"...
0x41e0a  call     string System.Design.SR::GetString(string name)
0x41e0f  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Exception ex, string message)
0x41e14  leave    loc_41F64
0x41e19  leave.s  loc_41E1B
0x41e1b  ldloc.s  9
0x41e1d  brtrue.s loc_41E39
0x41e1f  ldarg.0
0x41e20  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41e25  ldstr    aSqldatasources_12// "SqlDataSourceSummaryPanel_CouldNotCreat"...
0x41e2a  call     string System.Design.SR::GetString(string name)
0x41e2f  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x41e34  leave    loc_41F64
0x41e39  ldarg.0
0x41e3a  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceDesigner System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_sqlDataSourceDesigner
0x41e3f  ldloc.s  8
0x41e41  ldloc.s  9
0x41e43  ldarg.0
0x41e44  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41e49  callvirt instance string System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_Command()
0x41e4e  ldloc.0
0x41e4f  ldarg.0
0x41e50  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceQuery System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_selectQuery
0x41e55  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.Design.WebControls.SqlDataSourceQuery::get_CommandType()
0x41e5a  callvirt instance class [System.Data]System.Data.Common.DbCommand System.Web.UI.Design.WebControls.SqlDataSourceDesigner::BuildSelectCommand(class [System.Data]System.Data.Common.DbProviderFactory factory, class [System.Data]System.Data.Common.DbConnection connection, string commandText, class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType commandType)
0x41e5f  stloc.1
0x41e60  ldloc.s  8
0x41e62  ldloc.1
0x41e63  call     class [System.Data]System.Data.Common.DbDataAdapter System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CreateDataAdapter(class [System.Data]System.Data.Common.DbProviderFactory factory, class [System.Data]System.Data.Common.DbCommand command)
0x41e68  stloc.s  0xA
0x41e6a  ldloc.s  0xA
0x41e6c  ldc.i4.4
0x41e6d  callvirt instance void [System.Data]System.Data.Common.DataAdapter::set_MissingSchemaAction(valuetype [System.Data]System.Data.MissingSchemaAction)
0x41e72  newobj   instance void [System.Data]System.Data.DataSet::.ctor()
0x41e77  stloc.s  0xB
0x41e79  ldloc.s  0xA
0x41e7b  ldloc.s  0xB
0x41e7d  callvirt instance int32 [System.Data]System.Data.Common.DataAdapter::Fill(class [System.Data]System.Data.DataSet)
0x41e82  pop
0x41e83  ldloc.s  0xB
0x41e85  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x41e8a  callvirt instance int32 [System.Data]System.Data.InternalDataCollectionBase::get_Count()
0x41e8f  brtrue.s loc_41EAB
0x41e91  ldarg.0
0x41e92  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41e97  ldstr    aSqldatasources_13// "SqlDataSourceSummaryPanel_CannotExecute"...
0x41e9c  call     string System.Design.SR::GetString(string name)
0x41ea1  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x41ea6  leave    loc_41F64
0x41eab  ldarg.0
0x41eac  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_resultsGridView
0x41eb1  ldloc.s  0xB
0x41eb3  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x41eb8  ldc.i4.0
0x41eb9  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(int32)
0x41ebe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_DataSource(object)
0x41ec3  ldarg.0
0x41ec4  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_resultsGridView
0x41ec9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection [System.Windows.Forms]System.Windows.Forms.DataGridView::get_Columns()
0x41ece  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Windows.Forms]System.Windows.Forms.BaseCollection::GetEnumerator()
0x41ed3  stloc.s  0xD
0x41ed5  br.s     loc_41EED
0x41ed7  ldloc.s  0xD
0x41ed9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x41ede  castclass [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn
0x41ee3  stloc.s  0xE
0x41ee5  ldloc.s  0xE
0x41ee7  ldc.i4.0
0x41ee8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_SortMode(valuetype [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnSortMode)
0x41eed  ldloc.s  0xD
0x41eef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41ef4  brtrue.s loc_41ED7
0x41ef6  leave.s  loc_41F0D
0x41ef8  ldloc.s  0xD
0x41efa  isinst   [mscorlib]System.IDisposable
0x41eff  stloc.s  5
0x41f01  ldloc.s  5
0x41f03  brfalse.s loc_41F0C
0x41f05  ldloc.s  5
0x41f07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41f0c  endfinally
0x41f0d  ldarg.0
0x41f0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_resultsGridView
0x41f13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::AutoResizeColumnHeadersHeight()
0x41f18  ldarg.0
0x41f19  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceSummaryPanel::_resultsGridView
0x41f1e  ldc.i4.6
0x41f1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::AutoResizeColumns(valuetype [System.Windows.Forms]System.Windows.Forms.DataGridViewAutoSizeColumnsMode)
0x41f24  leave.s  loc_41F64
0x41f26  stloc.s  0xF
0x41f28  ldarg.0
0x41f29  call     instance class [mscorlib]System.IServiceProvider System.Web.UI.Design.Util.WizardPanel::get_ServiceProvider()
0x41f2e  ldloc.s  0xF
0x41f30  ldstr    aSqldatasources_14// "SqlDataSourceSummaryPanel_CannotExecute"...
0x41f35  call     string System.Design.SR::GetString(string name)
0x41f3a  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Exception ex, string message)
0x41f3f  leave.s  loc_41F64
0x41f41  ldloc.1
0x41f42  brfalse.s loc_41F5D
0x41f44  ldloc.1
0x41f45  callvirt instance class [System.Data]System.Data.Common.DbConnection [System.Data]System.Data.Common.DbCommand::get_Connection()
0x41f4a  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x41f4f  ldc.i4.1
0x41f50  bne.un.s loc_41F5D
0x41f52  ldloc.1
0x41f53  callvirt instance class [System.Data]System.Data.Common.DbConnection [System.Data]System.Data.Common.DbCommand::get_Connection()
0x41f58  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x41f5d  ldloc.2
0x41f5e  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x41f63  endfinally
0x41f64  ret
```
