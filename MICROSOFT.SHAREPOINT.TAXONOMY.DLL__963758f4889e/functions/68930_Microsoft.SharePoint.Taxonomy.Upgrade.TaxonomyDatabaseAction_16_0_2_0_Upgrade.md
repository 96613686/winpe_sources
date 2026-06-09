# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_2_0::Upgrade

- ea: `0x68930`
- end: `0x68966`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_2_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x6895b`: `Updated database with new SQL indexes.`
- `0x68946`: `\n-- IX_ECMTermSet_TermId [sic]\n\nIF NOT EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE object_id = object_id(N'[dbo].[ECMTermLabel]') AND name = 'IX_ECMTermSet_TermId')\nBEGIN\n\n    CREATE NONCLUSTERED INDEX [IX_ECMTermSet_TermId] ON [dbo].[ECMTermLabel] ([TermId]) \n\nEND\nGO\n\nIF (EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE fill_factor <> 95 AND name='IX_ECMTermSet_TermId' AND object_id=object_id(N'[dbo].[ECMTermLabel]'))\nOR EXISTS (SELECT TOP 1 1 FROM sys.stats WHERE no_reco`

## pseudocode

```c

```
