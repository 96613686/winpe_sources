# System.Web.Security.SqlRoleProvider::DeleteRole

- ea: `0x1234f0`
- end: `0x1235fd`
- name: `System.Web.Security.SqlRoleProvider::DeleteRole`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x34fa0`
- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x58550`
- `0x122fb0`
- `0x123100`
- `0x1234f0`
- `0x124150`
- `0x124170`

## string_xrefs

- `0x12351f`: `dbo.aspnet_Roles_DeleteRole`
- `0x1235a3`: `@DeleteOnlyIfRoleIsEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x1234f0  ldarga.s 1
0x1234f2  ldc.i4.1
0x1234f3  ldc.i4.1
0x1234f4  ldc.i4.1
0x1234f5  ldc.i4   0x100
0x1234fa  ldstr    aRolename// "roleName"
0x1234ff  call     void System.Web.Util.SecUtility::CheckParameter(string& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123504  ldnull
0x123505  stloc.0
0x123506  ldarg.0
0x123507  ldfld    string System.Web.Security.SqlRoleProvider::_sqlConnectionString
0x12350c  ldc.i4.1
0x12350d  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x123512  stloc.0
0x123513  ldarg.0
0x123514  ldloc.0
0x123515  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x12351a  call     instance void System.Web.Security.SqlRoleProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x12351f  ldstr    aDboAspnetRoles_0// "dbo.aspnet_Roles_DeleteRole"
0x123524  ldloc.0
0x123525  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x12352a  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x12352f  stloc.1
0x123530  ldloc.1
0x123531  ldc.i4.4
0x123532  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x123537  ldloc.1
0x123538  ldarg.0
0x123539  call     instance int32 System.Web.Security.SqlRoleProvider::get_CommandTimeout()
0x12353e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x123543  ldstr    aReturnvalue// "@ReturnValue"
0x123548  ldc.i4.8
0x123549  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x12354e  stloc.2
0x12354f  ldloc.2
0x123550  ldc.i4.6
0x123551  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x123556  ldloc.1
0x123557  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x12355c  ldloc.2
0x12355d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123562  pop
0x123563  ldloc.1
0x123564  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123569  ldarg.0
0x12356a  ldstr    aApplicationnam_0// "@ApplicationName"
0x12356f  ldc.i4.s 0xC
0x123571  ldarg.0
0x123572  callvirt instance string [System.Web.ApplicationServices]System.Web.Security.RoleProvider::get_ApplicationName()
0x123577  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x12357c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x123581  pop
0x123582  ldloc.1
0x123583  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x123588  ldarg.0
0x123589  ldstr    aRolename_0// "@RoleName"
0x12358e  ldc.i4.s 0xC
0x123590  ldarg.1
0x123591  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x123596  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x12359b  pop
0x12359c  ldloc.1
0x12359d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1235a2  ldarg.0
0x1235a3  ldstr    aDeleteonlyifro// "@DeleteOnlyIfRoleIsEmpty"
0x1235a8  ldc.i4.2
0x1235a9  ldarg.2
0x1235aa  brtrue.s loc_1235AF
0x1235ac  ldc.i4.0
0x1235ad  br.s     loc_1235B0
0x1235af  ldc.i4.1
0x1235b0  box      [mscorlib]System.Int32
0x1235b5  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Security.SqlRoleProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x1235ba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1235bf  pop
0x1235c0  ldloc.1
0x1235c1  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x1235c6  pop
0x1235c7  ldarg.0
0x1235c8  ldloc.1
0x1235c9  call     instance int32 System.Web.Security.SqlRoleProvider::GetReturnValue(class [System.Data]System.Data.SqlClient.SqlCommand cmd)
0x1235ce  stloc.3
0x1235cf  ldloc.3
0x1235d0  ldc.i4.2
0x1235d1  bne.un.s loc_1235E3
0x1235d3  ldstr    aRoleIsNotEmpty// "Role_is_not_empty"
0x1235d8  call     string System.Web.SR::GetString(string name)
0x1235dd  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1235e2  throw
0x1235e3  ldloc.3
0x1235e4  ldc.i4.0
0x1235e5  ceq
0x1235e7  stloc.s  4
0x1235e9  leave.s  loc_1235FA
0x1235eb  ldloc.0
0x1235ec  brfalse.s loc_1235F6
0x1235ee  ldloc.0
0x1235ef  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x1235f4  ldnull
0x1235f5  stloc.0
0x1235f6  endfinally
0x1235f7  pop
0x1235f8  rethrow
0x1235fa  ldloc.s  4
0x1235fc  ret
```
