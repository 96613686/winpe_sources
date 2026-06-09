# Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::.cctor

- ea: `0xe120`
- end: `0xe135`
- name: `Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0xe12a`: `UpdateUri`

## pseudocode

```c

```

## disassembly

```asm
0xe120  ldstr    aInfo_0// "Info"
0xe125  stsfld   string Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::CatalogInfoKey
0xe12a  ldstr    aUpdateuri// "UpdateUri"
0xe12f  stsfld   string Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::UpdateUriKey
0xe134  ret
```
