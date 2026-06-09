# System.Web.Security.SqlRoleProvider::AddUsersToRoles

- ea: `0x1236f0`
- end: `0x12387f`
- name: `System.Web.Security.SqlRoleProvider::AddUsersToRoles`
- size: `399`
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
- `0x1236f0`
- `0x123880`

## string_xrefs

- `0x12382e`: `COMMIT TRANSACTION`
- `0x12384c`: `ROLLBACK TRANSACTION`

## pseudocode

```c

```

## disassembly

```asm
0x1236f0  ldarga.s 2
0x1236f2  ldc.i4.1
0x1236f3  ldc.i4.1
0x1236f4  ldc.i4.1
0x1236f5  ldc.i4   0x100
0x1236fa  ldstr    aRolenames// "roleNames"
0x1236ff  call     void System.Web.Util.SecUtility::CheckArrayParameter(string[]& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123704  ldarga.s 1
0x123706  ldc.i4.1
0x123707  ldc.i4.1
0x123708  ldc.i4.1
0x123709  ldc.i4   0x100
0x12370e  ldstr    aUsernames// "usernames"
0x123713  call     void System.Web.Util.SecUtility::CheckArrayParameter(string[]& param, bool checkForNull, bool checkIfEmpty, bool checkForCommas, int32 maxSize, string paramName)
0x123718  ldc.i4.0
0x123719  stloc.0
0x12371a  ldnull
0x12371b  stloc.1
0x12371c  ldarg.0
0x12371d  ldfld    string System.Web.Security.SqlRoleProvider::_sqlConnectionString
0x123722  ldc.i4.1
0x123723  call     class System.Web.DataAccess.SqlConnectionHolder System.Web.DataAccess.SqlConnectionHelper::GetConnection(string connectionString, bool revertImpersonation)
0x123728  stloc.1
0x123729  ldarg.0
0x12372a  ldloc.1
0x12372b  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123730  call     instance void System.Web.Security.SqlRoleProvider::CheckSchemaVersion(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0x123735  ldarg.1
0x123736  ldlen
0x123737  conv.i4
0x123738  stloc.2
0x123739  br       loc_123824
0x12373e  ldarg.1
0x12373f  ldarg.1
0x123740  ldlen
0x123741  conv.i4
0x123742  ldloc.2
0x123743  sub
0x123744  ldelem.ref
0x123745  stloc.s  4
0x123747  ldloc.2
0x123748  ldc.i4.1
0x123749  sub
0x12374a  stloc.2
0x12374b  ldarg.1
0x12374c  ldlen
0x12374d  conv.i4
0x12374e  ldloc.2
0x12374f  sub
0x123750  stloc.3
0x123751  br.s     loc_123785
0x123753  ldloc.s  4
0x123755  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12375a  ldarg.1
0x12375b  ldloc.3
0x12375c  ldelem.ref
0x12375d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123762  add
0x123763  ldc.i4.1
0x123764  add
0x123765  ldc.i4   0xFA0
0x12376a  bge.s    loc_12378B
0x12376c  ldloc.s  4
0x12376e  ldstr    asc_1BCE7A// ","
0x123773  ldarg.1
0x123774  ldloc.3
0x123775  ldelem.ref
0x123776  call     string [mscorlib]System.String::Concat(string, string, string)
0x12377b  stloc.s  4
0x12377d  ldloc.2
0x12377e  ldc.i4.1
0x12377f  sub
0x123780  stloc.2
0x123781  ldloc.3
0x123782  ldc.i4.1
0x123783  add
0x123784  stloc.3
0x123785  ldloc.3
0x123786  ldarg.1
0x123787  ldlen
0x123788  conv.i4
0x123789  blt.s    loc_123753
0x12378b  ldarg.2
0x12378c  ldlen
0x12378d  conv.i4
0x12378e  stloc.s  5
0x123790  br       loc_12381C
0x123795  ldarg.2
0x123796  ldarg.2
0x123797  ldlen
0x123798  conv.i4
0x123799  ldloc.s  5
0x12379b  sub
0x12379c  ldelem.ref
0x12379d  stloc.s  6
0x12379f  ldloc.s  5
0x1237a1  ldc.i4.1
0x1237a2  sub
0x1237a3  stloc.s  5
0x1237a5  ldarg.2
0x1237a6  ldlen
0x1237a7  conv.i4
0x1237a8  ldloc.s  5
0x1237aa  sub
0x1237ab  stloc.3
0x1237ac  br.s     loc_1237E2
0x1237ae  ldloc.s  6
0x1237b0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1237b5  ldarg.2
0x1237b6  ldloc.3
0x1237b7  ldelem.ref
0x1237b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1237bd  add
0x1237be  ldc.i4.1
0x1237bf  add
0x1237c0  ldc.i4   0xFA0
0x1237c5  bge.s    loc_1237E8
0x1237c7  ldloc.s  6
0x1237c9  ldstr    asc_1BCE7A// ","
0x1237ce  ldarg.2
0x1237cf  ldloc.3
0x1237d0  ldelem.ref
0x1237d1  call     string [mscorlib]System.String::Concat(string, string, string)
0x1237d6  stloc.s  6
0x1237d8  ldloc.s  5
0x1237da  ldc.i4.1
0x1237db  sub
0x1237dc  stloc.s  5
0x1237de  ldloc.3
0x1237df  ldc.i4.1
0x1237e0  add
0x1237e1  stloc.3
0x1237e2  ldloc.3
0x1237e3  ldarg.2
0x1237e4  ldlen
0x1237e5  conv.i4
0x1237e6  blt.s    loc_1237AE
0x1237e8  ldloc.0
0x1237e9  brtrue.s loc_12380C
0x1237eb  ldloc.2
0x1237ec  ldc.i4.0
0x1237ed  bgt.s    loc_1237F4
0x1237ef  ldloc.s  5
0x1237f1  ldc.i4.0
0x1237f2  ble.s    loc_12380C
0x1237f4  ldstr    aBeginTransacti// "BEGIN TRANSACTION"
0x1237f9  ldloc.1
0x1237fa  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x1237ff  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x123804  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123809  pop
0x12380a  ldc.i4.1
0x12380b  stloc.0
0x12380c  ldarg.0
0x12380d  ldloc.1
0x12380e  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123813  ldloc.s  4
0x123815  ldloc.s  6
0x123817  call     instance void System.Web.Security.SqlRoleProvider::AddUsersToRolesCore(class [System.Data]System.Data.SqlClient.SqlConnection conn, string usernames, string roleNames)
0x12381c  ldloc.s  5
0x12381e  ldc.i4.0
0x12381f  bgt      loc_123795
0x123824  ldloc.2
0x123825  ldc.i4.0
0x123826  bgt      loc_12373E
0x12382b  ldloc.0
0x12382c  brfalse.s loc_123846
0x12382e  ldstr    aCommitTransact// "COMMIT TRANSACTION"
0x123833  ldloc.1
0x123834  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123839  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x12383e  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123843  pop
0x123844  ldc.i4.0
0x123845  stloc.0
0x123846  leave.s  loc_12386B
0x123848  pop
0x123849  ldloc.0
0x12384a  brfalse.s loc_123869
0x12384c  ldstr    aRollbackTransa// "ROLLBACK TRANSACTION"
0x123851  ldloc.1
0x123852  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection System.Web.DataAccess.SqlConnectionHolder::get_Connection()
0x123857  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x12385c  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x123861  pop
0x123862  leave.s  loc_123867
0x123864  pop
0x123865  leave.s  loc_123867
0x123867  ldc.i4.0
0x123868  stloc.0
0x123869  rethrow
0x12386b  leave.s  loc_123879
0x12386d  ldloc.1
0x12386e  brfalse.s loc_123878
0x123870  ldloc.1
0x123871  callvirt instance void System.Web.DataAccess.SqlConnectionHolder::Close()
0x123876  ldnull
0x123877  stloc.1
0x123878  endfinally
0x123879  leave.s  loc_12387E
0x12387b  pop
0x12387c  rethrow
0x12387e  ret
```
