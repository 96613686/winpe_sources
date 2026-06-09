# System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::StoreLastUserNameInOffileStore

- ea: `0x340f0`
- end: `0x3420a`
- name: `System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::StoreLastUserNameInOffileStore`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x33c90`
- `0x33e40`

## callees

- `0x340f0`
- `0x37320`
- `0x37370`
- `0x37c40`
- `0x37c60`
- `0x37dd0`
- `0x380c0`

## string_xrefs

- `0x34150`: `DELETE FROM ApplicationProperties WHERE PropertyName = N'LastLoggedInUserName'`

## pseudocode

```c

```

## disassembly

```asm
0x340f0  ldarg.0
0x340f1  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingFileSystemStore
0x340f6  brtrue.s loc_34100
0x340f8  ldarg.0
0x340f9  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingIsolatedStore
0x340fe  brfalse.s loc_34125
0x34100  ldarg.0
0x34101  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingIsolatedStore
0x34106  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetAppClientData(bool useIsolatedStore)
0x3410b  stloc.0
0x3410c  ldloc.0
0x3410d  ldarg.1
0x3410e  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_LastLoggedInUserName(string value)
0x34113  ldloc.0
0x34114  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34119  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_LastLoggedInDateUtc(valuetype [mscorlib]System.DateTime value)
0x3411e  ldloc.0
0x3411f  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x34124  ret
0x34125  ldnull
0x34126  ldarg.0
0x34127  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x3412c  ldarg.0
0x3412d  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionStringProvider
0x34132  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x34137  stloc.1
0x34138  ldnull
0x34139  stloc.2
0x3413a  ldloc.1
0x3413b  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x34140  stloc.2
0x34141  ldloc.1
0x34142  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34147  stloc.3
0x34148  ldloc.3
0x34149  ldloc.2
0x3414a  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x3414f  ldloc.3
0x34150  ldstr    aDeleteFromAppl// "DELETE FROM ApplicationProperties WHERE"...
0x34155  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x3415a  ldloc.3
0x3415b  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34160  pop
0x34161  ldarg.1
0x34162  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34167  brtrue.s loc_341E5
0x34169  ldloc.1
0x3416a  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x3416f  stloc.3
0x34170  ldloc.3
0x34171  ldloc.2
0x34172  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34177  ldloc.3
0x34178  ldstr    aInsertIntoAppl// "INSERT INTO ApplicationProperties(Prope"...
0x3417d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34182  ldloc.1
0x34183  ldloc.3
0x34184  ldstr    aUsername_0// "@UserName"
0x34189  ldarg.1
0x3418a  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x3418f  ldloc.3
0x34190  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34195  pop
0x34196  ldloc.1
0x34197  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x3419c  stloc.3
0x3419d  ldloc.3
0x3419e  ldloc.2
0x3419f  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x341a4  ldloc.3
0x341a5  ldstr    aInsertIntoAppl_0// "INSERT INTO ApplicationProperties(Prope"...
0x341aa  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x341af  ldloc.1
0x341b0  ldloc.3
0x341b1  ldstr    aDate_1// "@Date"
0x341b6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x341bb  stloc.s  4
0x341bd  ldloca.s 4
0x341bf  call     instance int64 [mscorlib]System.DateTime::ToFileTimeUtc()
0x341c4  stloc.s  5
0x341c6  ldloca.s 5
0x341c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x341cd  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x341d2  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x341d7  ldloc.3
0x341d8  ldloc.2
0x341d9  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x341de  ldloc.3
0x341df  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x341e4  pop
0x341e5  leave.s  loc_34209
0x341e7  pop
0x341e8  ldloc.2
0x341e9  brfalse.s loc_341F3
0x341eb  ldloc.2
0x341ec  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x341f1  ldnull
0x341f2  stloc.2
0x341f3  rethrow
0x341f5  ldloc.2
0x341f6  brfalse.s loc_341FE
0x341f8  ldloc.2
0x341f9  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x341fe  endfinally
0x341ff  ldloc.1
0x34200  brfalse.s loc_34208
0x34202  ldloc.1
0x34203  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34208  endfinally
0x34209  ret
```
