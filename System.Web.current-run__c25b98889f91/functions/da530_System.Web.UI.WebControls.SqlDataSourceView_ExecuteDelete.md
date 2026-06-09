# System.Web.UI.WebControls.SqlDataSourceView::ExecuteDelete

- ea: `0xda530`
- end: `0xda668`
- name: `System.Web.UI.WebControls.SqlDataSourceView::ExecuteDelete`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x34f20`
- `0x34fa0`
- `0x5f1b0`
- `0x69190`
- `0xd8d90`
- `0xd9210`
- `0xd9230`
- `0xd97f0`
- `0xd9b60`
- `0xd9ba0`
- `0xd9bd0`
- `0xd9c00`
- `0xd9d50`
- `0xda1b0`
- `0xda410`
- `0xda530`
- `0xdadb0`
- `0xdadc0`
- `0xdafb0`
- `0xdb1d0`

## string_xrefs

- `0xda5f3`: `DataSourceView_delete`
- `0xda538`: `SqlDataSourceView_DeleteNotSupported`
- `0xda576`: `SqlDataSourceView_CouldNotCreateConnection`

## pseudocode

```c

```

## disassembly

```asm
0xda530  ldarg.0
0xda531  callvirt instance bool System.Web.UI.DataSourceView::get_CanDelete()
0xda536  brtrue.s loc_DA55C
0xda538  ldstr    aSqldatasourcev_1// "SqlDataSourceView_DeleteNotSupported"
0xda53d  ldc.i4.1
0xda53e  newarr   [mscorlib]System.Object
0xda543  dup
0xda544  ldc.i4.0
0xda545  ldarg.0
0xda546  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda54b  callvirt instance string System.Web.UI.Control::get_ID()
0xda550  stelem.ref
0xda551  call     string System.Web.SR::GetString(string name, object[] args)
0xda556  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xda55b  throw
0xda55c  ldarg.0
0xda55d  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda562  ldarg.0
0xda563  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda568  callvirt instance string System.Web.UI.WebControls.SqlDataSource::get_ConnectionString()
0xda56d  callvirt instance class [System.Data]System.Data.Common.DbConnection System.Web.UI.WebControls.SqlDataSource::CreateConnection(string connectionString)
0xda572  stloc.0
0xda573  ldloc.0
0xda574  brtrue.s loc_DA59A
0xda576  ldstr    aSqldatasourcev_2// "SqlDataSourceView_CouldNotCreateConnect"...
0xda57b  ldc.i4.1
0xda57c  newarr   [mscorlib]System.Object
0xda581  dup
0xda582  ldc.i4.0
0xda583  ldarg.0
0xda584  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda589  callvirt instance string System.Web.UI.Control::get_ID()
0xda58e  stelem.ref
0xda58f  call     string System.Web.SR::GetString(string name, object[] args)
0xda594  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xda599  throw
0xda59a  ldarg.0
0xda59b  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_OldValuesParameterFormatString()
0xda5a0  stloc.1
0xda5a1  ldarg.0
0xda5a2  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda5a7  ldarg.0
0xda5a8  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_DeleteCommand()
0xda5ad  ldloc.0
0xda5ae  callvirt instance class [System.Data]System.Data.Common.DbCommand System.Web.UI.WebControls.SqlDataSource::CreateCommand(string commandText, class [System.Data]System.Data.Common.DbConnection connection)
0xda5b3  stloc.2
0xda5b4  ldarg.0
0xda5b5  ldloc.2
0xda5b6  ldarg.0
0xda5b7  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_DeleteParameters()
0xda5bc  ldarg.2
0xda5bd  call     instance void System.Web.UI.WebControls.SqlDataSourceView::InitializeParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Collections.IDictionary exclusionList)
0xda5c2  ldarg.0
0xda5c3  ldloc.2
0xda5c4  ldarg.0
0xda5c5  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_DeleteParameters()
0xda5ca  ldarg.1
0xda5cb  ldnull
0xda5cc  ldloc.1
0xda5cd  call     instance void System.Web.UI.WebControls.SqlDataSourceView::AddParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary parameters, class [mscorlib]System.Collections.IDictionary exclusionList, string oldValuesParameterFormatString)
0xda5d2  ldarg.0
0xda5d3  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.SqlDataSourceView::get_ConflictDetection()
0xda5d8  ldc.i4.1
0xda5d9  bne.un.s loc_DA62F
0xda5db  ldarg.2
0xda5dc  brfalse.s loc_DA5E6
0xda5de  ldarg.2
0xda5df  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xda5e4  brtrue.s loc_DA61F
0xda5e6  ldstr    aSqldatasourcev_3// "SqlDataSourceView_Pessimistic"
0xda5eb  ldc.i4.3
0xda5ec  newarr   [mscorlib]System.Object
0xda5f1  dup
0xda5f2  ldc.i4.0
0xda5f3  ldstr    aDatasourceview_2// "DataSourceView_delete"
0xda5f8  call     string System.Web.SR::GetString(string name)
0xda5fd  stelem.ref
0xda5fe  dup
0xda5ff  ldc.i4.1
0xda600  ldarg.0
0xda601  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda606  callvirt instance string System.Web.UI.Control::get_ID()
0xda60b  stelem.ref
0xda60c  dup
0xda60d  ldc.i4.2
0xda60e  ldstr    aValues// "values"
0xda613  stelem.ref
0xda614  call     string System.Web.SR::GetString(string name, object[] args)
0xda619  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xda61e  throw
0xda61f  ldarg.0
0xda620  ldloc.2
0xda621  ldarg.0
0xda622  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_DeleteParameters()
0xda627  ldarg.2
0xda628  ldnull
0xda629  ldloc.1
0xda62a  call     instance void System.Web.UI.WebControls.SqlDataSourceView::AddParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary parameters, class [mscorlib]System.Collections.IDictionary exclusionList, string oldValuesParameterFormatString)
0xda62f  ldloc.2
0xda630  ldarg.0
0xda631  call     instance valuetype System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.WebControls.SqlDataSourceView::get_DeleteCommandType()
0xda636  call     valuetype [System.Data]System.Data.CommandType System.Web.UI.WebControls.SqlDataSourceView::GetCommandType(valuetype System.Web.UI.WebControls.SqlDataSourceCommandType commandType)
0xda63b  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xda640  ldloc.2
0xda641  newobj   instance void System.Web.UI.WebControls.SqlDataSourceCommandEventArgs::.ctor(class [System.Data]System.Data.Common.DbCommand command)
0xda646  stloc.3
0xda647  ldarg.0
0xda648  ldloc.3
0xda649  callvirt instance void System.Web.UI.WebControls.SqlDataSourceView::OnDeleting(class System.Web.UI.WebControls.SqlDataSourceCommandEventArgs e)
0xda64e  ldloc.3
0xda64f  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xda654  brfalse.s loc_DA658
0xda656  ldc.i4.0
0xda657  ret
0xda658  ldarg.0
0xda659  ldloc.2
0xda65a  call     instance void System.Web.UI.WebControls.SqlDataSourceView::ReplaceNullValues(class [System.Data]System.Data.Common.DbCommand command)
0xda65f  ldarg.0
0xda660  ldloc.2
0xda661  ldc.i4.0
0xda662  call     instance int32 System.Web.UI.WebControls.SqlDataSourceView::ExecuteDbCommand(class [System.Data]System.Data.Common.DbCommand command, valuetype System.Web.UI.DataSourceOperation operation)
0xda667  ret
```
