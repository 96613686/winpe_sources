# Microsoft.VisualStudio.Setup.Cache.ProductReference::set_SupportsExtensions

- ea: `0x1bdd0`
- end: `0x1bde3`
- name: `Microsoft.VisualStudio.Setup.Cache.ProductReference::set_SupportsExtensions`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1bcd0`

## string_xrefs

- `0x1bdd8`: `SupportsExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x1bdd0  ldarg.0
0x1bdd1  ldarg.0
0x1bdd2  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Cache.ProductReference::supportsExtensions
0x1bdd7  ldarg.1
0x1bdd8  ldstr    aSupportsextens// "SupportsExtensions"
0x1bddd  call     T0x2B0000D4
0x1bde2  ret
```
