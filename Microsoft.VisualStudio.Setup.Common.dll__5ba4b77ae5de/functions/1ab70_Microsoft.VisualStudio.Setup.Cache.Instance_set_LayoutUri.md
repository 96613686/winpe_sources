# Microsoft.VisualStudio.Setup.Cache.Instance::set_LayoutUri

- ea: `0x1ab70`
- end: `0x1ab88`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_LayoutUri`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1ab78`: `LayoutUri`

## pseudocode

```c

```

## disassembly

```asm
0x1ab70  ldarg.0
0x1ab71  ldarg.0
0x1ab72  ldflda   class [System]System.Uri Microsoft.VisualStudio.Setup.Cache.Instance::layoutUri
0x1ab77  ldarg.1
0x1ab78  ldstr    aLayouturi// "LayoutUri"
0x1ab7d  ldsfld   class Microsoft.VisualStudio.Setup.UriStrictEqualityComparer Microsoft.VisualStudio.Setup.Cache.Instance::UriComparer
0x1ab82  call     T0x2B0000CC
0x1ab87  ret
```
