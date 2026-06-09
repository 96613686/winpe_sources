# operator delete(void *)

- ea: `0x180001e8c`
- end: `0x180001e91`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001940`
- `0x180001950`

## callees

- `0x180001fae`

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
0x180001e8c  jmp     free
```
