# Microsoft.VisualStudio.Setup.CatalogInfo::set_ManifestName

- ea: `0x2b40`
- end: `0x2b4d`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::set_ManifestName`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4df0`

## string_xrefs

- `0x2b41`: `ManifestName`

## pseudocode

```c

```

## disassembly

```asm
0x2b40  ldarg.0
0x2b41  ldstr    aManifestname// "ManifestName"
0x2b46  ldarg.1
0x2b47  call     instance void Microsoft.VisualStudio.Setup.ExtensibleObject::set_Item(string key, string value)
0x2b4c  ret
```
