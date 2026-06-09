# System.Web.ClientServices.Providers.SqlHelper::DeleteAllCookies

- ea: `0x37540`
- end: `0x375c3`
- name: `System.Web.ClientServices.Providers.SqlHelper::DeleteAllCookies`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x33c90`
- `0x33e40`

## callees

- `0x37320`
- `0x37540`
- `0x382a0`

## string_xrefs

- `0x37586`: `DELETE FROM UserProperties WHERE PropertyName LIKE N'CookieName_%'`

## pseudocode

```c

```

## disassembly

```asm
0x37540  ldarg.1
0x37541  ldstr    aFiles// "|FILES|"
0x37546  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3754b  brtrue.s loc_3755A
0x3754d  ldarg.1
0x3754e  ldstr    aIsolatedStorag// "|Isolated_Storage|"
0x37553  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37558  brfalse.s loc_3756C
0x3755a  ldarg.0
0x3755b  ldarg.1
0x3755c  ldstr    aIsolatedStorag// "|Isolated_Storage|"
0x37561  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37566  call     void System.Web.ClientServices.Providers.ClientDataManager::DeleteAllCookies(string username, bool useIsolatedStore)
0x3756b  ret
0x3756c  ldarg.0
0x3756d  ldarg.1
0x3756e  ldarg.2
0x3756f  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x37574  stloc.0
0x37575  ldnull
0x37576  stloc.1
0x37577  ldloc.0
0x37578  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x3757d  stloc.1
0x3757e  ldloc.0
0x3757f  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x37584  stloc.2
0x37585  ldloc.2
0x37586  ldstr    aDeleteFromUser_3// "DELETE FROM UserProperties WHERE Proper"...
0x3758b  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x37590  ldloc.2
0x37591  ldloc.1
0x37592  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x37597  ldloc.2
0x37598  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3759d  pop
0x3759e  leave.s  loc_375C2
0x375a0  pop
0x375a1  ldloc.1
0x375a2  brfalse.s loc_375AC
0x375a4  ldloc.1
0x375a5  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x375aa  ldnull
0x375ab  stloc.1
0x375ac  rethrow
0x375ae  ldloc.1
0x375af  brfalse.s loc_375B7
0x375b1  ldloc.1
0x375b2  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x375b7  endfinally
0x375b8  ldloc.0
0x375b9  brfalse.s loc_375C1
0x375bb  ldloc.0
0x375bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x375c1  endfinally
0x375c2  ret
```
