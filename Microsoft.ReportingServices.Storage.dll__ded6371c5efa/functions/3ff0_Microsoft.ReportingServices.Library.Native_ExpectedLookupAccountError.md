# Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError

- ea: `0x3ff0`
- end: `0x4018`
- name: `Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4020`
- `0x4150`

## callees

- `0x3ff0`

## pseudocode

```c

```

## disassembly

```asm
0x3ff0  ldarg.0
0x3ff1  ldc.i4   0x534
0x3ff6  beq.s    loc_4016
0x3ff8  ldarg.0
0x3ff9  ldc.i4   0x6FC
0x3ffe  beq.s    loc_4016
0x4000  ldarg.0
0x4001  ldc.i4   0x6FD
0x4006  beq.s    loc_4016
0x4008  ldarg.0
0x4009  ldc.i4.s 0x57
0x400b  beq.s    loc_4016
0x400d  ldarg.0
0x400e  ldc.i4   0x6BF
0x4013  ceq
0x4015  ret
0x4016  ldc.i4.1
0x4017  ret
```
