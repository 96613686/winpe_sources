# System.Index::ToString

- ea: `0x200`
- end: `0x21e`
- name: `System.Index::ToString`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x160`
- `0x180`
- `0x200`
- `0x220`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldarg.0
0x201  call     instance bool System.Index::get_IsFromEnd()
0x206  brfalse.s loc_20F
0x208  ldarg.0
0x209  call     instance string System.Index::ToStringFromEnd()
0x20e  ret
0x20f  ldarg.0
0x210  call     instance int32 System.Index::get_Value()
0x215  stloc.0
0x216  ldloca.s 0
0x218  call     instance string [mscorlib]System.UInt32::ToString()
0x21d  ret
```
