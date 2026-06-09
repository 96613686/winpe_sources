# Microsoft.VisualStudio.Setup.CatalogInfo::get_ManifestName

- ea: `0x2b30`
- end: `0x2b3c`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::get_ManifestName`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x27c0`
- `0x6020`
- `0x1aec0`

## callees

- `0x4dd0`

## string_xrefs

- `0x2b31`: `ManifestName`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  ldstr    aManifestname// "ManifestName"
0x2b36  call     instance string Microsoft.VisualStudio.Setup.ExtensibleObject::get_Item(string key)
0x2b3b  ret
```
