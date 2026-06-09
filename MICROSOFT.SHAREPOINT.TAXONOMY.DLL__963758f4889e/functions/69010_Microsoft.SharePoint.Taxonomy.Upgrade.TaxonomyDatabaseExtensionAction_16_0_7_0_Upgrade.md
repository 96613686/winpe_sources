# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_7_0::Upgrade

- ea: `0x69010`
- end: `0x69056`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_7_0::Upgrade`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1b5f0`
- `0x68f20`

## string_xrefs

- `0x6901c`: `TaxonomyDatabaseExtensionAction_16_0_7_0.Upgrade() called`
- `0x6904b`: `TaxonomyDatabaseExtensionAction_16_0_7_0.Upgrade() completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x69010  ldc.i4   0x7037D9
0x69015  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6901a  ldc.i4.s 0x14
0x6901c  ldstr    aTaxonomydataba_7// "TaxonomyDatabaseExtensionAction_16_0_7_"...
0x69021  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69026  ldarg.0
0x69027  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_UpgradableObject()
0x6902c  castclass [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase
0x69031  stloc.0
0x69032  ldloc.0
0x69033  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForContentDatabase(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x69038  stloc.1
0x69039  ldloc.1
0x6903a  call     void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseExtension::SetDefaultQuotaValues(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter databaseAdapter)
0x6903f  ldc.i4   0x7037DA
0x69044  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x69049  ldc.i4.s 0x14
0x6904b  ldstr    aTaxonomydataba_8// "TaxonomyDatabaseExtensionAction_16_0_7_"...
0x69050  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69055  ret
```
