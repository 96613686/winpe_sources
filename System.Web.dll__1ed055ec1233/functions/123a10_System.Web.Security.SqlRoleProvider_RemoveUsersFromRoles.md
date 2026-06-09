# System.Web.Security.SqlRoleProvider::RemoveUsersFromRoles

- ea: `0x123a10`
- end: `0x123b9a`
- name: `System.Web.Security.SqlRoleProvider::RemoveUsersFromRoles`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4c580`
- `0x4cb40`
- `0x4cbc0`
- `0x58600`
- `0x123100`
- `0x123a10`
- `0x123ba0`

## string_xrefs

- `0x123b4e`: `COMMIT TRANSACTION`
- `0x123b6c`: `ROLLBACK TRANSACTION`

## pseudocode

```c

```

## disassembly

```asm
0x123a10  ldarga.s 2
0x123a12  ldc.i4.1
0x123a13  ldc.i4.1
0x123a14  ldc.i4.1
0x123a15  ldc.i4   0x100
0x123a1a  ldstr    aRolenames// "roleNames"
0x123a1f  call     void System.Web.Util.SecUtility::CheckArrayParameter(string[]& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123a24  ldarga.s 1
0x123a26  ldc.i4.1
0x123a27  ldc.i4.1
0x123a28  ldc.i4.1
0x123a29  ldc.i4   0x100
0x123a2e  ldstr    aUsernames// "usernames"
0x123a33  call     void System.Web.Util.SecUtility::CheckArrayParameter(string[]& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123a38  ldc.i4.0
0x123a39  stloc.0
0x123a3a  ldnull
0x123a3b  stloc.1
0x123a3c  ldarg.0
0x123a3d  ldfld    string System.Web.Security.SqlRoleProvider::_sqlConnectionString
0x123a42  ldc.i4.1
0x123a43  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x123a48  stloc.1
0x123a49  ldarg.0
0x123a4a  ldloc.1
0x123a4b  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123a50  call     instance void System.Web.Security.SqlRoleProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x123a55  ldarg.1
0x123a56  ldlen
0x123a57  conv.i4
0x123a58  stloc.2
0x123a59  br       loc_123B44
0x123a5e  ldarg.1
0x123a5f  ldarg.1
0x123a60  ldlen
0x123a61  conv.i4
0x123a62  ldloc.2
0x123a63  sub
0x123a64  ldelem.ref
0x123a65  stloc.s  4
0x123a67  ldloc.2
0x123a68  ldc.i4.1
0x123a69  sub
0x123a6a  stloc.2
0x123a6b  ldarg.1
0x123a6c  ldlen
0x123a6d  conv.i4
0x123a6e  ldloc.2
0x123a6f  sub
0x123a70  stloc.3
0x123a71  br.s     loc_123AA5
0x123a73  ldloc.s  4
0x123a75  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123a7a  ldarg.1
0x123a7b  ldloc.3
0x123a7c  ldelem.ref
0x123a7d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123a82  add
0x123a83  ldc.i4.1
0x123a84  add
0x123a85  ldc.i4   0xFA0
0x123a8a  bge.s    loc_123AAB
0x123a8c  ldloc.s  4
0x123a8e  ldstr    asc_1BCE7A// ","
0x123a93  ldarg.1
0x123a94  ldloc.3
0x123a95  ldelem.ref
0x123a96  call     string [mscorlib]System.String::Concat(string, string, string)
0x123a9b  stloc.s  4
0x123a9d  ldloc.2
0x123a9e  ldc.i4.1
0x123a9f  sub
0x123aa0  stloc.2
0x123aa1  ldloc.3
0x123aa2  ldc.i4.1
0x123aa3  add
0x123aa4  stloc.3
0x123aa5  ldloc.3
0x123aa6  ldarg.1
0x123aa7  ldlen
0x123aa8  conv.i4
0x123aa9  blt.s    loc_123A73
0x123aab  ldarg.2
0x123aac  ldlen
0x123aad  conv.i4
0x123aae  stloc.s  5
0x123ab0  br       loc_123B3C
0x123ab5  ldarg.2
0x123ab6  ldarg.2
0x123ab7  ldlen
0x123ab8  conv.i4
0x123ab9  ldloc.s  5
0x123abb  sub
0x123abc  ldelem.ref
0x123abd  stloc.s  6
0x123abf  ldloc.s  5
0x123ac1  ldc.i4.1
0x123ac2  sub
0x123ac3  stloc.s  5
0x123ac5  ldarg.2
0x123ac6  ldlen
0x123ac7  conv.i4
0x123ac8  ldloc.s  5
0x123aca  sub
0x123acb  stloc.3
0x123acc  br.s     loc_123B02
0x123ace  ldloc.s  6
0x123ad0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123ad5  ldarg.2
0x123ad6  ldloc.3
0x123ad7  ldelem.ref
0x123ad8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123add  add
0x123ade  ldc.i4.1
0x123adf  add
0x123ae0  ldc.i4   0xFA0
0x123ae5  bge.s    loc_123B08
0x123ae7  ldloc.s  6
0x123ae9  ldstr    asc_1BCE7A// ","
0x123aee  ldarg.2
0x123aef  ldloc.3
0x123af0  ldelem.ref
0x123af1  call     string [mscorlib]System.String::Concat(string, string, string)
0x123af6  stloc.s  6
0x123af8  ldloc.s  5
0x123afa  ldc.i4.1
0x123afb  sub
0x123afc  stloc.s  5
0x123afe  ldloc.3
0x123aff  ldc.i4.1
0x123b00  add
0x123b01  stloc.3
0x123b02  ldloc.3
0x123b03  ldarg.2
0x123b04  ldlen
0x123b05  conv.i4
0x123b06  blt.s    loc_123ACE
0x123b08  ldloc.0
0x123b09  brtrue.s loc_123B2C
0x123b0b  ldloc.2
0x123b0c  ldc.i4.0
0x123b0d  bgt.s    loc_123B14
0x123b0f  ldloc.s  5
0x123b11  ldc.i4.0
0x123b12  ble.s    loc_123B2C
0x123b14  ldstr    aBeginTransacti// "BEGIN TRANSACTION"
0x123b19  ldloc.1
0x123b1a  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123b1f  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x123b24  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123b29  pop
0x123b2a  ldc.i4.1
0x123b2b  stloc.0
0x123b2c  ldarg.0
0x123b2d  ldloc.1
0x123b2e  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123b33  ldloc.s  4
0x123b35  ldloc.s  6
0x123b37  call     instance void System.Web.Security.SqlRoleProvider::RemoveUsersFromRolesCore(class [System.Data]System.Data.SqlClient.SqlConnection conn, string usernames, string roleNames)
0x123b3c  ldloc.s  5
0x123b3e  ldc.i4.0
0x123b3f  bgt      loc_123AB5
0x123b44  ldloc.2
0x123b45  ldc.i4.0
0x123b46  bgt      loc_123A5E
0x123b4b  ldloc.0
0x123b4c  brfalse.s loc_123B66
0x123b4e  ldstr    aCommitTransact// "COMMIT TRANSACTION"
0x123b53  ldloc.1
0x123b54  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123b59  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x123b5e  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123b63  pop
0x123b64  ldc.i4.0
0x123b65  stloc.0
0x123b66  leave.s  loc_123B86
0x123b68  pop
0x123b69  ldloc.0
0x123b6a  brfalse.s loc_123B84
0x123b6c  ldstr    aRollbackTransa// "ROLLBACK TRANSACTION"
0x123b71  ldloc.1
0x123b72  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123b77  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x123b7c  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123b81  pop
0x123b82  ldc.i4.0
0x123b83  stloc.0
0x123b84  rethrow
0x123b86  leave.s  loc_123B94
0x123b88  ldloc.1
0x123b89  brfalse.s loc_123B93
0x123b8b  ldloc.1
0x123b8c  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x123b91  ldnull
0x123b92  stloc.1
0x123b93  endfinally
0x123b94  leave.s  loc_123B99
0x123b96  pop
0x123b97  rethrow
0x123b99  ret
```
