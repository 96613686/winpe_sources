# Microsoft.VisualStudio.Setup.Cache.ProductReference::set_IsInstalled

- ea: `0x1bd80`
- end: `0x1bd93`
- name: `Microsoft.VisualStudio.Setup.Cache.ProductReference::set_IsInstalled`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1bca0`

## string_xrefs

- `0x1bd88`: `IsInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x1bd80  ldarg.0
0x1bd81  ldarg.0
0x1bd82  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Cache.ProductReference::isInstalled
0x1bd87  ldarg.1
0x1bd88  ldstr    aIsinstalled// "IsInstalled"
0x1bd8d  call     T0x2B0000D4
0x1bd92  ret
```
