# System.Range::Equals

- ea: `0x280`
- end: `0x2be`
- name: `System.Range::Equals`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1d0`
- `0x250`
- `0x260`
- `0x280`

## pseudocode

```c

```

## disassembly

```asm
0x280  ldarg.1
0x281  isinst   System.Range
0x286  brfalse.s loc_2BC
0x288  ldarg.1
0x289  unbox.any System.Range
0x28e  stloc.0
0x28f  ldloca.s 0
0x291  call     instance valuetype System.Index System.Range::get_Start()
0x296  stloc.1
0x297  ldloca.s 1
0x299  ldarg.0
0x29a  call     instance valuetype System.Index System.Range::get_Start()
0x29f  call     instance bool System.Index::Equals(valuetype System.Index other)
0x2a4  brfalse.s loc_2BC
0x2a6  ldloca.s 0
0x2a8  call     instance valuetype System.Index System.Range::get_End()
0x2ad  stloc.1
0x2ae  ldloca.s 1
0x2b0  ldarg.0
0x2b1  call     instance valuetype System.Index System.Range::get_End()
0x2b6  call     instance bool System.Index::Equals(valuetype System.Index other)
0x2bb  ret
0x2bc  ldc.i4.0
0x2bd  ret
```
