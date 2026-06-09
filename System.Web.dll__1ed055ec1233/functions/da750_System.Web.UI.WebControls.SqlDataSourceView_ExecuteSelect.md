# System.Web.UI.WebControls.SqlDataSourceView::ExecuteSelect

- ea: `0xda750`
- end: `0xdac5d`
- name: `System.Web.UI.WebControls.SqlDataSourceView::ExecuteSelect`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x8e4a0`

## callees

- `0x34f20`
- `0x5f1b0`
- `0x68550`
- `0x68f70`
- `0x68f90`
- `0x69030`
- `0x690e0`
- `0x691b0`
- `0x691c0`
- `0x691d0`
- `0x69210`
- `0x7d0f0`
- `0xad4b0`
- `0xd1140`
- `0xd8cd0`
- `0xd8d90`
- `0xd8de0`
- `0xd9210`
- `0xd9230`
- `0xd9250`
- `0xd9290`
- `0xd9640`
- `0xd9700`
- `0xd9880`
- `0xd9910`
- `0xd9990`
- `0xd99e0`
- `0xd9ac0`
- `0xd9c20`
- `0xd9c70`
- `0xd9d90`
- `0xd9dd0`
- `0xd9e20`
- `0xd9e50`
- `0xd9ea0`
- `0xda310`
- `0xda750`
- `0xdadb0`
- `0xdadc0`
- `0xdafe0`
- `0xdb070`
- `0xdb0a0`
- `0xdb1d0`
- `0x189ba0`

## string_xrefs

- `0xdaa0f`: `CommandNotification`
- `0xda779`: `SqlDataSourceView_CouldNotCreateConnection`
- `0xda7fe`: `SqlDataSourceView_CacheNotSupported`
- `0xdaa25`: `SqlDataSourceView_CommandNotificationNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0xda750  ldarg.0
0xda751  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_SelectCommand()
0xda756  callvirt instance int32 [mscorlib]System.String::get_Length()
0xda75b  brtrue.s loc_DA75F
0xda75d  ldnull
0xda75e  ret
0xda75f  ldarg.0
0xda760  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda765  ldarg.0
0xda766  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda76b  callvirt instance string System.Web.UI.WebControls.SqlDataSource::get_ConnectionString()
0xda770  callvirt instance class [System.Data]System.Data.Common.DbConnection System.Web.UI.WebControls.SqlDataSource::CreateConnection(string connectionString)
0xda775  stloc.0
0xda776  ldloc.0
0xda777  brtrue.s loc_DA79D
0xda779  ldstr    aSqldatasourcev_2// "SqlDataSourceView_CouldNotCreateConnect"...
0xda77e  ldc.i4.1
0xda77f  newarr   [mscorlib]System.Object
0xda784  dup
0xda785  ldc.i4.0
0xda786  ldarg.0
0xda787  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda78c  callvirt instance string System.Web.UI.Control::get_ID()
0xda791  stelem.ref
0xda792  call     string System.Web.SR::GetString(string name, object[] args)
0xda797  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xda79c  throw
0xda79d  ldarg.0
0xda79e  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda7a3  callvirt instance class System.Web.UI.DataSourceCache System.Web.UI.WebControls.SqlDataSource::get_Cache()
0xda7a8  stloc.1
0xda7a9  ldloc.1
0xda7aa  brfalse.s loc_DA7B4
0xda7ac  ldloc.1
0xda7ad  callvirt instance bool System.Web.UI.DataSourceCache::get_Enabled()
0xda7b2  br.s     loc_DA7B5
0xda7b4  ldc.i4.0
0xda7b5  stloc.2
0xda7b6  ldarg.1
0xda7b7  callvirt instance string System.Web.UI.DataSourceSelectArguments::get_SortExpression()
0xda7bc  stloc.3
0xda7bd  ldarg.0
0xda7be  callvirt instance bool System.Web.UI.DataSourceView::get_CanPage()
0xda7c3  brfalse.s loc_DA7CC
0xda7c5  ldarg.1
0xda7c6  ldc.i4.2
0xda7c7  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xda7cc  ldarg.0
0xda7cd  callvirt instance bool System.Web.UI.DataSourceView::get_CanSort()
0xda7d2  brfalse.s loc_DA7DB
0xda7d4  ldarg.1
0xda7d5  ldc.i4.1
0xda7d6  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xda7db  ldarg.0
0xda7dc  callvirt instance bool System.Web.UI.DataSourceView::get_CanRetrieveTotalRowCount()
0xda7e1  brfalse.s loc_DA7EA
0xda7e3  ldarg.1
0xda7e4  ldc.i4.4
0xda7e5  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xda7ea  ldloc.2
0xda7eb  brfalse  loc_DA8A0
0xda7f0  ldarg.0
0xda7f1  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda7f6  callvirt instance valuetype System.Web.UI.WebControls.SqlDataSourceMode System.Web.UI.WebControls.SqlDataSource::get_DataSourceMode()
0xda7fb  ldc.i4.1
0xda7fc  beq.s    loc_DA822
0xda7fe  ldstr    aSqldatasourcev_5// "SqlDataSourceView_CacheNotSupported"
0xda803  ldc.i4.1
0xda804  newarr   [mscorlib]System.Object
0xda809  dup
0xda80a  ldc.i4.0
0xda80b  ldarg.0
0xda80c  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda811  callvirt instance string System.Web.UI.Control::get_ID()
0xda816  stelem.ref
0xda817  call     string System.Web.SR::GetString(string name, object[] args)
0xda81c  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xda821  throw
0xda822  ldarg.1
0xda823  ldarg.0
0xda824  callvirt instance void System.Web.UI.DataSourceSelectArguments::RaiseUnsupportedCapabilitiesError(class System.Web.UI.DataSourceView view)
0xda829  ldarg.0
0xda82a  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda82f  ldc.i4.0
0xda830  ldc.i4.m1
0xda831  callvirt instance object System.Web.UI.WebControls.SqlDataSource::LoadDataFromCache(int32 startRowIndex, int32 maximumRows)
0xda836  isinst   [System.Data]System.Data.DataSet
0xda83b  stloc.s  8
0xda83d  ldloc.s  8
0xda83f  brfalse.s loc_DA8A0
0xda841  ldarg.0
0xda842  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_FilterParameters()
0xda847  ldarg.0
0xda848  ldfld    class System.Web.HttpContext System.Web.UI.WebControls.SqlDataSourceView::_context
0xda84d  ldarg.0
0xda84e  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda853  callvirt instance class [System]System.Collections.Specialized.IOrderedDictionary System.Web.UI.WebControls.ParameterCollection::GetValues(class System.Web.HttpContext context, class System.Web.UI.Control control)
0xda858  stloc.s  9
0xda85a  ldarg.0
0xda85b  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_FilterExpression()
0xda860  callvirt instance int32 [mscorlib]System.String::get_Length()
0xda865  ldc.i4.0
0xda866  ble.s    loc_DA884
0xda868  ldloc.s  9
0xda86a  newobj   instance void System.Web.UI.WebControls.SqlDataSourceFilteringEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary parameterValues)
0xda86f  stloc.s  0xA
0xda871  ldarg.0
0xda872  ldloc.s  0xA
0xda874  callvirt instance void System.Web.UI.WebControls.SqlDataSourceView::OnFiltering(class System.Web.UI.WebControls.SqlDataSourceFilteringEventArgs e)
0xda879  ldloc.s  0xA
0xda87b  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xda880  brfalse.s loc_DA884
0xda882  ldnull
0xda883  ret
0xda884  ldloc.s  8
0xda886  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0xda88b  ldc.i4.0
0xda88c  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(int32)
0xda891  ldloc.3
0xda892  ldarg.0
0xda893  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_FilterExpression()
0xda898  ldloc.s  9
0xda89a  call     class [System.Data]System.Data.DataView System.Web.UI.WebControls.FilteredDataSetHelper::CreateFilteredDataView(class [System.Data]System.Data.DataTable table, string sortExpression, string filterExpression, class [mscorlib]System.Collections.IDictionary filterParameters)
0xda89f  ret
0xda8a0  ldarg.0
0xda8a1  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda8a6  ldarg.0
0xda8a7  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_SelectCommand()
0xda8ac  ldloc.0
0xda8ad  callvirt instance class [System.Data]System.Data.Common.DbCommand System.Web.UI.WebControls.SqlDataSource::CreateCommand(string commandText, class [System.Data]System.Data.Common.DbConnection connection)
0xda8b2  stloc.s  4
0xda8b4  ldarg.0
0xda8b5  ldloc.s  4
0xda8b7  ldarg.0
0xda8b8  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.SqlDataSourceView::get_SelectParameters()
0xda8bd  ldnull
0xda8be  call     instance void System.Web.UI.WebControls.SqlDataSourceView::InitializeParameters(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.WebControls.ParameterCollection parameters, class [mscorlib]System.Collections.IDictionary exclusionList)
0xda8c3  ldloc.s  4
0xda8c5  ldarg.0
0xda8c6  call     instance valuetype System.Web.UI.WebControls.SqlDataSourceCommandType System.Web.UI.WebControls.SqlDataSourceView::get_SelectCommandType()
0xda8cb  call     valuetype [System.Data]System.Data.CommandType System.Web.UI.WebControls.SqlDataSourceView::GetCommandType(valuetype System.Web.UI.WebControls.SqlDataSourceCommandType commandType)
0xda8d0  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xda8d5  ldloc.s  4
0xda8d7  ldarg.1
0xda8d8  newobj   instance void System.Web.UI.WebControls.SqlDataSourceSelectingEventArgs::.ctor(class [System.Data]System.Data.Common.DbCommand command, class System.Web.UI.DataSourceSelectArguments arguments)
0xda8dd  stloc.s  5
0xda8df  ldarg.0
0xda8e0  ldloc.s  5
0xda8e2  callvirt instance void System.Web.UI.WebControls.SqlDataSourceView::OnSelecting(class System.Web.UI.WebControls.SqlDataSourceSelectingEventArgs e)
0xda8e7  ldloc.s  5
0xda8e9  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xda8ee  brfalse.s loc_DA8F2
0xda8f0  ldnull
0xda8f1  ret
0xda8f2  ldarg.0
0xda8f3  call     instance string System.Web.UI.WebControls.SqlDataSourceView::get_SortParameterName()
0xda8f8  stloc.s  6
0xda8fa  ldloc.s  6
0xda8fc  callvirt instance int32 [mscorlib]System.String::get_Length()
0xda901  ldc.i4.0
0xda902  ble.s    loc_DA963
0xda904  ldloc.s  4
0xda906  callvirt instance valuetype [System.Data]System.Data.CommandType [System.Data]System.Data.Common.DbCommand::get_CommandType()
0xda90b  ldc.i4.4
0xda90c  beq.s    loc_DA932
0xda90e  ldstr    aSqldatasourcev_6// "SqlDataSourceView_SortParameterRequires"...
0xda913  ldc.i4.1
0xda914  newarr   [mscorlib]System.Object
0xda919  dup
0xda91a  ldc.i4.0
0xda91b  ldarg.0
0xda91c  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda921  callvirt instance string System.Web.UI.Control::get_ID()
0xda926  stelem.ref
0xda927  call     string System.Web.SR::GetString(string name, object[] args)
0xda92c  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xda931  throw
0xda932  ldloc.s  4
0xda934  callvirt instance class [System.Data]System.Data.Common.DbParameterCollection [System.Data]System.Data.Common.DbCommand::get_Parameters()
0xda939  ldarg.0
0xda93a  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda93f  ldarg.0
0xda940  callvirt instance string System.Web.UI.WebControls.SqlDataSourceView::get_ParameterPrefix()
0xda945  ldloc.s  6
0xda947  call     string [mscorlib]System.String::Concat(string, string)
0xda94c  ldloc.3
0xda94d  callvirt instance class [System.Data]System.Data.Common.DbParameter System.Web.UI.WebControls.SqlDataSource::CreateParameter(string parameterName, object parameterValue)
0xda952  callvirt instance int32 [System.Data]System.Data.Common.DbParameterCollection::Add(object)
0xda957  pop
0xda958  ldarg.1
0xda959  ldsfld   string [mscorlib]System.String::Empty
0xda95e  callvirt instance void System.Web.UI.DataSourceSelectArguments::set_SortExpression(string value)
0xda963  ldarg.1
0xda964  ldarg.0
0xda965  callvirt instance void System.Web.UI.DataSourceSelectArguments::RaiseUnsupportedCapabilitiesError(class System.Web.UI.DataSourceView view)
0xda96a  ldarg.1
0xda96b  callvirt instance string System.Web.UI.DataSourceSelectArguments::get_SortExpression()
0xda970  stloc.3
0xda971  ldarg.0
0xda972  call     instance bool System.Web.UI.WebControls.SqlDataSourceView::get_CancelSelectOnNullParameter()
0xda977  brfalse.s loc_DA9CB
0xda979  ldloc.s  4
0xda97b  callvirt instance class [System.Data]System.Data.Common.DbParameterCollection [System.Data]System.Data.Common.DbCommand::get_Parameters()
0xda980  callvirt instance int32 [System.Data]System.Data.Common.DbParameterCollection::get_Count()
0xda985  stloc.s  0xB
0xda987  ldc.i4.0
0xda988  stloc.s  0xC
0xda98a  br.s     loc_DA9C5
0xda98c  ldloc.s  4
0xda98e  callvirt instance class [System.Data]System.Data.Common.DbParameterCollection [System.Data]System.Data.Common.DbCommand::get_Parameters()
0xda993  ldloc.s  0xC
0xda995  callvirt instance class [System.Data]System.Data.Common.DbParameter [System.Data]System.Data.Common.DbParameterCollection::get_Item(int32)
0xda99a  stloc.s  0xD
0xda99c  ldloc.s  0xD
0xda99e  brfalse.s loc_DA9BF
0xda9a0  ldloc.s  0xD
0xda9a2  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0xda9a7  brtrue.s loc_DA9BF
0xda9a9  ldloc.s  0xD
0xda9ab  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.Common.DbParameter::get_Direction()
0xda9b0  ldc.i4.1
0xda9b1  beq.s    loc_DA9BD
0xda9b3  ldloc.s  0xD
0xda9b5  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.Common.DbParameter::get_Direction()
0xda9ba  ldc.i4.3
0xda9bb  bne.un.s loc_DA9BF
0xda9bd  ldnull
0xda9be  ret
0xda9bf  ldloc.s  0xC
0xda9c1  ldc.i4.1
0xda9c2  add
0xda9c3  stloc.s  0xC
0xda9c5  ldloc.s  0xC
0xda9c7  ldloc.s  0xB
0xda9c9  blt.s    loc_DA98C
0xda9cb  ldarg.0
0xda9cc  ldloc.s  4
0xda9ce  call     instance void System.Web.UI.WebControls.SqlDataSourceView::ReplaceNullValues(class [System.Data]System.Data.Common.DbCommand command)
0xda9d3  ldnull
0xda9d4  stloc.s  7
0xda9d6  ldarg.0
0xda9d7  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xda9dc  callvirt instance valuetype System.Web.UI.WebControls.SqlDataSourceMode System.Web.UI.WebControls.SqlDataSource::get_DataSourceMode()
0xda9e1  stloc.s  0xE
0xda9e3  ldloc.s  0xE
0xda9e5  brfalse  loc_DAB87
0xda9ea  ldloc.s  0xE
0xda9ec  ldc.i4.1
0xda9ed  bne.un   loc_DAC5A
0xda9f2  ldnull
0xda9f3  stloc.s  0xF
0xda9f5  ldloc.2
0xda9f6  brfalse.s loc_DAA57
0xda9f8  ldloc.1
0xda9f9  isinst   System.Web.UI.SqlDataSourceCache
0xda9fe  brfalse.s loc_DAA57
0xdaa00  ldloc.1
0xdaa01  castclass System.Web.UI.SqlDataSourceCache
0xdaa06  stloc.s  0x15
0xdaa08  ldloc.s  0x15
0xdaa0a  callvirt instance string System.Web.UI.SqlDataSourceCache::get_SqlCacheDependency()
0xdaa0f  ldstr    aCommandnotific// "CommandNotification"
0xdaa14  ldc.i4.5
0xdaa15  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xdaa1a  brfalse.s loc_DAA57
0xdaa1c  ldloc.s  4
0xdaa1e  isinst   [System.Data]System.Data.SqlClient.SqlCommand
0xdaa23  brtrue.s loc_DAA49
0xdaa25  ldstr    aSqldatasourcev_7// "SqlDataSourceView_CommandNotificationNo"...
0xdaa2a  ldc.i4.1
0xdaa2b  newarr   [mscorlib]System.Object
0xdaa30  dup
0xdaa31  ldc.i4.0
0xdaa32  ldarg.0
0xdaa33  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdaa38  callvirt instance string System.Web.UI.Control::get_ID()
0xdaa3d  stelem.ref
0xdaa3e  call     string System.Web.SR::GetString(string name, object[] args)
0xdaa43  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdaa48  throw
0xdaa49  ldloc.s  4
0xdaa4b  castclass [System.Data]System.Data.SqlClient.SqlCommand
0xdaa50  newobj   instance void System.Web.Caching.SqlCacheDependency::.ctor(class [System.Data]System.Data.SqlClient.SqlCommand sqlCmd)
0xdaa55  stloc.s  0xF
0xdaa57  ldarg.0
0xdaa58  ldfld    class System.Web.UI.WebControls.SqlDataSource System.Web.UI.WebControls.SqlDataSourceView::_owner
0xdaa5d  ldloc.s  4
0xdaa5f  callvirt instance class [System.Data]System.Data.Common.DbDataAdapter System.Web.UI.WebControls.SqlDataSource::CreateDataAdapter(class [System.Data]System.Data.Common.DbCommand command)
0xdaa64  stloc.s  0x10
0xdaa66  newobj   instance void [System.Data]System.Data.DataSet::.ctor()
0xdaa6b  stloc.s  0x11
0xdaa6d  ldc.i4.0
0xdaa6e  stloc.s  0x12
0xdaa70  ldc.i4.0
0xdaa71  stloc.s  0x13
0xdaa73  ldloc.s  0x10
0xdaa75  ldloc.s  0x11
0xdaa77  ldarg.0
0xdaa78  call     instance string System.Web.UI.DataSourceView::get_Name()
0xdaa7d  callvirt instance int32 [System.Data]System.Data.Common.DbDataAdapter::Fill(class [System.Data]System.Data.DataSet, string)
  ... truncated ...
```
