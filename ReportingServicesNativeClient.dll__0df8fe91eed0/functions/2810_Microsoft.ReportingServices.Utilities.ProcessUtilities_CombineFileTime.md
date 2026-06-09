# Microsoft.ReportingServices.Utilities.ProcessUtilities::CombineFileTime

- ea: `0x2810`
- end: `0x281f`
- name: `Microsoft.ReportingServices.Utilities.ProcessUtilities::CombineFileTime`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2720`

## pseudocode

```c

```

## disassembly

```asm
0x2810  ldarga.s 0
0x2812  ldc.i4.4
0x2813  add
0x2814  ldind.i4
0x2815  conv.u8
0x2816  ldc.i4.s 0x20
0x2818  shl
0x2819  ldarga.s 0
0x281b  ldind.i4
0x281c  conv.u8
0x281d  or
0x281e  ret
```
