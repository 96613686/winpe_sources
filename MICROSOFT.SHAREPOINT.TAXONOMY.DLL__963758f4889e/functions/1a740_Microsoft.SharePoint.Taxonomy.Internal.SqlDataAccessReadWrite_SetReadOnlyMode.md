# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::SetReadOnlyMode

- ea: `0x1a740`
- end: `0x1a840`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::SetReadOnlyMode`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c080`

## callees

- `0x178f0`
- `0x19bd0`
- `0x1a740`
- `0x1af40`

## string_xrefs

- `0x1a74f`: `proc_ECM_SetPartitionReadOnly`
- `0x1a796`: `@IsReadOnly`
- `0x1a7d5`: `Read Only mode for partition {0} set to {1}`
- `0x1a82f`: `Attempted to set Read Only mode without stored procedure installed`

## pseudocode

```c

```

## disassembly

```asm
0x1a740  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x1a745  stloc.0
0x1a746  ldloc.0
0x1a747  ldc.i4.4
0x1a748  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x1a74d  ldloc.0
0x1a74e  ldarg.0
0x1a74f  ldstr    aProcEcmSetpart// "proc_ECM_SetPartitionReadOnly"
0x1a754  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x1a759  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x1a75e  ldloc.0
0x1a75f  ldarg.0
0x1a760  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x1a765  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x1a76a  ldloc.0
0x1a76b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1a770  ldstr    aPartitionid// "@PartitionId"
0x1a775  ldc.i4.s 0xE
0x1a777  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x1a77c  stloc.1
0x1a77d  ldloc.1
0x1a77e  ldarg.1
0x1a77f  box      [mscorlib]System.Guid
0x1a784  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1a789  ldloc.1
0x1a78a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1a78f  pop
0x1a790  ldloc.0
0x1a791  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1a796  ldstr    aIsreadonly// "@IsReadOnly"
0x1a79b  ldc.i4.2
0x1a79c  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x1a7a1  stloc.2
0x1a7a2  ldloc.2
0x1a7a3  ldarg.2
0x1a7a4  box      [mscorlib]System.Boolean
0x1a7a9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1a7ae  ldloc.2
0x1a7af  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1a7b4  pop
0x1a7b5  ldarg.0
0x1a7b6  ldloc.0
0x1a7b7  ldc.i4.0
0x1a7b8  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::ExecuteTransactionalNonQuery(class [System.Data]System.Data.SqlClient.SqlCommand command, bool canRetry)
0x1a7bd  leave.s  loc_1A7C9
0x1a7bf  ldloc.0
0x1a7c0  brfalse.s loc_1A7C8
0x1a7c2  ldloc.0
0x1a7c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a7c8  endfinally
0x1a7c9  ldc.i4   0x78B1DF
0x1a7ce  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1a7d3  ldc.i4.s 0x32
0x1a7d5  ldstr    aReadOnlyModeFo// "Read Only mode for partition {0} set to"...
0x1a7da  ldc.i4.2
0x1a7db  newarr   [mscorlib]System.Object
0x1a7e0  stloc.s  5
0x1a7e2  ldloc.s  5
0x1a7e4  ldc.i4.0
0x1a7e5  ldarg.1
0x1a7e6  box      [mscorlib]System.Guid
0x1a7eb  stelem.ref
0x1a7ec  ldloc.s  5
0x1a7ee  ldc.i4.1
0x1a7ef  ldarg.2
0x1a7f0  box      [mscorlib]System.Boolean
0x1a7f5  stelem.ref
0x1a7f6  ldloc.s  5
0x1a7f8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1a7fd  leave.s  loc_1A83F
0x1a7ff  stloc.3
0x1a800  ldloc.3
0x1a801  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1a806  isinst   [System.Data]System.Data.SqlClient.SqlException
0x1a80b  stloc.s  4
0x1a80d  ldloc.3
0x1a80e  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1a813  brfalse.s loc_1A83B
0x1a815  ldloc.s  4
0x1a817  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x1a81c  ldc.i4   0xAFC
0x1a821  bne.un.s loc_1A83B
0x1a823  ldc.i4   0x5D4563
0x1a828  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1a82d  ldc.i4.s 0x32
0x1a82f  ldstr    aAttemptedToSet// "Attempted to set Read Only mode without"...
0x1a834  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1a839  br.s     loc_1A83D
0x1a83b  rethrow
0x1a83d  leave.s  loc_1A83F
0x1a83f  ret
```
