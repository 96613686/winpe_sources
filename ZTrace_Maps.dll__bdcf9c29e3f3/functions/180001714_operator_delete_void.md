# operator delete(void *)

- ea: `0x180001714`
- end: `0x180001719`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e40`
- `0x1800021b0`
- `0x180002420`

## callees

- `0x1800022a6`

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
0x180001714  jmp     free
```
