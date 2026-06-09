# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateData

- ea: `0x648a0`
- end: `0x649c8`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateData`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x64660`

## callees

- `0x1bb60`
- `0x1bc00`
- `0x1beb0`
- `0x2a8d0`
- `0x2a940`
- `0x63a10`
- `0x648a0`
- `0x64ba0`

## string_xrefs

- `0x648ac`: `MetadataWebServiceApplication '{0}' property update started.`
- `0x649ae`: `MetadataWebServiceApplication '{0}' property update complete.`

## pseudocode

```c

```

## disassembly

```asm
0x648a0  ldc.i4   0x61617332
0x648a5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x648aa  ldc.i4.s 0x14
0x648ac  ldstr    aMetadatawebser_47// "MetadataWebServiceApplication '{0}' pro"...
0x648b1  ldc.i4.1
0x648b2  newarr   [mscorlib]System.Object
0x648b7  stloc.s  4
0x648b9  ldloc.s  4
0x648bb  ldc.i4.0
0x648bc  ldarg.1
0x648bd  stelem.ref
0x648be  ldloc.s  4
0x648c0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x648c5  ldarg.1
0x648c6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x648cb  brtrue.s loc_648E3
0x648cd  ldarg.0
0x648ce  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x648d3  ldarg.1
0x648d4  ldc.i4.4
0x648d5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x648da  brtrue.s loc_648E3
0x648dc  ldarg.0
0x648dd  ldarg.1
0x648de  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::set_Name(string)
0x648e3  ldarg.2
0x648e4  ldnull
0x648e5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x648ea  brfalse.s loc_64901
0x648ec  ldarg.2
0x648ed  ldarg.0
0x648ee  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::get_ApplicationPool()
0x648f3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x648f8  brfalse.s loc_64901
0x648fa  ldarg.0
0x648fb  ldarg.2
0x648fc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::set_ApplicationPool(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool)
0x64901  ldarg.0
0x64902  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x64907  ldarg.s  7
0x64909  brfalse.s loc_64911
0x6490b  ldarg.0
0x6490c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x64911  ldarg.0
0x64912  call     instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsPartitioned()
0x64917  brtrue   loc_649A2
0x6491c  ldarg.s  5
0x6491e  brtrue.s loc_64929
0x64920  ldarg.s  4
0x64922  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64927  brtrue.s loc_649A2
0x64929  ldc.i4.0
0x6492a  stloc.0
0x6492b  ldarg.s  5
0x6492d  brfalse.s loc_64934
0x6492f  ldarg.s  6
0x64931  stloc.0
0x64932  br.s     loc_64945
0x64934  ldarg.0
0x64935  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x6493a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPServiceApplicationUtilities::DefaultPartitionId
0x6493f  callvirt instance bool Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetIsSyndicationErrorReportEnabledLocal(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x64944  stloc.0
0x64945  ldarg.0
0x64946  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x6494b  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPServiceApplicationUtilities::DefaultPartitionId
0x64950  callvirt instance class Microsoft.SharePoint.Taxonomy.PartitionSettings Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetPartitionSettingsLocal(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x64955  stloc.1
0x64956  ldc.i4.0
0x64957  stloc.2
0x64958  ldc.i4   0x2B22
0x6495d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x64962  brfalse.s loc_64971
0x64964  ldloc.1
0x64965  brtrue.s loc_6496A
0x64967  ldc.i4.0
0x64968  br.s     loc_64970
0x6496a  ldloc.1
0x6496b  ldfld    bool Microsoft.SharePoint.Taxonomy.PartitionSettings::isSearchNotified
0x64970  stloc.2
0x64971  ldnull
0x64972  stloc.3
0x64973  call     bool Microsoft.SharePoint.Taxonomy.PartitionSettings::get_IsTaxonomyReplicationParametersKillSwitchActivated()
0x64978  brtrue.s loc_64987
0x6497a  ldloc.1
0x6497b  brtrue.s loc_64980
0x6497d  ldnull
0x6497e  br.s     loc_64986
0x64980  ldloc.1
0x64981  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters Microsoft.SharePoint.Taxonomy.PartitionSettings::taxonomyReplicationParameters
0x64986  stloc.3
0x64987  ldarg.0
0x64988  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x6498d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPServiceApplicationUtilities::DefaultPartitionId
0x64992  ldarg.s  4
0x64994  ldloc.0
0x64995  ldloc.2
0x64996  ldloc.3
0x64997  call     string Microsoft.SharePoint.Taxonomy.PartitionSettings::GenerateServiceSettingsXml(string hubUri, bool isSyndicationErrorReportEnabled, bool isSearchNotified, class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters taxonomyReplicationParameters)
0x6499c  ldarg.3
0x6499d  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SetServiceSettingsLocal(valuetype [mscorlib]System.Guid rawPartitionId, string settingsXml, bool unpublishAllPackages)
0x649a2  ldc.i4   0x61617333
0x649a7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x649ac  ldc.i4.s 0x14
0x649ae  ldstr    aMetadatawebser_48// "MetadataWebServiceApplication '{0}' pro"...
0x649b3  ldc.i4.1
0x649b4  newarr   [mscorlib]System.Object
0x649b9  stloc.s  5
0x649bb  ldloc.s  5
0x649bd  ldc.i4.0
0x649be  ldarg.1
0x649bf  stelem.ref
0x649c0  ldloc.s  5
0x649c2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x649c7  ret
```
