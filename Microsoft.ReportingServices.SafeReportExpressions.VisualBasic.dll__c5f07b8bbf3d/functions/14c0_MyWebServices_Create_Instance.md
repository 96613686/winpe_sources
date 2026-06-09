# MyWebServices::Create__Instance__

- ea: `0x14c0`
- end: `0x14d4`
- name: `MyWebServices::Create__Instance__`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  ldarg.0
0x14c1  box      mvar<u1>
0x14c6  brtrue.s loc_14D0
0x14c8  call     T0x2B000001
0x14cd  stloc.0
0x14ce  br.s     loc_14D2
0x14d0  ldarg.0
0x14d1  stloc.0
0x14d2  ldloc.0
0x14d3  ret
```
