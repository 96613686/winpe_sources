# operator delete(void *)

- ea: `0x180001950`
- end: `0x180001955`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001944`
- `0x180001f40`
- `0x180002010`

## callees

- `0x180002134`

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
0x180001950  jmp     free
```
