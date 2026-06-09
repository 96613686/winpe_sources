# Microsoft.VisualStudio.Setup.Extensions::GetManifestId_0

- ea: `0x5fd0`
- end: `0x5fe7`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetManifestId_0`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x16c00`
- `0x16e40`
- `0x170e0`

## callees

- `0x5fd0`
- `0x80d0`
- `0x98b0`

## pseudocode

```c

```

## disassembly

```asm
0x5fd0  ldarg.0
0x5fd1  brtrue.s loc_5FD5
0x5fd3  ldnull
0x5fd4  ret
0x5fd5  ldarg.0
0x5fd6  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x5fdb  dup
0x5fdc  brtrue.s loc_5FE1
0x5fde  pop
0x5fdf  ldnull
0x5fe0  ret
0x5fe1  call     instance string Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestId()
0x5fe6  ret
```
