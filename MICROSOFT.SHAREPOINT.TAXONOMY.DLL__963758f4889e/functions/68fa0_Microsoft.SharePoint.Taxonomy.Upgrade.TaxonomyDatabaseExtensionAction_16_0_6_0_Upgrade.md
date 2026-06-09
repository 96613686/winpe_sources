# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_6_0::Upgrade

- ea: `0x68fa0`
- end: `0x68fec`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_6_0::Upgrade`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1b5f0`
- `0x68e70`

## string_xrefs

- `0x68fac`: `TaxonomyDatabaseExtensionAction_16_0_6_0.Upgrade() called`
- `0x68fe1`: `TaxonomyDatabaseExtensionAction_16_0_6_0.Upgrade() completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x68fa0  ldc.i4   0x6CE1E0
0x68fa5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x68faa  ldc.i4.s 0x14
0x68fac  ldstr    aTaxonomydataba_5// "TaxonomyDatabaseExtensionAction_16_0_6_"...
0x68fb1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x68fb6  ldarg.0
0x68fb7  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_UpgradableObject()
0x68fbc  castclass [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase
0x68fc1  stloc.0
0x68fc2  ldloc.0
0x68fc3  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForContentDatabase(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x68fc8  stloc.1
0x68fc9  ldloc.1
0x68fca  ldarg.0
0x68fcb  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISqlSession [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseAction::get_SqlSession()
0x68fd0  call     void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseExtension::ProvisionSchema(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter databaseAdapter, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISqlSession sqlSession)
0x68fd5  ldc.i4   0x6CE1E1
0x68fda  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x68fdf  ldc.i4.s 0x14
0x68fe1  ldstr    aTaxonomydataba_6// "TaxonomyDatabaseExtensionAction_16_0_6_"...
0x68fe6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x68feb  ret
```
