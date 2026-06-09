# System.Web.UI.WebControls.SqlDataSourceView::ExecuteUpdate

- ea: `0xdac60`
- end: `0xdada8`
- name: `System.Web.UI.WebControls.SqlDataSourceView::ExecuteUpdate`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update`

## callees

- `0x34f20`
- `0x34fa0`
- `0x5f1b0`
- `0x691e0`
- `0xd8d90`
- `0xd9210`
- `0xd9230`
- `0xd97f0`
- `0xd9b60`
- `0xd9d50`
- `0xd9ef0`
- `0xd9f20`
- `0xd9f50`
- `0xda1b0`
- `0xda410`
- `0xdac60`
- `0xdadb0`
- `0xdadc0`
- `0xdb100`
- `0xdb1d0`

## string_xrefs

- `0xdad33`: `DataSourceView_update`
- `0xdaca6`: `SqlDataSourceView_CouldNotCreateConnection`
- `0xdac68`: `SqlDataSourceView_UpdateNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0xdac60  ldarg.0
0xdac61  callvirt instance bool System.Web.UI.DataSourceView::get_CanUpdate()
0xdac66  brtrue.s loc_DAC8C
0xdac68  ldstr    aSqldatasourcev_10// "SqlDataSourceView_UpdateNotSupported"
0xdac6d  ldc.i4.1
0xdac6e  newarr   [mscorlib]System.Object
0xdac73  dup
0xdac74  ldc.i4.0
0xdac75  ldarg.0
0xdac76  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdac7b  callvirt instance string System.Web.UI.Control::get_ID()
0xdac80  stelem.ref
0xdac81  call     string System.Web.SR::GetString(string name, object[] args)
0xdac86  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xdac8b  throw
0xdac8c  ldarg.0
0xdac8d  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdac92  ldarg.0
0xdac93  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdac98  callvirt instance string System.Web.UI.WebControls.SqlDataSource::get_ConnectionString()
0xdac9d  callvirt instance class [System.Data]System.Data.Common.DbConnection System.Web.UI.WebControls.SqlDataSource::CreateConnection(string connectionString)
0xdaca2  stloc.0
0xdaca3  ldloc.0
0xdaca4  brtrue.s loc_DACCA
0xdaca6  ldstr    aSqldatasourcev_2// "SqlDataSourceView_CouldNotCreateConnect"...
0xdacab  ldc.i4.1
0xdacac  newarr   [mscorlib]System.Object
0xdacb1  dup
0xdacb2  ldc.i4.0
0xdacb3  ldarg.0
0xdacb4  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdacb9  callvirt instance string System.Web.UI.Control::get_ID()
0xdacbe  stelem.ref
0xdacbf  call     string System.Web.SR::GetString(string name, object[] args)
0xdacc4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdacc9  throw
0xdacca  ldarg.0
0xdaccb  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_OldValuesParameterFormatString()
0xdacd0  stloc.1
0xdacd1  ldarg.0
0xdacd2  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdacd7  ldarg.0
0xdacd8  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_UpdateCommand()
0xdacdd  ldloc.0
0xdacde  callvirt instance class [System.Data]System.Data.Common.DbCommand System.Web.UI.WebControls.SqlDataSource::CreateCommand(string commandText, class [System.Data]System.Data.Common.DbConnection connection)
0xdace3  stloc.2
0xdace4  ldarg.0
0xdace5  ldloc.2
0xdace6  ldarg.0
0xdace7  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_UpdateParameters()
0xdacec  ldarg.1
0xdaced  call     instance void System.Web.UI.WebControls.SqlDataSourceView::InitializeParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Collections.IDictionary exclusionList)
0xdacf2  ldarg.0
0xdacf3  ldloc.2
0xdacf4  ldarg.0
0xdacf5  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_UpdateParameters()
0xdacfa  ldarg.2
0xdacfb  ldnull
0xdacfc  ldnull
0xdacfd  call     instance void System.Web.UI.WebControls.SqlDataSourceView::AddParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary parameters, class [mscorlib]System.Collections.IDictionary exclusionList, string oldValuesParameterFormatString)
0xdad02  ldarg.0
0xdad03  ldloc.2
0xdad04  ldarg.0
0xdad05  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_UpdateParameters()
0xdad0a  ldarg.1
0xdad0b  ldnull
0xdad0c  ldloc.1
0xdad0d  call     instance void System.Web.UI.WebControls.SqlDataSourceView::AddParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary parameters, class [mscorlib]System.Collections.IDictionary exclusionList, string oldValuesParameterFormatString)
0xdad12  ldarg.0
0xdad13  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.SqlDataSourceView::get_ConflictDetection()
0xdad18  ldc.i4.1
0xdad19  bne.un.s loc_DAD6F
0xdad1b  ldarg.3
0xdad1c  brfalse.s loc_DAD26
0xdad1e  ldarg.3
0xdad1f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xdad24  brtrue.s loc_DAD5F
0xdad26  ldstr    aSqldatasourcev_3// "SqlDataSourceView_Pessimistic"
0xdad2b  ldc.i4.3
0xdad2c  newarr   [mscorlib]System.Object
0xdad31  dup
0xdad32  ldc.i4.0
0xdad33  ldstr    aDatasourceview_3// "DataSourceView_update"
0xdad38  call     string System.Web.SR::GetString(string name)
0xdad3d  stelem.ref
0xdad3e  dup
0xdad3f  ldc.i4.1
0xdad40  ldarg.0
0xdad41  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdad46  callvirt instance string System.Web.UI.Control::get_ID()
0xdad4b  stelem.ref
0xdad4c  dup
0xdad4d  ldc.i4.2
0xdad4e  ldstr    aOldvalues// "oldValues"
0xdad53  stelem.ref
0xdad54  call     string System.Web.SR::GetString(string name, object[] args)
0xdad59  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdad5e  throw
0xdad5f  ldarg.0
0xdad60  ldloc.2
0xdad61  ldarg.0
0xdad62  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_UpdateParameters()
0xdad67  ldarg.3
0xdad68  ldnull
0xdad69  ldloc.1
0xdad6a  call     instance void System.Web.UI.WebControls.SqlDataSourceView::AddParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary parameters, class [mscorlib]System.Collections.IDictionary exclusionList, string oldValuesParameterFormatString)
0xdad6f  ldloc.2
0xdad70  ldarg.0
0xdad71  call     instance valuetype System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.WebControls.SqlDataSourceView::get_UpdateCommandType()
0xdad76  call     valuetype [System.Data]System.Data.CommandType System.Web.UI.WebControls.SqlDataSourceView::GetCommandType(valuetype System.Web.UI.WebControls.SqlDataSourceCommandType commandType)
0xdad7b  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xdad80  ldloc.2
0xdad81  newobj   instance void System.Web.UI.WebControls.SqlDataSourceCommandEventArgs::.ctor(class [System.Data]System.Data.Common.DbCommand command)
0xdad86  stloc.3
0xdad87  ldarg.0
0xdad88  ldloc.3
0xdad89  callvirt instance void System.Web.UI.WebControls.SqlDataSourceView::OnUpdating(class System.Web.UI.WebControls.SqlDataSourceCommandEventArgs e)
0xdad8e  ldloc.3
0xdad8f  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xdad94  brfalse.s loc_DAD98
0xdad96  ldc.i4.0
0xdad97  ret
0xdad98  ldarg.0
0xdad99  ldloc.2
0xdad9a  call     instance void System.Web.UI.WebControls.SqlDataSourceView::ReplaceNullValues(class [System.Data]System.Data.Common.DbCommand command)
0xdad9f  ldarg.0
0xdada0  ldloc.2
0xdada1  ldc.i4.3
0xdada2  call     instance int32 System.Web.UI.WebControls.SqlDataSourceView::ExecuteDbCommand(class [System.Data]System.Data.Common.DbCommand command, valuetype System.Web.UI.DataSourceOperation operation)
0xdada7  ret
```
