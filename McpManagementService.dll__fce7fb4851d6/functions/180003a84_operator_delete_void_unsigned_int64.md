# operator delete(void *,unsigned __int64)

- ea: `0x180003a84`
- end: `0x180003a89`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `40`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005888`
- `0x180005be8`
- `0x180006804`
- `0x180007d00`
- `0x180007d30`
- `0x180007d70`
- `0x180007db0`
- `0x180007df0`
- `0x180007e30`
- `0x180007e70`
- `0x180007ea0`
- `0x180007ed0`
- `0x180007f10`
- `0x180007f50`
- `0x180007f90`
- `0x180007fd0`
- `0x180008010`
- `0x18000804c`
- `0x180008088`
- `0x1800080d0`
- `0x18000d69c`
- `0x180012628`
- `0x180012d24`
- `0x180012d60`
- `0x180012db0`
- `0x180012df0`
- `0x180012e30`
- `0x180021aa0`
- `0x180021ae0`
- `0x180022178`
- `0x180022380`
- `0x1800223c0`
- `0x180022400`
- `0x180022d60`
- `0x180023a00`
- `0x180024b90`
- `0x180025670`
- `0x180027ec2`
- `0x180028298`
- `0x1800285b1`

## callees

- `0x180003eb4`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180003a84  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
