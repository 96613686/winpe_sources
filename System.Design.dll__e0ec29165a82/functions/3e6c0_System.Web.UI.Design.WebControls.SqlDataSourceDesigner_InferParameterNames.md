# System.Web.UI.Design.WebControls.SqlDataSourceDesigner::InferParameterNames

- ea: `0x3e6c0`
- end: `0x3e869`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceDesigner::InferParameterNames`
- size: `425`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x3c1e0`
- `0x3eb40`
- `0x400b0`

## callees

- `0x3e040`
- `0x3e0b0`
- `0x3e4a0`
- `0x3e4d0`
- `0x3e570`
- `0x3e590`
- `0x3e6c0`
- `0x3ef20`
- `0x3f020`
- `0x52bb0`
- `0x52bf0`
- `0x584f0`
- `0x70ed0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x3e6e3`: `SqlDataSourceDesigner_NoCommand`
- `0x3e742`: `SqlDataSourceDesigner_CouldNotCreateConnection`
- `0x3e768`: `SqlDataSourceDesigner_CouldNotCreateConnection`

## pseudocode

```c

```

## disassembly

```asm
0x3e6c0  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x3e6c5  stloc.0
0x3e6c6  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x3e6cb  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x3e6d0  ldarg.2
0x3e6d1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3e6d6  brtrue.s loc_3E6F9
0x3e6d8  ldarg.0
0x3e6d9  call     instance class [System.Web]System.Web.UI.WebControls.SqlDataSource System.Web.UI.Design.WebControls.SqlDataSourceDesigner::get_SqlDataSource()
0x3e6de  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x3e6e3  ldstr    aSqldatasourced_8// "SqlDataSourceDesigner_NoCommand"
0x3e6e8  call     string System.Design.SR::GetString(string name)
0x3e6ed  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x3e6f2  ldnull
0x3e6f3  stloc.1
0x3e6f4  leave    loc_3E867
0x3e6f9  ldarg.3
0x3e6fa  brtrue.s loc_3E70E
0x3e6fc  ldarg.1
0x3e6fd  callvirt instance string System.ComponentModel.Design.Data.DesignerDataConnection::get_ProviderName()
0x3e702  ldarg.2
0x3e703  call     class [System.Web]System.Web.UI.WebControls.Parameter[] System.Web.UI.Design.WebControls.SqlDataSourceParameterParser::ParseCommandText(string providerName, string commandText)
0x3e708  stloc.1
0x3e709  leave    loc_3E867
0x3e70e  ldarg.1
0x3e70f  callvirt instance string System.ComponentModel.Design.Data.DesignerDataConnection::get_ProviderName()
0x3e714  call     class [System.Data]System.Data.Common.DbProviderFactory System.Web.UI.Design.WebControls.SqlDataSourceDesigner::GetDbProviderFactory(string providerName)
0x3e719  stloc.2
0x3e71a  ldnull
0x3e71b  stloc.3
0x3e71c  ldarg.0
0x3e71d  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x3e722  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x3e727  ldarg.1
0x3e728  call     class [System.Data]System.Data.Common.DbConnection System.Web.UI.Design.WebControls.SqlDataSourceDesigner::GetDesignTimeConnection(class [mscorlib]System.IServiceProvider serviceProvider, class System.ComponentModel.Design.Data.DesignerDataConnection connection)
0x3e72d  stloc.3
0x3e72e  leave.s  loc_3E75A
0x3e730  stloc.s  7
0x3e732  ldloc.3
0x3e733  brtrue.s loc_3E758
0x3e735  ldarg.0
0x3e736  call     instance class [System.Web]System.Web.UI.WebControls.SqlDataSource System.Web.UI.Design.WebControls.SqlDataSourceDesigner::get_SqlDataSource()
0x3e73b  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x3e740  ldloc.s  7
0x3e742  ldstr    aSqldatasourced_9// "SqlDataSourceDesigner_CouldNotCreateCon"...
0x3e747  call     string System.Design.SR::GetString(string name)
0x3e74c  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Exception ex, string message)
0x3e751  ldnull
0x3e752  stloc.1
0x3e753  leave    loc_3E867
0x3e758  leave.s  loc_3E75A
0x3e75a  ldloc.3
0x3e75b  brtrue.s loc_3E77E
0x3e75d  ldarg.0
0x3e75e  call     instance class [System.Web]System.Web.UI.WebControls.SqlDataSource System.Web.UI.Design.WebControls.SqlDataSourceDesigner::get_SqlDataSource()
0x3e763  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x3e768  ldstr    aSqldatasourced_9// "SqlDataSourceDesigner_CouldNotCreateCon"...
0x3e76d  call     string System.Design.SR::GetString(string name)
0x3e772  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x3e777  ldnull
0x3e778  stloc.1
0x3e779  leave    loc_3E867
0x3e77e  ldarg.0
0x3e77f  ldloc.2
0x3e780  ldloc.3
0x3e781  ldarg.2
0x3e782  ldnull
0x3e783  ldarg.3
0x3e784  call     instance class [System.Data]System.Data.Common.DbCommand System.Web.UI.Design.WebControls.SqlDataSourceDesigner::BuildSelectCommand(class [System.Data]System.Data.Common.DbProviderFactory factory, class [System.Data]System.Data.Common.DbConnection connection, string commandText, class [System.Web]System.Web.UI.WebControls.ParameterCollection parameters, valuetype [System.Web]System.Web.UI.WebControls.SqlDataSourceCommandType commandType)
0x3e789  stloc.s  4
0x3e78b  ldloc.s  4
0x3e78d  ldc.i4.4
0x3e78e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x3e793  ldarg.0
0x3e794  ldarg.1
0x3e795  callvirt instance string System.ComponentModel.Design.Data.DesignerDataConnection::get_ProviderName()
0x3e79a  ldloc.s  4
0x3e79c  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceDesigner::DeriveParameters(string providerName, class [System.Data]System.Data.Common.DbCommand command)
0x3e7a1  leave.s  loc_3E7EC
0x3e7a3  stloc.s  8
0x3e7a5  ldarg.0
0x3e7a6  call     instance class [System.Web]System.Web.UI.WebControls.SqlDataSource System.Web.UI.Design.WebControls.SqlDataSourceDesigner::get_SqlDataSource()
0x3e7ab  callvirt instance class [System]System.ComponentModel.ISite [System.Web]System.Web.UI.Control::get_Site()
0x3e7b0  ldstr    aSqldatasourced_10// "SqlDataSourceDesigner_InferStoredProced"...
0x3e7b5  ldc.i4.1
0x3e7b6  newarr   [mscorlib]System.Object
0x3e7bb  dup
0x3e7bc  ldc.i4.0
0x3e7bd  ldloc.s  8
0x3e7bf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3e7c4  stelem.ref
0x3e7c5  call     string System.Design.SR::GetString(string name, object[] args)
0x3e7ca  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x3e7cf  ldnull
0x3e7d0  stloc.1
0x3e7d1  leave    loc_3E867
0x3e7d6  ldloc.s  4
0x3e7d8  callvirt instance class [System.Data]System.Data.Common.DbConnection [System.Data]System.Data.Common.DbCommand::get_Connection()
0x3e7dd  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x3e7e2  ldc.i4.1
0x3e7e3  bne.un.s loc_3E7EB
0x3e7e5  ldloc.3
0x3e7e6  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x3e7eb  endfinally
0x3e7ec  ldloc.s  4
0x3e7ee  callvirt instance class [System.Data]System.Data.Common.DbParameterCollection [System.Data]System.Data.Common.DbCommand::get_Parameters()
0x3e7f3  callvirt instance int32 [System.Data]System.Data.Common.DbParameterCollection::get_Count()
0x3e7f8  stloc.s  5
0x3e7fa  ldloc.s  5
0x3e7fc  newarr   [System.Web]System.Web.UI.WebControls.Parameter
0x3e801  stloc.s  6
0x3e803  ldc.i4.0
0x3e804  stloc.s  9
0x3e806  br.s     loc_3E855
0x3e808  ldloc.s  4
0x3e80a  callvirt instance class [System.Data]System.Data.Common.DbParameterCollection [System.Data]System.Data.Common.DbCommand::get_Parameters()
0x3e80f  ldloc.s  9
0x3e811  callvirt instance class [System.Data]System.Data.Common.DbParameter [System.Data]System.Data.Common.DbParameterCollection::get_Item(int32)
0x3e816  stloc.s  0xA
0x3e818  ldloc.s  0xA
0x3e81a  brfalse.s loc_3E84F
0x3e81c  ldloc.s  0xA
0x3e81e  callvirt instance string [System.Data]System.Data.IDataParameter::get_ParameterName()
0x3e823  call     string System.Web.UI.Design.WebControls.SqlDataSourceDesigner::StripParameterPrefix(string parameterName)
0x3e828  stloc.s  0xB
0x3e82a  ldloc.s  6
0x3e82c  ldloc.s  9
0x3e82e  ldloc.2
0x3e82f  ldloc.s  0xB
0x3e831  ldloc.s  0xA
0x3e833  callvirt instance valuetype [System.Data]System.Data.DbType [System.Data]System.Data.IDataParameter::get_DbType()
0x3e838  call     class [System.Web]System.Web.UI.WebControls.Parameter System.Web.UI.Design.WebControls.SqlDataSourceDesigner::CreateParameter(class [System.Data]System.Data.Common.DbProviderFactory factory, string name, valuetype [System.Data]System.Data.DbType dbType)
0x3e83d  stelem.ref
0x3e83e  ldloc.s  6
0x3e840  ldloc.s  9
0x3e842  ldelem.ref
0x3e843  ldloc.s  0xA
0x3e845  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.IDataParameter::get_Direction()
0x3e84a  callvirt instance void [System.Web]System.Web.UI.WebControls.Parameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x3e84f  ldloc.s  9
0x3e851  ldc.i4.1
0x3e852  add
0x3e853  stloc.s  9
0x3e855  ldloc.s  9
0x3e857  ldloc.s  5
0x3e859  blt.s    loc_3E808
0x3e85b  ldloc.s  6
0x3e85d  stloc.1
0x3e85e  leave.s  loc_3E867
0x3e860  ldloc.0
0x3e861  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x3e866  endfinally
0x3e867  ldloc.1
0x3e868  ret
```
