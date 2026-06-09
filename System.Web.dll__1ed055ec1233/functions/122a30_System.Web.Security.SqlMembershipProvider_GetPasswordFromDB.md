# System.Web.Security.SqlMembershipProvider::GetPasswordFromDB

- ea: `0x122a30`
- end: `0x122bc0`
- name: `System.Web.Security.SqlMembershipProvider::GetPasswordFromDB`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x120d50`

## callees

- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x1206a0`
- `0x1206d0`
- `0x122a30`
- `0x122c40`

## string_xrefs

- `0x122ab3`: `@MaxInvalidPasswordAttempts`
- `0x122ad6`: `@PasswordAttemptWindow`

## pseudocode

```c

```

## disassembly

```asm
0x122a30  ldnull
0x122a31  stloc.0
0x122a32  ldnull
0x122a33  stloc.1
0x122a34  ldnull
0x122a35  stloc.2
0x122a36  ldarg.0
0x122a37  ldfld    string System.Web.Security.SqlMembershipProvider::_sqlConnectionString
0x122a3c  ldc.i4.1
0x122a3d  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x122a42  stloc.0
0x122a43  ldarg.0
0x122a44  ldloc.0
0x122a45  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x122a4a  call     instance void System.Web.Security.SqlMembershipProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x122a4f  ldstr    aDboAspnetMembe_14// "dbo.aspnet_Membership_GetPassword"
0x122a54  ldloc.0
0x122a55  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x122a5a  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x122a5f  stloc.3
0x122a60  ldloc.3
0x122a61  ldarg.0
0x122a62  call     instance int32 System.Web.Security.SqlMembershipProvider::get_CommandTimeout()
0x122a67  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x122a6c  ldloc.3
0x122a6d  ldc.i4.4
0x122a6e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x122a73  ldloc.3
0x122a74  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122a79  ldarg.0
0x122a7a  ldstr    aApplicationnam_0// "@ApplicationName"
0x122a7f  ldc.i4.s 0xC
0x122a81  ldarg.0
0x122a82  callvirt instance string [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_ApplicationName()
0x122a87  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122a8c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122a91  pop
0x122a92  ldloc.3
0x122a93  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122a98  ldarg.0
0x122a99  ldstr    aUsername_1// "@UserName"
0x122a9e  ldc.i4.s 0xC
0x122aa0  ldarg.1
0x122aa1  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122aa6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122aab  pop
0x122aac  ldloc.3
0x122aad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122ab2  ldarg.0
0x122ab3  ldstr    aMaxinvalidpass_0// "@MaxInvalidPasswordAttempts"
0x122ab8  ldc.i4.8
0x122ab9  ldarg.0
0x122aba  callvirt instance int32 [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_MaxInvalidPasswordAttempts()
0x122abf  box      [mscorlib]System.Int32
0x122ac4  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122ac9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122ace  pop
0x122acf  ldloc.3
0x122ad0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122ad5  ldarg.0
0x122ad6  ldstr    aPasswordattemp_0// "@PasswordAttemptWindow"
0x122adb  ldc.i4.8
0x122adc  ldarg.0
0x122add  callvirt instance int32 [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_PasswordAttemptWindow()
0x122ae2  box      [mscorlib]System.Int32
0x122ae7  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122aec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122af1  pop
0x122af2  ldloc.3
0x122af3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122af8  ldarg.0
0x122af9  ldstr    aCurrenttimeutc// "@CurrentTimeUtc"
0x122afe  ldc.i4.4
0x122aff  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x122b04  box      [mscorlib]System.DateTime
0x122b09  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122b0e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122b13  pop
0x122b14  ldarg.3
0x122b15  brfalse.s loc_122B31
0x122b17  ldloc.3
0x122b18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122b1d  ldarg.0
0x122b1e  ldstr    aPasswordanswer_1// "@PasswordAnswer"
0x122b23  ldc.i4.s 0xC
0x122b25  ldarg.2
0x122b26  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x122b2b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122b30  pop
0x122b31  ldstr    aReturnvalue// "@ReturnValue"
0x122b36  ldc.i4.8
0x122b37  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x122b3c  stloc.2
0x122b3d  ldloc.2
0x122b3e  ldc.i4.6
0x122b3f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x122b44  ldloc.3
0x122b45  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x122b4a  ldloc.2
0x122b4b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x122b50  pop
0x122b51  ldloc.3
0x122b52  ldc.i4.8
0x122b53  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader [System.Data]System.Data.SqlClient.SqlCommand::ExecuteReader(valuetype [System.Data]System.Data.CommandBehavior)
0x122b58  stloc.1
0x122b59  ldnull
0x122b5a  stloc.s  4
0x122b5c  ldarg.s  5
0x122b5e  ldc.i4.m1
0x122b5f  stind.i4
0x122b60  ldloc.1
0x122b61  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x122b66  brfalse.s loc_122B7D
0x122b68  ldloc.1
0x122b69  ldc.i4.0
0x122b6a  callvirt instance string [System.Data]System.Data.Common.DbDataReader::GetString(int32)
0x122b6f  stloc.s  4
0x122b71  ldarg.s  4
0x122b73  ldloc.1
0x122b74  ldc.i4.1
0x122b75  callvirt instance int32 [System.Data]System.Data.Common.DbDataReader::GetInt32(int32)
0x122b7a  stind.i4
0x122b7b  br.s     loc_122B84
0x122b7d  ldnull
0x122b7e  stloc.s  4
0x122b80  ldarg.s  4
0x122b82  ldc.i4.0
0x122b83  stind.i4
0x122b84  ldloc.s  4
0x122b86  stloc.s  5
0x122b88  leave.s  loc_122BBD
0x122b8a  ldloc.1
0x122b8b  brfalse.s loc_122BAE
0x122b8d  ldloc.1
0x122b8e  callvirt instance void [System.Data]System.Data.Common.DbDataReader::Close()
0x122b93  ldnull
0x122b94  stloc.1
0x122b95  ldarg.s  5
0x122b97  ldloc.2
0x122b98  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x122b9d  brtrue.s loc_122BA2
0x122b9f  ldc.i4.m1
0x122ba0  br.s     loc_122BAD
0x122ba2  ldloc.2
0x122ba3  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x122ba8  unbox.any [mscorlib]System.Int32
0x122bad  stind.i4
0x122bae  ldloc.0
0x122baf  brfalse.s loc_122BB9
0x122bb1  ldloc.0
0x122bb2  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x122bb7  ldnull
0x122bb8  stloc.0
0x122bb9  endfinally
0x122bba  pop
0x122bbb  rethrow
0x122bbd  ldloc.s  5
0x122bbf  ret
```
