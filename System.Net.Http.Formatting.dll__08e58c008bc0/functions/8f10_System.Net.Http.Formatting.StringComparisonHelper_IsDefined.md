# System.Net.Http.Formatting.StringComparisonHelper::IsDefined

- ea: `0x8f10`
- end: `0x8f2a`
- name: `System.Net.Http.Formatting.StringComparisonHelper::IsDefined`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8f30`

## callees

- `0x8f10`

## pseudocode

```c

```

## disassembly

```asm
0x8f10  ldarg.0
0x8f11  brfalse.s loc_8F28
0x8f13  ldarg.0
0x8f14  ldc.i4.1
0x8f15  beq.s    loc_8F28
0x8f17  ldarg.0
0x8f18  ldc.i4.2
0x8f19  beq.s    loc_8F28
0x8f1b  ldarg.0
0x8f1c  ldc.i4.3
0x8f1d  beq.s    loc_8F28
0x8f1f  ldarg.0
0x8f20  ldc.i4.4
0x8f21  beq.s    loc_8F28
0x8f23  ldarg.0
0x8f24  ldc.i4.5
0x8f25  ceq
0x8f27  ret
0x8f28  ldc.i4.1
0x8f29  ret
```
