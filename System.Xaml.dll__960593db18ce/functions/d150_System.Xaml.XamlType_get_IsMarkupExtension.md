# System.Xaml.XamlType::get_IsMarkupExtension

- ea: `0xd150`
- end: `0xd158`
- name: `System.Xaml.XamlType::get_IsMarkupExtension`
- size: `8`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x2ca0`
- `0x33d0`
- `0x3c80`
- `0x3e90`
- `0xbd10`
- `0xd3d0`
- `0xed00`
- `0x10110`
- `0x246d0`
- `0x28a00`
- `0x299b0`
- `0x2a3f0`
- `0x2ac60`
- `0x2de50`
- `0x35c10`

## callees

- `0xe910`

## pseudocode

```c

```

## disassembly

```asm
0xd150  ldarg.0
0xd151  ldc.i4.4
0xd152  call     instance bool System.Xaml.XamlType::GetFlag(valuetype System.Xaml.BoolTypeBits flagBit)
0xd157  ret
```
