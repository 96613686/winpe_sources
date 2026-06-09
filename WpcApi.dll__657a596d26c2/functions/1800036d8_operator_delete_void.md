# operator delete(void *)

- ea: `0x1800036d8`
- end: `0x1800036dd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800036e4`
- `0x1800036f0`
- `0x18000b6e0`
- `0x18000ba00`

## callees

- `0x180003ce4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1800036d8  jmp     free
```
