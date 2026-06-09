# Microsoft.VisualStudio.Setup.CatalogInfo::set_ManifestType

- ea: `0x2b60`
- end: `0x2b6d`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::set_ManifestType`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x4df0`

## string_xrefs

- `0x2b61`: `ManifestType`

## pseudocode

```c

```

## disassembly

```asm
0x2b60  ldarg.0
0x2b61  ldstr    aManifesttype// "ManifestType"
0x2b66  ldarg.1
0x2b67  call     instance void Microsoft.VisualStudio.Setup.ExtensibleObject::set_Item(string key, string value)
0x2b6c  ret
```
