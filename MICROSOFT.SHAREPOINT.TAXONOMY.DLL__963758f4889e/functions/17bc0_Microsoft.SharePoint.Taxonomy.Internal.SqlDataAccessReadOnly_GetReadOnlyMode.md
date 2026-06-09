# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetReadOnlyMode

- ea: `0x17bc0`
- end: `0x17c67`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetReadOnlyMode`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c0a0`

## callees

- `0x178f0`
- `0x17bc0`
- `0x19bd0`
- `0x19e40`

## string_xrefs

- `0x17bcc`: `Getting service read only flag`
- `0x17be7`: `proc_ECM_GetPartitionReadOnly`
- `0x17c5b`: `Got service read only flag`

## pseudocode

```c

```

## disassembly

```asm
0x17bc0  ldc.i4   0x78B1DD
0x17bc5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17bca  ldc.i4.s 0x64
0x17bcc  ldstr    aGettingService_0// "Getting service read only flag"
0x17bd1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17bd6  ldnull
0x17bd7  stloc.0
0x17bd8  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x17bdd  stloc.1
0x17bde  ldloc.1
0x17bdf  ldc.i4.4
0x17be0  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x17be5  ldloc.1
0x17be6  ldarg.0
0x17be7  ldstr    aProcEcmGetpart// "proc_ECM_GetPartitionReadOnly"
0x17bec  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x17bf1  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x17bf6  ldloc.1
0x17bf7  ldarg.0
0x17bf8  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x17bfd  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x17c02  ldloc.1
0x17c03  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17c08  ldstr    aPartitionid// "@PartitionId"
0x17c0d  ldc.i4.s 0xE
0x17c0f  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x17c14  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x17c19  pop
0x17c1a  ldloc.1
0x17c1b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17c20  ldstr    aPartitionid// "@PartitionId"
0x17c25  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x17c2a  ldarg.1
0x17c2b  box      [mscorlib]System.Guid
0x17c30  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x17c35  ldarg.0
0x17c36  ldloc.1
0x17c37  ldsfld   string[] GetServiceSettings::Tables
0x17c3c  ldc.i4.1
0x17c3d  call     instance string Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetResultXML(class [System.Data]System.Data.SqlClient.SqlCommand command, string[] tableNameList, valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x17c42  stloc.0
0x17c43  leave.s  loc_17C4F
0x17c45  ldloc.1
0x17c46  brfalse.s loc_17C4E
0x17c48  ldloc.1
0x17c49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17c4e  endfinally
0x17c4f  ldc.i4   0x78B1DE
0x17c54  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17c59  ldc.i4.s 0x64
0x17c5b  ldstr    aGotServiceRead// "Got service read only flag"
0x17c60  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17c65  ldloc.0
0x17c66  ret
```
