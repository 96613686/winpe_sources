# Microsoft.VisualStudio.Setup.CatalogInfo::get_ManifestType

- ea: `0x2b50`
- end: `0x2b5c`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::get_ManifestType`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x6060`

## callees

- `0x4dd0`

## string_xrefs

- `0x2b51`: `ManifestType`

## pseudocode

```c

```

## disassembly

```asm
0x2b50  ldarg.0
0x2b51  ldstr    aManifesttype// "ManifestType"
0x2b56  call     instance string Microsoft.VisualStudio.Setup.ExtensibleObject::get_Item(string key)
0x2b5b  ret
```
