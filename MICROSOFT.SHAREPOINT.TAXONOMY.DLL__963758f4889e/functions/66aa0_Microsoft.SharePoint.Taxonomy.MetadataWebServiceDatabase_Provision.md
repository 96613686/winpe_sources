# Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::Provision

- ea: `0x66aa0`
- end: `0x66c88`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::Provision`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x17960`
- `0x1b560`
- `0x2a960`
- `0x38910`
- `0x66aa0`
- `0x66cd0`
- `0x66ec0`

## string_xrefs

- `0x66b22`: `proc_ECM_SetServiceSettings`
- `0x66ae3`: `Provisioning the MetadataServiceDatabase`
- `0x66bc1`: `MetadataWebServiceDatabase contains valid schema`
- `0x66c1a`: `Finish upgrading MetadataWebServiceDatabase to current schema`
- `0x66c33`: `MetadataWebServiceDatabase {0} upgrade failed during database attach`
- `0x66c5f`: `MetadataWebServiceDatabase does not contain valid scheme`
- `0x66c69`: `MetadataWebServiceDatabase does not contain valid scheme`

## pseudocode

```c

```

## disassembly

```asm
0x66aa0  ldarg.0
0x66aa1  ldc.i4.4
0x66aa2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus)
0x66aa7  ldc.i4.1
0x66aa8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase/DatabaseOptions, bool>::.ctor(int32)
0x66aad  stloc.0
0x66aae  ldloc.0
0x66aaf  ldc.i4.2
0x66ab0  ldc.i4.0
0x66ab1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase/DatabaseOptions, bool>::Add(var<u1>, !!T0)
0x66ab6  ldarg.0
0x66ab7  ldarg.0
0x66ab8  call     instance valuetype Microsoft.SharePoint.Taxonomy.DatabaseStatus Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::GetDatabaseStatus()
0x66abd  stfld    valuetype Microsoft.SharePoint.Taxonomy.DatabaseStatus Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::preProvisionStatus
0x66ac2  ldarg.0
0x66ac3  ldfld    valuetype Microsoft.SharePoint.Taxonomy.DatabaseStatus Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::preProvisionStatus
0x66ac8  ldc.i4.1
0x66ac9  beq.s    loc_66AD7
0x66acb  ldarg.0
0x66acc  ldfld    valuetype Microsoft.SharePoint.Taxonomy.DatabaseStatus Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::preProvisionStatus
0x66ad1  ldc.i4.2
0x66ad2  bne.un   loc_66BA9
0x66ad7  ldc.i4   0x387A306A
0x66adc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66ae1  ldc.i4.s 0x32
0x66ae3  ldstr    aProvisioningTh// "Provisioning the MetadataServiceDatabas"...
0x66ae8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66aed  ldarg.0
0x66aee  call     instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::get_DatabaseConnectionString()
0x66af3  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::get_SqlScriptFilePath()
0x66af8  ldloc.0
0x66af9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::Provision(string, string, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase/DatabaseOptions, bool>)
0x66afe  ldarg.0
0x66aff  ldc.i4.0
0x66b00  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::set_NeedsUpgrade(bool)
0x66b05  ldarg.0
0x66b06  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase database)
0x66b0b  stloc.1
0x66b0c  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x66b11  stloc.2
0x66b12  ldloc.1
0x66b13  ldc.i4.0
0x66b14  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::CreateSqlSession(valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x66b19  stloc.3
0x66b1a  ldloc.2
0x66b1b  ldc.i4.4
0x66b1c  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x66b21  ldloc.2
0x66b22  ldstr    aProcEcmSetserv// "proc_ECM_SetServiceSettings"
0x66b27  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x66b2c  ldloc.2
0x66b2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x66b32  ldstr    aPartitionid// "@PartitionId"
0x66b37  ldc.i4.s 0xE
0x66b39  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x66b3e  pop
0x66b3f  ldloc.2
0x66b40  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x66b45  ldstr    aPartitionid// "@PartitionId"
0x66b4a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x66b4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x66b54  box      [mscorlib]System.Guid
0x66b59  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x66b5e  ldloc.2
0x66b5f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x66b64  ldstr    aSettings// "@Settings"
0x66b69  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x66b6e  ldstr    asc_794BA// ""
0x66b73  ldc.i4.0
0x66b74  ldarg.0
0x66b75  ldfld    int32 Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::cacheCheckInterval
0x66b7a  ldarg.0
0x66b7b  ldfld    int32 Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::maxChannelCache
0x66b80  ldc.i4.0
0x66b81  ldnull
0x66b82  call     string Microsoft.SharePoint.Taxonomy.PartitionSettings::GenerateServiceSettingsXml(valuetype [mscorlib]System.Guid termStoreId, string hubUri, bool isSyndicationErrorReportEnabled, int32 cacheCheckInterval, int32 maxChannelsToCache, bool isSearchNotified, class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters taxonomyReplicationParameters)
0x66b87  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x66b8c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66b91  pop
0x66b92  ldloc.3
0x66b93  ldloc.2
0x66b94  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession::ExecuteNonQuery(class [System.Data]System.Data.SqlClient.SqlCommand command)
0x66b99  pop
0x66b9a  leave    loc_66C74
0x66b9f  ldloc.2
0x66ba0  brfalse.s loc_66BA8
0x66ba2  ldloc.2
0x66ba3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66ba8  endfinally
0x66ba9  ldarg.0
0x66baa  ldfld    valuetype Microsoft.SharePoint.Taxonomy.DatabaseStatus Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::preProvisionStatus
0x66baf  ldc.i4.3
0x66bb0  bne.un   loc_66C53
0x66bb5  ldc.i4   0x6335656C
0x66bba  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66bbf  ldc.i4.s 0x32
0x66bc1  ldstr    aMetadatawebser_66// "MetadataWebServiceDatabase contains val"...
0x66bc6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66bcb  ldarg.0
0x66bcc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::get_NeedsUpgrade()
0x66bd1  brfalse  loc_66C74
0x66bd6  ldarg.0
0x66bd7  call     instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::get_ShouldDeferUpgradeActions()
0x66bdc  brtrue   loc_66C74
0x66be1  ldarg.0
0x66be2  call     instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::get_ShouldSkipUpgradeForHigherSchemaVersion()
0x66be7  brtrue   loc_66C74
0x66bec  ldarg.0
0x66bed  ldc.i4.1
0x66bee  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::set_NeedsUpgrade(bool)
0x66bf3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPManager::PeekIsUpgradeRunning()
0x66bf8  brtrue.s loc_66C08
0x66bfa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPManager [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPManager::get_Instance()
0x66bff  ldarg.0
0x66c00  ldc.i4.0
0x66c01  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPManager::RunUpgradeSession(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.IUpgradable, bool)
0x66c06  br.s     loc_66C0E
0x66c08  ldarg.0
0x66c09  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::Upgrade()
0x66c0e  ldc.i4   0x6335656D
0x66c13  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66c18  ldc.i4.s 0x14
0x66c1a  ldstr    aFinishUpgradin// "Finish upgrading MetadataWebServiceData"...
0x66c1f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66c24  leave.s  loc_66C74
0x66c26  pop
0x66c27  ldc.i4   0x6335656E
0x66c2c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66c31  ldc.i4.s 0xA
0x66c33  ldstr    aMetadatawebser_67// "MetadataWebServiceDatabase {0} upgrade "...
0x66c38  ldc.i4.1
0x66c39  newarr   [mscorlib]System.Object
0x66c3e  stloc.s  4
0x66c40  ldloc.s  4
0x66c42  ldc.i4.0
0x66c43  ldarg.0
0x66c44  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x66c49  stelem.ref
0x66c4a  ldloc.s  4
0x66c4c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x66c51  leave.s  loc_66C74
0x66c53  ldc.i4   0x6335656F
0x66c58  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66c5d  ldc.i4.s 0xA
0x66c5f  ldstr    aMetadatawebser_68// "MetadataWebServiceDatabase does not con"...
0x66c64  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66c69  ldstr    aMetadatawebser_68// "MetadataWebServiceDatabase does not con"...
0x66c6e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x66c73  throw
0x66c74  ldarg.0
0x66c75  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::GrantOwnerAccessToDatabaseAccount()
0x66c7a  ldarg.0
0x66c7b  ldc.i4.0
0x66c7c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus)
0x66c81  ldarg.0
0x66c82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x66c87  ret
```
