# System.Xaml.XmlCompatibilityReader::ShouldIgnoreNamespace

- ea: `0x11010`
- end: `0x11034`
- name: `System.Xaml.XmlCompatibilityReader::ShouldIgnoreNamespace`
- size: `36`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10900`
- `0x10a40`
- `0x10b80`
- `0x10bb0`
- `0x10c10`
- `0x10c60`
- `0x11080`
- `0x110b0`
- `0x11570`

## callees

- `0x10fc0`
- `0x11010`
- `0x117e0`
- `0x119a0`
- `0x2ee20`

## pseudocode

```c

```

## disassembly

```asm
0x11010  ldarg.0
0x11011  ldarg.1
0x11012  call     instance bool System.Xaml.XmlCompatibilityReader::IsNamespaceKnown(string namespaceName)
0x11017  brfalse.s loc_11025
0x11019  ldarg.1
0x1101a  ldarg.0
0x1101b  call     instance string System.Xaml.XmlCompatibilityReader::get_CompatibilityUri()
0x11020  ceq
0x11022  stloc.0
0x11023  br.s     loc_11032
0x11025  ldarg.0
0x11026  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x1102b  ldarg.1
0x1102c  callvirt instance bool CompatibilityScope::CanIgnore(string namespaceName)
0x11031  stloc.0
0x11032  ldloc.0
0x11033  ret
```
