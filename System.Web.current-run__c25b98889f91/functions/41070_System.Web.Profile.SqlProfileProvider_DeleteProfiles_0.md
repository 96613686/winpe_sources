# System.Web.Profile.SqlProfileProvider::DeleteProfiles_0

- ea: `0x41070`
- end: `0x41203`
- name: `System.Web.Profile.SqlProfileProvider::DeleteProfiles_0`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x40b30`
- `0x40ba0`
- `0x40fc0`
- `0x41070`
- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x58600`

## string_xrefs

- `0x41128`: `dbo.aspnet_Profile_DeleteProfiles`
- `0x411b0`: `COMMIT TRANSACTION`
- `0x411d0`: `ROLLBACK TRANSACTION`

## pseudocode

```c

```

## disassembly

```asm
0x41070  ldarga.s 1
0x41072  ldc.i4.1
0x41073  ldc.i4.1
0x41074  ldc.i4.1
0x41075  ldc.i4   0x100
0x4107a  ldstr    aUsernames// "usernames"
0x4107f  call     void System.Web.Util.SecUtility::CheckArrayParameter(string[]& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x41084  ldc.i4.0
0x41085  stloc.0
0x41086  ldc.i4.0
0x41087  stloc.1
0x41088  ldnull
0x41089  stloc.2
0x4108a  ldarg.0
0x4108b  ldfld    string System.Web.Profile.SqlProfileProvider::_sqlConnectionString
0x41090  ldc.i4.1
0x41091  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x41096  stloc.2
0x41097  ldarg.0
0x41098  ldloc.2
0x41099  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x4109e  call     instance void System.Web.Profile.SqlProfileProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x410a3  ldarg.1
0x410a4  ldlen
0x410a5  conv.i4
0x410a6  stloc.s  4
0x410a8  br       loc_411A5
0x410ad  ldarg.1
0x410ae  ldarg.1
0x410af  ldlen
0x410b0  conv.i4
0x410b1  ldloc.s  4
0x410b3  sub
0x410b4  ldelem.ref
0x410b5  stloc.s  5
0x410b7  ldloc.s  4
0x410b9  ldc.i4.1
0x410ba  sub
0x410bb  stloc.s  4
0x410bd  ldarg.1
0x410be  ldlen
0x410bf  conv.i4
0x410c0  ldloc.s  4
0x410c2  sub
0x410c3  stloc.s  7
0x410c5  br.s     loc_410FF
0x410c7  ldloc.s  5
0x410c9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x410ce  ldarg.1
0x410cf  ldloc.s  7
0x410d1  ldelem.ref
0x410d2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x410d7  add
0x410d8  ldc.i4.1
0x410d9  add
0x410da  ldc.i4   0xFA0
0x410df  bge.s    loc_41106
0x410e1  ldloc.s  5
0x410e3  ldstr    asc_1BCE7A// ","
0x410e8  ldarg.1
0x410e9  ldloc.s  7
0x410eb  ldelem.ref
0x410ec  call     string [mscorlib]System.String::Concat(string, string, string)
0x410f1  stloc.s  5
0x410f3  ldloc.s  4
0x410f5  ldc.i4.1
0x410f6  sub
0x410f7  stloc.s  4
0x410f9  ldloc.s  7
0x410fb  ldc.i4.1
0x410fc  add
0x410fd  stloc.s  7
0x410ff  ldloc.s  7
0x41101  ldarg.1
0x41102  ldlen
0x41103  conv.i4
0x41104  blt.s    loc_410C7
0x41106  ldloc.1
0x41107  brtrue.s loc_41128
0x41109  ldloc.s  4
0x4110b  ldc.i4.0
0x4110c  ble.s    loc_41128
0x4110e  ldstr    aBeginTransacti// "BEGIN TRANSACTION"
0x41113  ldloc.2
0x41114  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x41119  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x4111e  stloc.3
0x4111f  ldloc.3
0x41120  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x41125  pop
0x41126  ldc.i4.1
0x41127  stloc.1
0x41128  ldstr    aDboAspnetProfi_1// "dbo.aspnet_Profile_DeleteProfiles"
0x4112d  ldloc.2
0x4112e  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x41133  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x41138  stloc.3
0x41139  ldloc.3
0x4113a  ldarg.0
0x4113b  call     instance int32 System.Web.Profile.SqlProfileProvider::get_CommandTimeout()
0x41140  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x41145  ldloc.3
0x41146  ldc.i4.4
0x41147  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x4114c  ldloc.3
0x4114d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x41152  ldarg.0
0x41153  ldstr    aApplicationnam_0// "@ApplicationName"
0x41158  ldc.i4.s 0xC
0x4115a  ldarg.0
0x4115b  callvirt instance string [System]System.Configuration.SettingsProvider::get_ApplicationName()
0x41160  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Profile.SqlProfileProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x41165  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x4116a  pop
0x4116b  ldloc.3
0x4116c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x41171  ldarg.0
0x41172  ldstr    aUsernames_0// "@UserNames"
0x41177  ldc.i4.s 0xC
0x41179  ldloc.s  5
0x4117b  call     instance class [System.Data]System.Data.SqlClient.SqlParameter System.Web.Profile.SqlProfileProvider::CreateInputParam(string paramName, valuetype [System.Data]System.Data.SqlDbType dbType, object objValue)
0x41180  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x41185  pop
0x41186  ldloc.3
0x41187  callvirt instance object [System.Data]System.Data.Common.DbCommand::ExecuteScalar()
0x4118c  stloc.s  6
0x4118e  ldloc.s  6
0x41190  brfalse.s loc_411A5
0x41192  ldloc.s  6
0x41194  isinst   [mscorlib]System.Int32
0x41199  brfalse.s loc_411A5
0x4119b  ldloc.0
0x4119c  ldloc.s  6
0x4119e  unbox.any [mscorlib]System.Int32
0x411a3  add
0x411a4  stloc.0
0x411a5  ldloc.s  4
0x411a7  ldc.i4.0
0x411a8  bgt      loc_410AD
0x411ad  ldloc.1
0x411ae  brfalse.s loc_411CA
0x411b0  ldstr    aCommitTransact// "COMMIT TRANSACTION"
0x411b5  ldloc.2
0x411b6  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x411bb  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x411c0  stloc.3
0x411c1  ldloc.3
0x411c2  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x411c7  pop
0x411c8  ldc.i4.0
0x411c9  stloc.1
0x411ca  leave.s  loc_411EE
0x411cc  pop
0x411cd  ldloc.1
0x411ce  brfalse.s loc_411EC
0x411d0  ldstr    aRollbackTransa// "ROLLBACK TRANSACTION"
0x411d5  ldloc.2
0x411d6  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x411db  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x411e0  stloc.s  8
0x411e2  ldloc.s  8
0x411e4  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x411e9  pop
0x411ea  ldc.i4.0
0x411eb  stloc.1
0x411ec  rethrow
0x411ee  leave.s  loc_411FC
0x411f0  ldloc.2
0x411f1  brfalse.s loc_411FB
0x411f3  ldloc.2
0x411f4  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x411f9  ldnull
0x411fa  stloc.2
0x411fb  endfinally
0x411fc  leave.s  loc_41201
0x411fe  pop
0x411ff  rethrow
0x41201  ldloc.0
0x41202  ret
```
