# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_5_0::Upgrade

- ea: `0x68a80`
- end: `0x68ab6`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_5_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x68aab`: `Updated database with new SQL indexes.`
- `0x68a96`: `\n-- IX_ECMUsedTerms_TermId\n\nIF NOT EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE object_id = object_id(N'[dbo].[ECMUsedTerms]') AND name = 'IX_ECMUsedTerms_TermId')\nBEGIN\n\n    CREATE NONCLUSTERED INDEX [IX_ECMUsedTerms_TermId] ON [dbo].[ECMUsedTerms] ([TermId]) \n\nEND\nGO\n\n\nIF (EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE fill_factor <> 95 AND name='IX_ECMUsedTerms_TermId' AND object_id=object_id(N'[dbo].[ECMUsedTerms]'))\nOR EXISTS (SELECT TOP 1 1 FROM sys.stats WHERE no`

## pseudocode

```c

```
