# System.Web.Security.SqlMembershipProvider::DeleteUser

- ea: `0x121c80`
- end: `0x121da6`
- name: `System.Web.Security.SqlMembershipProvider::DeleteUser`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x58550`
- `0x1206a0`
- `0x1206d0`
- `0x121c80`
- `0x122c40`

## string_xrefs

- `0x121caf`: `dbo.aspnet_Users_DeleteUser`
- `0x121d16`: `@TablesToDeleteFrom`
- `0x121d37`: `@TablesToDeleteFrom`
- `0x121d4e`: `@NumTablesDeletedFrom`

## pseudocode

```c

```

## disassembly

```asm
0x121c80  ldarga.s 1
0x121c82  ldc.i4.1
0x121c83  ldc.i4.1
0x121c84  ldc.i4.1
0x121c85  ldc.i4   0x100
0x121c8a  ldstr    aUsername_0// "username"
0x121c8f  call     void System.Web.Util.SecUtility::CheckParameter(string& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x121c94  ldnull
0x121c95  stloc.0
0x121c96  ldarg.0
0x121c97  ldfld    string System.Web.Security.SqlMembershipProvider::_sqlConnectionString
0x121c9c  ldc.i4.1
0x121c9d  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x121ca2  stloc.0
0x121ca3  ldarg.0
0x121ca4  ldloc.0
0x121ca5  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x121caa  call     instance void System.Web.Security.SqlMembershipProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x121caf  ldstr    aDboAspnetUsers// "dbo.aspnet_Users_DeleteUser"
0x121cb4  ldloc.0
0x121cb5  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x121cba  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x121cbf  stloc.1
0x121cc0  ldloc.1
0x121cc1  ldarg.0
0x121cc2  call     instance int32 System.Web.Security.SqlMembershipProvider::get_CommandTimeout()
0x121cc7  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x121ccc  ldloc.1
0x121ccd  ldc.i4.4
0x121cce  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x121cd3  ldloc.1
0x121cd4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x121cd9  ldarg.0
0x121cda  ldstr    aApplicationnam_0// "@ApplicationName"
0x121cdf  ldc.i4.s 0xC
0x121ce1  ldarg.0
0x121ce2  callvirt instance string [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_ApplicationName()
0x121ce7  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x121cec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x121cf1  pop
0x121cf2  ldloc.1
0x121cf3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x121cf8  ldarg.0
0x121cf9  ldstr    aUsername_1// "@UserName"
0x121cfe  ldc.i4.s 0xC
0x121d00  ldarg.1
0x121d01  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x121d06  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x121d0b  pop
0x121d0c  ldarg.2
0x121d0d  brfalse.s loc_121D30
0x121d0f  ldloc.1
0x121d10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x121d15  ldarg.0
0x121d16  ldstr    aTablestodelete// "@TablesToDeleteFrom"
0x121d1b  ldc.i4.8
0x121d1c  ldc.i4.s 0xF
0x121d1e  box      [mscorlib]System.Int32
0x121d23  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x121d28  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x121d2d  pop
0x121d2e  br.s     loc_121D4E
0x121d30  ldloc.1
0x121d31  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x121d36  ldarg.0
0x121d37  ldstr    aTablestodelete// "@TablesToDeleteFrom"
0x121d3c  ldc.i4.8
0x121d3d  ldc.i4.1
0x121d3e  box      [mscorlib]System.Int32
0x121d43  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlMembershipProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x121d48  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x121d4d  pop
0x121d4e  ldstr    aNumtablesdelet// "@NumTablesDeletedFrom"
0x121d53  ldc.i4.8
0x121d54  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x121d59  stloc.2
0x121d5a  ldloc.2
0x121d5b  ldc.i4.2
0x121d5c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x121d61  ldloc.1
0x121d62  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x121d67  ldloc.2
0x121d68  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x121d6d  pop
0x121d6e  ldloc.1
0x121d6f  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x121d74  pop
0x121d75  ldloc.2
0x121d76  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x121d7b  brtrue.s loc_121D80
0x121d7d  ldc.i4.m1
0x121d7e  br.s     loc_121D8B
0x121d80  ldloc.2
0x121d81  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x121d86  unbox.any [mscorlib]System.Int32
0x121d8b  stloc.3
0x121d8c  ldloc.3
0x121d8d  ldc.i4.0
0x121d8e  cgt
0x121d90  stloc.s  4
0x121d92  leave.s  loc_121DA3
0x121d94  ldloc.0
0x121d95  brfalse.s loc_121D9F
0x121d97  ldloc.0
0x121d98  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x121d9d  ldnull
0x121d9e  stloc.0
0x121d9f  endfinally
0x121da0  pop
0x121da1  rethrow
0x121da3  ldloc.s  4
0x121da5  ret
```
