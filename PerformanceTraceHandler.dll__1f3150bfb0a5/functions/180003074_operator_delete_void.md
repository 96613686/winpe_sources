# operator delete(void *)

- ea: `0x180003074`
- end: `0x180003079`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002fd0`
- `0x180002fe0`
- `0x18000b464`

## callees

- `0x1800036d4`

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
0x180003074  jmp     free
```
