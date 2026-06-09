# Microsoft.VisualStudio.Setup.Extensions::IsDowngradable

- ea: `0x5ec0`
- end: `0x5ecd`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsDowngradable`
- size: `13`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x9c90`
- `0x14920`
- `0x15a20`
- `0x172e0`
- `0x173e0`
- `0x17660`
- `0x1d3c0`

## callees

- `0x8090`

## pseudocode

```c

```

## disassembly

```asm
0x5ec0  ldarg.0
0x5ec1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x5ec6  ldnull
0x5ec7  ceq
0x5ec9  ldc.i4.0
0x5eca  ceq
0x5ecc  ret
```
