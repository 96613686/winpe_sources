# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetServiceApplicationSettings

- ea: `0x17b10`
- end: `0x17bbb`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetServiceApplicationSettings`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x178f0`
- `0x17b10`
- `0x19bd0`
- `0x19e40`

## string_xrefs

- `0x17b1c`: `Getting service settings data`
- `0x17b37`: `proc_ECM_GetServiceSettings`
- `0x17baf`: `Got service settings data`

## pseudocode

```c

```

## disassembly

```asm
0x17b10  ldc.i4   0x636D6138
0x17b15  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17b1a  ldc.i4.s 0x64
0x17b1c  ldstr    aGettingService// "Getting service settings data"
0x17b21  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17b26  ldnull
0x17b27  stloc.0
0x17b28  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x17b2d  stloc.1
0x17b2e  ldloc.1
0x17b2f  ldc.i4.4
0x17b30  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x17b35  ldloc.1
0x17b36  ldarg.0
0x17b37  ldstr    aProcEcmGetserv// "proc_ECM_GetServiceSettings"
0x17b3c  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x17b41  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x17b46  ldloc.1
0x17b47  ldarg.0
0x17b48  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x17b4d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x17b52  ldloc.1
0x17b53  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17b58  ldstr    aPartitionid// "@PartitionId"
0x17b5d  ldc.i4.s 0xE
0x17b5f  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x17b64  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x17b69  pop
0x17b6a  ldloc.1
0x17b6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x17b70  ldstr    aPartitionid// "@PartitionId"
0x17b75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x17b7a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17b7f  box      [mscorlib]System.Guid
0x17b84  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x17b89  ldarg.0
0x17b8a  ldloc.1
0x17b8b  ldsfld   string[] GetServiceSettings::Tables
0x17b90  ldc.i4.1
0x17b91  call     instance string Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetResultXML(class [System.Data]System.Data.SqlClient.SqlCommand command, string[] tableNameList, valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x17b96  stloc.0
0x17b97  leave.s  loc_17BA3
0x17b99  ldloc.1
0x17b9a  brfalse.s loc_17BA2
0x17b9c  ldloc.1
0x17b9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17ba2  endfinally
0x17ba3  ldc.i4   0x636D6139
0x17ba8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x17bad  ldc.i4.s 0x64
0x17baf  ldstr    aGotServiceSett// "Got service settings data"
0x17bb4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x17bb9  ldloc.0
0x17bba  ret
```
