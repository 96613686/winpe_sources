# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetServiceSettings

- ea: `0x17a60`
- end: `0x17b07`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetServiceSettings`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1e000`

## callees

- `0x178f0`
- `0x17a60`
- `0x19bd0`
- `0x19e40`

## string_xrefs

- `0x17a6c`: `Getting service settings data`
- `0x17a87`: `proc_ECM_GetServiceSettings`
- `0x17afb`: `Got service settings data`

## pseudocode

```c

```

## disassembly

```asm
0x17a60  ldc.i4   0x3973696B
0x17a65  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17a6a  ldc.i4.s 0x64
0x17a6c  ldstr    aGettingService// "Getting service settings data"
0x17a71  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17a76  ldnull
0x17a77  stloc.0
0x17a78  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x17a7d  stloc.1
0x17a7e  ldloc.1
0x17a7f  ldc.i4.4
0x17a80  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x17a85  ldloc.1
0x17a86  ldarg.0
0x17a87  ldstr    aProcEcmGetserv// "proc_ECM_GetServiceSettings"
0x17a8c  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x17a91  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x17a96  ldloc.1
0x17a97  ldarg.0
0x17a98  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x17a9d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x17aa2  ldloc.1
0x17aa3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17aa8  ldstr    aPartitionid// "@PartitionId"
0x17aad  ldc.i4.s 0xE
0x17aaf  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x17ab4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x17ab9  pop
0x17aba  ldloc.1
0x17abb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17ac0  ldstr    aPartitionid// "@PartitionId"
0x17ac5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x17aca  ldarg.1
0x17acb  box      [mscorlib]System.Guid
0x17ad0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x17ad5  ldarg.0
0x17ad6  ldloc.1
0x17ad7  ldsfld   string[] GetServiceSettings::Tables
0x17adc  ldc.i4.1
0x17add  call     instance string Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetResultXML(class [System.Data]System.Data.SqlClient.SqlCommand command, string[] tableNameList, valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x17ae2  stloc.0
0x17ae3  leave.s  loc_17AEF
0x17ae5  ldloc.1
0x17ae6  brfalse.s loc_17AEE
0x17ae8  ldloc.1
0x17ae9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17aee  endfinally
0x17aef  ldc.i4   0x3973696C
0x17af4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17af9  ldc.i4.s 0x64
0x17afb  ldstr    aGotServiceSett// "Got service settings data"
0x17b00  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17b05  ldloc.0
0x17b06  ret
```
