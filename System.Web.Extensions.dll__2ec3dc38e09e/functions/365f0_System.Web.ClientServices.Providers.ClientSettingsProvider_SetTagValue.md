# System.Web.ClientServices.Providers.ClientSettingsProvider::SetTagValue

- ea: `0x365f0`
- end: `0x3667c`
- name: `System.Web.ClientServices.Providers.ClientSettingsProvider::SetTagValue`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x36480`
- `0x36530`

## callees

- `0x365f0`
- `0x36800`
- `0x37320`
- `0x37370`

## string_xrefs

- `0x3661b`: `DELETE FROM Settings WHERE PropertyName = @PropName AND PropertyStoredAs='I'`

## pseudocode

```c

```

## disassembly

```asm
0x365f0  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x365f5  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x365fa  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x365ff  stloc.0
0x36600  ldloc.0
0x36601  ldarg.0
0x36602  call     instance string System.Web.ClientServices.Providers.ClientSettingsProvider::GetConnectionString()
0x36607  ldarg.0
0x36608  ldfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionStringProvider
0x3660d  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x36612  stloc.1
0x36613  ldloc.1
0x36614  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x36619  stloc.2
0x3661a  ldloc.2
0x3661b  ldstr    aDeleteFromSett_0// "DELETE FROM Settings WHERE PropertyName"...
0x36620  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x36625  ldloc.1
0x36626  ldloc.2
0x36627  ldstr    aPropname// "@PropName"
0x3662c  ldarg.1
0x3662d  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x36632  ldloc.2
0x36633  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x36638  pop
0x36639  ldarg.2
0x3663a  brfalse.s loc_3666F
0x3663c  ldloc.1
0x3663d  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x36642  stloc.2
0x36643  ldloc.2
0x36644  ldstr    aInsertIntoSett_2// "INSERT INTO Settings (PropertyName, Pro"...
0x36649  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x3664e  ldloc.1
0x3664f  ldloc.2
0x36650  ldstr    aPropname// "@PropName"
0x36655  ldarg.1
0x36656  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x3665b  ldloc.1
0x3665c  ldloc.2
0x3665d  ldstr    aPropvalue// "@PropValue"
0x36662  ldarg.2
0x36663  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x36668  ldloc.2
0x36669  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3666e  pop
0x3666f  leave.s  loc_3667B
0x36671  ldloc.1
0x36672  brfalse.s loc_3667A
0x36674  ldloc.1
0x36675  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3667a  endfinally
0x3667b  ret
```
