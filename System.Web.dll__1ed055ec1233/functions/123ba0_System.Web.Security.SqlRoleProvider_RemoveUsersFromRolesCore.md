# System.Web.Security.SqlRoleProvider::RemoveUsersFromRolesCore

- ea: `0x123ba0`
- end: `0x123d07`
- name: `System.Web.Security.SqlRoleProvider::RemoveUsersFromRolesCore`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x123a10`

## callees

- `0x34f20`
- `0x34fa0`
- `0x122fb0`
- `0x123ba0`
- `0x124150`
- `0x124170`

## string_xrefs

- `0x123ba0`: `dbo.aspnet_UsersInRoles_RemoveUsersFromRoles`
- `0x123cd8`: `Provider_this_user_already_not_in_role`

## pseudocode

```c

```

## disassembly

```asm
0x123ba0  ldstr    aDboAspnetUsers_3// "dbo.aspnet_UsersInRoles_RemoveUsersFrom"...
0x123ba5  ldarg.1
0x123ba6  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x123bab  stloc.0
0x123bac  ldnull
0x123bad  stloc.1
0x123bae  ldstr    aReturnvalue// "@ReturnValue"
0x123bb3  ldc.i4.8
0x123bb4  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x123bb9  stloc.2
0x123bba  ldsfld   string [mscorlib]System.String::Empty
0x123bbf  stloc.3
0x123bc0  ldsfld   string [mscorlib]System.String::Empty
0x123bc5  stloc.s  4
0x123bc7  ldloc.0
0x123bc8  ldc.i4.4
0x123bc9  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x123bce  ldloc.0
0x123bcf  ldarg.0
0x123bd0  call     instance int32 System.Web.Security.SqlRoleProvider::get_CommandTimeout()
0x123bd5  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x123bda  ldloc.2
0x123bdb  ldc.i4.6
0x123bdc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x123be1  ldloc.0
0x123be2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123be7  ldloc.2
0x123be8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123bed  pop
0x123bee  ldloc.0
0x123bef  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123bf4  ldarg.0
0x123bf5  ldstr    aApplicationnam_0// "@ApplicationName"
0x123bfa  ldc.i4.s 0xC
0x123bfc  ldarg.0
0x123bfd  callvirt instance string [System.Web.ApplicationServices]System.Web.Security.RoleProvider::get_ApplicationName()
0x123c02  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x123c07  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123c0c  pop
0x123c0d  ldloc.0
0x123c0e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123c13  ldarg.0
0x123c14  ldstr    aUsernames_0// "@UserNames"
0x123c19  ldc.i4.s 0xC
0x123c1b  ldarg.2
0x123c1c  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x123c21  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123c26  pop
0x123c27  ldloc.0
0x123c28  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123c2d  ldarg.0
0x123c2e  ldstr    aRolenames_0// "@RoleNames"
0x123c33  ldc.i4.s 0xC
0x123c35  ldarg.3
0x123c36  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x123c3b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123c40  pop
0x123c41  ldloc.0
0x123c42  ldc.i4.8
0x123c43  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader [System.Data]System.Data.SqlClient.SqlCommand::ExecuteReader(valuetype [System.Data]System.Data.CommandBehavior)
0x123c48  stloc.1
0x123c49  ldloc.1
0x123c4a  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x123c4f  brfalse.s loc_123C74
0x123c51  ldloc.1
0x123c52  callvirt instance int32 [System.Data]System.Data.Common.DbDataReader::get_FieldCount()
0x123c57  ldc.i4.0
0x123c58  ble.s    loc_123C62
0x123c5a  ldloc.1
0x123c5b  ldc.i4.0
0x123c5c  callvirt instance string [System.Data]System.Data.Common.DbDataReader::GetString(int32)
0x123c61  stloc.3
0x123c62  ldloc.1
0x123c63  callvirt instance int32 [System.Data]System.Data.Common.DbDataReader::get_FieldCount()
0x123c68  ldc.i4.1
0x123c69  ble.s    loc_123C74
0x123c6b  ldloc.1
0x123c6c  ldc.i4.1
0x123c6d  callvirt instance string [System.Data]System.Data.Common.DbDataReader::GetString(int32)
0x123c72  stloc.s  4
0x123c74  leave.s  loc_123C80
0x123c76  ldloc.1
0x123c77  brfalse.s loc_123C7F
0x123c79  ldloc.1
0x123c7a  callvirt instance void [System.Data]System.Data.Common.DbDataReader::Close()
0x123c7f  endfinally
0x123c80  ldarg.0
0x123c81  ldloc.0
0x123c82  call     instance int32 System.Web.Security.SqlRoleProvider::GetReturnValue(class [System.Data]System.Data.SqlClient.SqlCommand cmd)
0x123c87  stloc.s  5
0x123c89  ldloc.s  5
0x123c8b  switch   loc_123CA2, loc_123CA3, loc_123CBD, loc_123CD8
0x123ca0  br.s     loc_123CF7
0x123ca2  ret
0x123ca3  ldstr    aProviderThisUs// "Provider_this_user_not_found"
0x123ca8  ldc.i4.1
0x123ca9  newarr   [mscorlib]System.Object
0x123cae  dup
0x123caf  ldc.i4.0
0x123cb0  ldloc.3
0x123cb1  stelem.ref
0x123cb2  call     string System.Web.SR::GetString(string name, object[] args)
0x123cb7  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x123cbc  throw
0x123cbd  ldstr    aProviderRoleNo// "Provider_role_not_found"
0x123cc2  ldc.i4.1
0x123cc3  newarr   [mscorlib]System.Object
0x123cc8  dup
0x123cc9  ldc.i4.0
0x123cca  ldloc.s  4
0x123ccc  stelem.ref
0x123ccd  call     string System.Web.SR::GetString(string name, object[] args)
0x123cd2  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x123cd7  throw
0x123cd8  ldstr    aProviderThisUs_1// "Provider_this_user_already_not_in_role"
0x123cdd  ldc.i4.2
0x123cde  newarr   [mscorlib]System.Object
0x123ce3  dup
0x123ce4  ldc.i4.0
0x123ce5  ldloc.3
0x123ce6  stelem.ref
0x123ce7  dup
0x123ce8  ldc.i4.1
0x123ce9  ldloc.s  4
0x123ceb  stelem.ref
0x123cec  call     string System.Web.SR::GetString(string name, object[] args)
0x123cf1  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x123cf6  throw
0x123cf7  ldstr    aProviderUnknow// "Provider_unknown_failure"
0x123cfc  call     string System.Web.SR::GetString(string name)
0x123d01  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x123d06  throw
```
