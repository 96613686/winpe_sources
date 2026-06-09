# System.Web.ClientServices.Providers.SqlHelper::StoreCookieInDB

- ea: `0x37420`
- end: `0x3753c`
- name: `System.Web.ClientServices.Providers.SqlHelper::StoreCookieInDB`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x37180`

## callees

- `0x37320`
- `0x37370`
- `0x37420`
- `0x38170`

## string_xrefs

- `0x3747e`: `DELETE FROM UserProperties WHERE PropertyName LIKE N'CookieName_%' AND PropertyValue LIKE @PropValue`

## pseudocode

```c

```

## disassembly

```asm
0x37420  ldarg.3
0x37421  ldstr    aFiles// "|FILES|"
0x37426  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3742b  brfalse.s loc_37437
0x3742d  ldarg.2
0x3742e  ldarg.0
0x3742f  ldarg.1
0x37430  ldc.i4.0
0x37431  call     string System.Web.ClientServices.Providers.ClientDataManager::StoreCookie(string username, string cookieName, string cookieValue, bool useIsolatedStore)
0x37436  ret
0x37437  ldarg.3
0x37438  ldstr    aIsolatedStorag// "|Isolated_Storage|"
0x3743d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37442  brfalse.s loc_3744E
0x37444  ldarg.2
0x37445  ldarg.0
0x37446  ldarg.1
0x37447  ldc.i4.1
0x37448  call     string System.Web.ClientServices.Providers.ClientDataManager::StoreCookie(string username, string cookieName, string cookieValue, bool useIsolatedStore)
0x3744d  ret
0x3744e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x37453  stloc.1
0x37454  ldloca.s 1
0x37456  ldstr    aN// "N"
0x3745b  call     instance string [mscorlib]System.Guid::ToString(string)
0x37460  stloc.0
0x37461  ldarg.2
0x37462  ldarg.3
0x37463  ldarg.s  4
0x37465  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x3746a  stloc.2
0x3746b  ldnull
0x3746c  stloc.3
0x3746d  ldloc.2
0x3746e  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x37473  stloc.3
0x37474  ldloc.2
0x37475  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x3747a  stloc.s  4
0x3747c  ldloc.s  4
0x3747e  ldstr    aDeleteFromUser_2// "DELETE FROM UserProperties WHERE Proper"...
0x37483  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x37488  ldloc.s  4
0x3748a  ldloc.3
0x3748b  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x37490  ldloc.2
0x37491  ldloc.s  4
0x37493  ldstr    aPropvalue// "@PropValue"
0x37498  ldarg.0
0x37499  ldstr    asc_4E31A// "=%"
0x3749e  call     string [mscorlib]System.String::Concat(string, string)
0x374a3  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x374a8  ldloc.s  4
0x374aa  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x374af  pop
0x374b0  ldarg.1
0x374b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x374b6  brtrue.s loc_37512
0x374b8  ldloc.2
0x374b9  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x374be  stloc.s  4
0x374c0  ldloc.s  4
0x374c2  ldloc.3
0x374c3  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x374c8  ldloc.s  4
0x374ca  ldstr    aInsertIntoUser_2// "INSERT INTO UserProperties (PropertyNam"...
0x374cf  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x374d4  ldloc.2
0x374d5  ldloc.s  4
0x374d7  ldstr    aPropname// "@PropName"
0x374dc  ldstr    aCookiename// "CookieName_"
0x374e1  ldloc.0
0x374e2  call     string [mscorlib]System.String::Concat(string, string)
0x374e7  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x374ec  ldloc.2
0x374ed  ldloc.s  4
0x374ef  ldstr    aPropvalue// "@PropValue"
0x374f4  ldarg.0
0x374f5  ldstr    asc_3F82A// "="
0x374fa  ldarg.1
0x374fb  call     string [mscorlib]System.String::Concat(string, string, string)
0x37500  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x37505  ldloc.s  4
0x37507  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3750c  pop
0x3750d  ldloc.0
0x3750e  stloc.s  5
0x37510  leave.s  loc_37539
0x37512  ldarg.0
0x37513  stloc.s  5
0x37515  leave.s  loc_37539
0x37517  pop
0x37518  ldloc.3
0x37519  brfalse.s loc_37523
0x3751b  ldloc.3
0x3751c  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x37521  ldnull
0x37522  stloc.3
0x37523  rethrow
0x37525  ldloc.3
0x37526  brfalse.s loc_3752E
0x37528  ldloc.3
0x37529  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x3752e  endfinally
0x3752f  ldloc.2
0x37530  brfalse.s loc_37538
0x37532  ldloc.2
0x37533  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37538  endfinally
0x37539  ldloc.s  5
0x3753b  ret
```
