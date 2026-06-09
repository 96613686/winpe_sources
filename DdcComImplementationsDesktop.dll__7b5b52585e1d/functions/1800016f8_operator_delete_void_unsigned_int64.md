# operator delete(void *,unsigned __int64)

- ea: `0x1800016f8`
- end: `0x1800016fd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002310`
- `0x180002360`
- `0x180002778`
- `0x1800027e4`
- `0x1800031c0`
- `0x180003f20`
- `0x180004070`
- `0x180006000`
- `0x180006040`
- `0x180006080`

## callees

- `0x180001694`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800016f8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
