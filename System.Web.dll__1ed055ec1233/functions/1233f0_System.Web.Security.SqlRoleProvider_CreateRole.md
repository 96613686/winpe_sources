# System.Web.Security.SqlRoleProvider::CreateRole

- ea: `0x1233f0`
- end: `0x1234f0`
- name: `System.Web.Security.SqlRoleProvider::CreateRole`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x34f20`
- `0x34fa0`
- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x58550`
- `0x122fb0`
- `0x123100`
- `0x1233f0`
- `0x124150`
- `0x124170`

## string_xrefs

- `0x12341f`: `dbo.aspnet_Roles_CreateRole`
- `0x1234b6`: `Provider_role_already_exists`

## pseudocode

```c

```

## disassembly

```asm
0x1233f0  ldarga.s 1
0x1233f2  ldc.i4.1
0x1233f3  ldc.i4.1
0x1233f4  ldc.i4.1
0x1233f5  ldc.i4   0x100
0x1233fa  ldstr    aRolename// "roleName"
0x1233ff  call     void System.Web.Util.SecUtility::CheckParameter(string& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123404  ldnull
0x123405  stloc.0
0x123406  ldarg.0
0x123407  ldfld    string System.Web.Security.SqlRoleProvider::_sqlConnectionString
0x12340c  ldc.i4.1
0x12340d  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x123412  stloc.0
0x123413  ldarg.0
0x123414  ldloc.0
0x123415  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x12341a  call     instance void System.Web.Security.SqlRoleProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x12341f  ldstr    aDboAspnetRoles// "dbo.aspnet_Roles_CreateRole"
0x123424  ldloc.0
0x123425  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x12342a  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x12342f  stloc.1
0x123430  ldloc.1
0x123431  ldc.i4.4
0x123432  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x123437  ldloc.1
0x123438  ldarg.0
0x123439  call     instance int32 System.Web.Security.SqlRoleProvider::get_CommandTimeout()
0x12343e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x123443  ldstr    aReturnvalue// "@ReturnValue"
0x123448  ldc.i4.8
0x123449  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x12344e  stloc.2
0x12344f  ldloc.2
0x123450  ldc.i4.6
0x123451  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x123456  ldloc.1
0x123457  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x12345c  ldloc.2
0x12345d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123462  pop
0x123463  ldloc.1
0x123464  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123469  ldarg.0
0x12346a  ldstr    aApplicationnam_0// "@ApplicationName"
0x12346f  ldc.i4.s 0xC
0x123471  ldarg.0
0x123472  callvirt instance string [System.Web.ApplicationServices]System.Web.Security.RoleProvider::get_ApplicationName()
0x123477  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x12347c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123481  pop
0x123482  ldloc.1
0x123483  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123488  ldarg.0
0x123489  ldstr    aRolename_0// "@RoleName"
0x12348e  ldc.i4.s 0xC
0x123490  ldarg.1
0x123491  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x123496  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x12349b  pop
0x12349c  ldloc.1
0x12349d  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x1234a2  pop
0x1234a3  ldarg.0
0x1234a4  ldloc.1
0x1234a5  call     instance int32 System.Web.Security.SqlRoleProvider::GetReturnValue(class [System.Data]System.Data.SqlClient.SqlCommand cmd)
0x1234aa  stloc.3
0x1234ab  ldloc.3
0x1234ac  brfalse.s loc_1234B4
0x1234ae  ldloc.3
0x1234af  ldc.i4.1
0x1234b0  beq.s    loc_1234B6
0x1234b2  br.s     loc_1234D0
0x1234b4  leave.s  loc_1234EF
0x1234b6  ldstr    aProviderRoleAl// "Provider_role_already_exists"
0x1234bb  ldc.i4.1
0x1234bc  newarr   [mscorlib]System.Object
0x1234c1  dup
0x1234c2  ldc.i4.0
0x1234c3  ldarg.1
0x1234c4  stelem.ref
0x1234c5  call     string System.Web.SR::GetString(string name, object[] args)
0x1234ca  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1234cf  throw
0x1234d0  ldstr    aProviderUnknow// "Provider_unknown_failure"
0x1234d5  call     string System.Web.SR::GetString(string name)
0x1234da  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1234df  throw
0x1234e0  ldloc.0
0x1234e1  brfalse.s loc_1234EB
0x1234e3  ldloc.0
0x1234e4  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x1234e9  ldnull
0x1234ea  stloc.0
0x1234eb  endfinally
0x1234ec  pop
0x1234ed  rethrow
0x1234ef  ret
```
