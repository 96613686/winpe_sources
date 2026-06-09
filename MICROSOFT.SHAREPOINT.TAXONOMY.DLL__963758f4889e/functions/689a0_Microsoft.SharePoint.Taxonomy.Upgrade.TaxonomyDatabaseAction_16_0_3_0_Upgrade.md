# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_3_0::Upgrade

- ea: `0x689a0`
- end: `0x689d6`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_3_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x689cb`: `Updated database with new SQL indexes.`
- `0x689b6`: `\n-- IX_ECMTermProperty_TermId\n\nIF NOT EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE object_id = object_id(N'[dbo].[ECMTermProperty]') AND name = 'IX_ECMTermProperty_TermId')\nBEGIN\n\n    CREATE NONCLUSTERED INDEX [IX_ECMTermProperty_TermId] ON [dbo].[ECMTermProperty] ([TermId]) \n\nEND\nGO\n\nIF (EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE fill_factor <> 100 AND name='IX_ECMTermProperty_TermId' AND object_id=object_id(N'[dbo].[ECMTermProperty]'))\nOR EXISTS (SELECT TOP 1 1 FROM`

## pseudocode

```c

```
