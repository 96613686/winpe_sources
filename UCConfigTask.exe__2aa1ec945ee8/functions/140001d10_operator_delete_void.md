# operator delete(void *)

- ea: `0x140001d10`
- end: `0x140001d15`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001754`
- `0x140001760`
- `0x140001e60`

## callees

- `0x140002054`

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
0x140001d10  jmp     free
```
