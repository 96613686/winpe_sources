# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_1_0::Upgrade

- ea: `0x684c0`
- end: `0x684f6`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_1_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x684cb`: `Updating primary keys, indexes, foreign keys and sprocs for SQL Azure Compatibility.`
- `0x684d6`: `\n\nIF EXISTS (SELECT * FROM sysobjects WHERE name = 'proc_ECM_UpdateTermLabel' AND type = 'P') DROP PROCEDURE proc_ECM_UpdateTermLabel\nGO\n\nIF EXISTS (SELECT * FROM sysobjects WHERE name = 'proc_ECM_InitiateCacheFlush' AND type = 'P') DROP PROCEDURE proc_ECM_InitiateCacheFlush\nGO\n\nIF NOT EXISTS (\nSELECT name FROM sysobjects so \nJOIN sysconstraints sc\nON \nso.id = sc.constid \nWHERE \nobject_name(so.parent_obj) = 'ECMGroup'\nAND so.xtype = 'D'\nAND sc.colid = \n (SELECT `
- `0x684eb`: `Updated primary keys, indexes, foreign keys and sprocs for SQL Azure Compatibility.`

## pseudocode

```c

```

## disassembly

```asm
0x684c0  ldarg.0
0x684c1  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0x684c6  ldc.i4   0x6867C8
0x684cb  ldstr    aUpdatingPrimar// "Updating primary keys, indexes, foreign"...
0x684d0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32, string)
0x684d5  ldarg.0
0x684d6  ldstr    aIfExistsSelect_2// "\r\n\r\nIF EXISTS (SELECT * FROM sysobj"...
0x684db  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseAction::ExecuteSql(string)
0x684e0  ldarg.0
0x684e1  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0x684e6  ldc.i4   0x6867C9
0x684eb  ldstr    aUpdatedPrimary// "Updated primary keys, indexes, foreign "...
0x684f0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32, string)
0x684f5  ret
```
