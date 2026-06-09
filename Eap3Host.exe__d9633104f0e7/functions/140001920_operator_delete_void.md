# operator delete(void *)

- ea: `0x140001920`
- end: `0x140001925`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001354`
- `0x140001d40`
- `0x140001e10`

## callees

- `0x140001f5c`

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
0x140001920  jmp     free
```
