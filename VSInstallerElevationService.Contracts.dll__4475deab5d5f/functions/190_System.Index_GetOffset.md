# System.Index::GetOffset

- ea: `0x190`
- end: `0x1a7`
- name: `System.Index::GetOffset`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180`
- `0x190`

## pseudocode

```c

```

## disassembly

```asm
0x190  ldarg.0
0x191  ldfld    int32 System.Index::_value
0x196  stloc.0
0x197  ldarg.0
0x198  call     instance bool System.Index::get_IsFromEnd()
0x19d  brfalse.s loc_1A5
0x19f  ldloc.0
0x1a0  ldarg.1
0x1a1  ldc.i4.1
0x1a2  add
0x1a3  add
0x1a4  stloc.0
0x1a5  ldloc.0
0x1a6  ret
```
