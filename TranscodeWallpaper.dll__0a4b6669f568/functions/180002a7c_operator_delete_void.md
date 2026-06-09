# operator delete(void *)

- ea: `0x180002a7c`
- end: `0x180002a81`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002540`
- `0x180002550`
- `0x180002b00`

## callees

- `0x180002c84`

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
0x180002a7c  jmp     free
```
