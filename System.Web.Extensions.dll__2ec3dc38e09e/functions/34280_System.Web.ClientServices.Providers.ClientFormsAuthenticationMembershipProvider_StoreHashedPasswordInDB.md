# System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::StoreHashedPasswordInDB

- ea: `0x34280`
- end: `0x34446`
- name: `System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::StoreHashedPasswordInDB`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x33e40`

## callees

- `0x34280`
- `0x34450`
- `0x37320`
- `0x37370`
- `0x37c80`
- `0x37ca0`
- `0x37dd0`
- `0x380e0`

## string_xrefs

- `0x3430b`: `DELETE FROM UserProperties WHERE PropertyName = @PasswordHashName`
- `0x3434a`: `DELETE FROM UserProperties WHERE PropertyName = @PasswordSaltName`

## pseudocode

```c

```

## disassembly

```asm
0x34280  ldarg.0
0x34281  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_SavePasswordHash
0x34286  brtrue.s loc_34289
0x34288  ret
0x34289  ldc.i4.s 0x10
0x3428b  newarr   [mscorlib]System.Byte
0x34290  stloc.0
0x34291  newobj   instance void [mscorlib]System.Security.Cryptography.RNGCryptoServiceProvider::.ctor()
0x34296  ldloc.0
0x34297  callvirt instance void [mscorlib]System.Security.Cryptography.RandomNumberGenerator::GetBytes(unsigned int8[])
0x3429c  ldloc.0
0x3429d  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x342a2  stloc.1
0x342a3  ldarg.2
0x342a4  ldloc.0
0x342a5  call     string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::EncodePassword(string password, unsigned int8[] salt)
0x342aa  stloc.2
0x342ab  ldarg.0
0x342ac  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingFileSystemStore
0x342b1  brtrue.s loc_342BB
0x342b3  ldarg.0
0x342b4  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingIsolatedStore
0x342b9  brfalse.s loc_342DD
0x342bb  ldarg.1
0x342bc  ldarg.0
0x342bd  ldfld    bool System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_UsingIsolatedStore
0x342c2  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x342c7  stloc.3
0x342c8  ldloc.3
0x342c9  ldloc.2
0x342ca  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_PasswordHash(string value)
0x342cf  ldloc.3
0x342d0  ldloc.1
0x342d1  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_PasswordSalt(string value)
0x342d6  ldloc.3
0x342d7  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x342dc  ret
0x342dd  ldarg.1
0x342de  ldarg.0
0x342df  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionString
0x342e4  ldarg.0
0x342e5  ldfld    string System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::_ConnectionStringProvider
0x342ea  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x342ef  stloc.s  4
0x342f1  ldnull
0x342f2  stloc.s  5
0x342f4  ldnull
0x342f5  stloc.s  6
0x342f7  ldloc.s  4
0x342f9  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x342fe  stloc.s  5
0x34300  ldloc.s  4
0x34302  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34307  stloc.s  6
0x34309  ldloc.s  6
0x3430b  ldstr    aDeleteFromUser// "DELETE FROM UserProperties WHERE Proper"...
0x34310  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34315  ldloc.s  4
0x34317  ldloc.s  6
0x34319  ldstr    aPasswordhashna// "@PasswordHashName"
0x3431e  ldstr    aPasswordhash// "PasswordHash_"
0x34323  ldarg.1
0x34324  call     string [mscorlib]System.String::Concat(string, string)
0x34329  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x3432e  ldloc.s  6
0x34330  ldloc.s  5
0x34332  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34337  ldloc.s  6
0x34339  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3433e  pop
0x3433f  ldloc.s  4
0x34341  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34346  stloc.s  6
0x34348  ldloc.s  6
0x3434a  ldstr    aDeleteFromUser_0// "DELETE FROM UserProperties WHERE Proper"...
0x3434f  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34354  ldloc.s  4
0x34356  ldloc.s  6
0x34358  ldstr    aPasswordsaltna// "@PasswordSaltName"
0x3435d  ldstr    aPasswordsalt// "PasswordSalt_"
0x34362  ldarg.1
0x34363  call     string [mscorlib]System.String::Concat(string, string)
0x34368  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x3436d  ldloc.s  6
0x3436f  ldloc.s  5
0x34371  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34376  ldloc.s  6
0x34378  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3437d  pop
0x3437e  ldloc.s  4
0x34380  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x34385  stloc.s  6
0x34387  ldloc.s  6
0x34389  ldstr    aInsertIntoUser// "INSERT INTO UserProperties(PropertyName"...
0x3438e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x34393  ldloc.s  4
0x34395  ldloc.s  6
0x34397  ldstr    aPasswordhashna// "@PasswordHashName"
0x3439c  ldstr    aPasswordhash// "PasswordHash_"
0x343a1  ldarg.1
0x343a2  call     string [mscorlib]System.String::Concat(string, string)
0x343a7  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x343ac  ldloc.s  4
0x343ae  ldloc.s  6
0x343b0  ldstr    aPasswordhashva// "@PasswordHashValue"
0x343b5  ldloc.2
0x343b6  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x343bb  ldloc.s  6
0x343bd  ldloc.s  5
0x343bf  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x343c4  ldloc.s  6
0x343c6  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x343cb  pop
0x343cc  ldloc.s  4
0x343ce  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x343d3  stloc.s  6
0x343d5  ldloc.s  6
0x343d7  ldstr    aInsertIntoUser_0// "INSERT INTO UserProperties(PropertyName"...
0x343dc  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x343e1  ldloc.s  4
0x343e3  ldloc.s  6
0x343e5  ldstr    aPasswordsaltna// "@PasswordSaltName"
0x343ea  ldstr    aPasswordsalt// "PasswordSalt_"
0x343ef  ldarg.1
0x343f0  call     string [mscorlib]System.String::Concat(string, string)
0x343f5  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x343fa  ldloc.s  4
0x343fc  ldloc.s  6
0x343fe  ldstr    aPasswordsaltva// "@PasswordSaltValue"
0x34403  ldloc.1
0x34404  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x34409  ldloc.s  6
0x3440b  ldloc.s  5
0x3440d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x34412  ldloc.s  6
0x34414  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x34419  pop
0x3441a  leave.s  loc_34445
0x3441c  pop
0x3441d  ldloc.s  5
0x3441f  brfalse.s loc_3442B
0x34421  ldloc.s  5
0x34423  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x34428  ldnull
0x34429  stloc.s  5
0x3442b  rethrow
0x3442d  ldloc.s  5
0x3442f  brfalse.s loc_34438
0x34431  ldloc.s  5
0x34433  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x34438  endfinally
0x34439  ldloc.s  4
0x3443b  brfalse.s loc_34444
0x3443d  ldloc.s  4
0x3443f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34444  endfinally
0x34445  ret
```
