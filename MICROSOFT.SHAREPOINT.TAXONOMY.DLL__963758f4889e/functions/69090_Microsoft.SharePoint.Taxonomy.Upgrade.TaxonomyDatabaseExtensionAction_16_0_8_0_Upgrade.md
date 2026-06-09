# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_8_0::Upgrade

- ea: `0x69090`
- end: `0x690cd`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseExtensionAction_16_0_8_0::Upgrade`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x6909c`: `TaxonomyDatabaseExtensionAction_16_0_8_0.Upgrade() called`
- `0x690a7`: `\nIF EXISTS (SELECT * FROM sys.database_principals WHERE '[' + name + ']' = N'[SPDataAccess]' AND type = 'R')\n    GRANT SELECT,DELETE,UPDATE,EXECUTE,INSERT ON SCHEMA :: [tax] TO [SPDataAccess];\nGO\n\nIF EXISTS (SELECT * FROM sys.database_principals WHERE '[' + name + ']' = N'[SPReadOnly]' AND type = 'R')\n    GRANT SELECT ON SCHEMA :: [tax] TO [SPReadOnly];\nGO\n`
- `0x690c2`: `TaxonomyDatabaseExtensionAction_16_0_8_0.Upgrade() completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x69090  ldc.i4   0x758812
0x69095  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6909a  ldc.i4.s 0x14
0x6909c  ldstr    aTaxonomydataba_9// "TaxonomyDatabaseExtensionAction_16_0_8_"...
0x690a1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x690a6  ldarg.0
0x690a7  ldstr    aIfExistsSelect_8// "\r\nIF EXISTS (SELECT * FROM sys.databa"...
0x690ac  ldc.i4   0x12C
0x690b1  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseAction::ExecuteSql(string, int32)
0x690b6  ldc.i4   0x758813
0x690bb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x690c0  ldc.i4.s 0x14
0x690c2  ldstr    aTaxonomydataba_10// "TaxonomyDatabaseExtensionAction_16_0_8_"...
0x690c7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x690cc  ret
```
