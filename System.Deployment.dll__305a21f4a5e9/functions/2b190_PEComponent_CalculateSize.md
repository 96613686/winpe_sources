# PEComponent::CalculateSize

- ea: `0x2b190`
- end: `0x2b198`
- name: `PEComponent::CalculateSize`
- size: `8`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2b1b0`
- `0x2b2a0`
- `0x2b310`
- `0x2b3c0`
- `0x2b530`
- `0x2b5b0`
- `0x2b6f0`
- `0x2b9d0`
- `0x2bb00`
- `0x2bc60`

## pseudocode

```c

```

## disassembly

```asm
0x2b190  ldarg.1
0x2b191  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x2b196  conv.i8
0x2b197  ret
```
