# operator delete[](void *,unsigned __int64)

- ea: `0x1800018e4`
- end: `0x1800018e9`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003f20`
- `0x180003fb8`
- `0x1800075ac`
- `0x180027e53`
- `0x180027ebb`

## callees

- `0x180001894`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800018e4  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
