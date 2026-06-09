# Microsoft.VisualStudio.Setup.Extensions::GetManifestId

- ea: `0x5fb0`
- end: `0x5fc7`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetManifestId`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x8ce0`
- `0x8d20`
- `0x9940`

## callees

- `0x2b10`
- `0x5fb0`
- `0x6d30`

## pseudocode

```c

```

## disassembly

```asm
0x5fb0  ldarg.0
0x5fb1  brtrue.s loc_5FB5
0x5fb3  ldnull
0x5fb4  ret
0x5fb5  ldarg.0
0x5fb6  callvirt instance class Microsoft.VisualStudio.Setup.CatalogInfo Microsoft.VisualStudio.Setup.IManifest::get_Info()
0x5fbb  dup
0x5fbc  brtrue.s loc_5FC1
0x5fbe  pop
0x5fbf  ldnull
0x5fc0  ret
0x5fc1  call     instance string Microsoft.VisualStudio.Setup.CatalogInfo::get_Id()
0x5fc6  ret
```
