# System.Range::Equals_0

- ea: `0x2c0`
- end: `0x2ef`
- name: `System.Range::Equals_0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1d0`
- `0x250`
- `0x260`
- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldarga.s 1
0x2c2  call     instance valuetype System.Index System.Range::get_Start()
0x2c7  stloc.0
0x2c8  ldloca.s 0
0x2ca  ldarg.0
0x2cb  call     instance valuetype System.Index System.Range::get_Start()
0x2d0  call     instance bool System.Index::Equals(valuetype System.Index other)
0x2d5  brfalse.s loc_2ED
0x2d7  ldarga.s 1
0x2d9  call     instance valuetype System.Index System.Range::get_End()
0x2de  stloc.0
0x2df  ldloca.s 0
0x2e1  ldarg.0
0x2e2  call     instance valuetype System.Index System.Range::get_End()
0x2e7  call     instance bool System.Index::Equals(valuetype System.Index other)
0x2ec  ret
0x2ed  ldc.i4.0
0x2ee  ret
```
