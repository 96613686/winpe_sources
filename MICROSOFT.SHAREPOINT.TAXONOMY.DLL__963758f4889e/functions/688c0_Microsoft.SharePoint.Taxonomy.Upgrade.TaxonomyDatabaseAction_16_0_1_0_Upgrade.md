# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_1_0::Upgrade

- ea: `0x688c0`
- end: `0x688f6`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_1_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x688d6`: `\n-- IX_ECMTerm_Id\n\nIF NOT EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE object_id = object_id(N'[dbo].[ECMTerm]') AND name = 'IX_ECMTerm_Id')\nBEGIN\n\n    CREATE NONCLUSTERED INDEX [IX_ECMTerm_Id] ON [dbo].[ECMTerm] ([Id]) \n\nEND\nGO\n\nIF (EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE fill_factor <> 100 AND name='IX_ECMTerm_Id' AND object_id=object_id(N'[dbo].[ECMTerm]'))\nOR EXISTS (SELECT TOP 1 1 FROM sys.stats WHERE no_recompute = 0 AND name='IX_ECMTerm_Id' AND object_id=obj`
- `0x688eb`: `Updated database with new SQL indexes.`

## pseudocode

```c

```
