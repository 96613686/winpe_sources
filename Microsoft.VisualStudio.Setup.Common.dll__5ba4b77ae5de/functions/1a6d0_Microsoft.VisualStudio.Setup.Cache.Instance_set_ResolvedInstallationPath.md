# Microsoft.VisualStudio.Setup.Cache.Instance::set_ResolvedInstallationPath

- ea: `0x1a6d0`
- end: `0x1a6e8`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_ResolvedInstallationPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a6d8`: `ResolvedInstallationPath`

## pseudocode

```c

```

## disassembly

```asm
0x1a6d0  ldarg.0
0x1a6d1  ldarg.0
0x1a6d2  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::resolvedInstallationPath
0x1a6d7  ldarg.1
0x1a6d8  ldstr    aResolvedinstal// "ResolvedInstallationPath"
0x1a6dd  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1a6e2  call     T0x2B0000C9
0x1a6e7  ret
```
