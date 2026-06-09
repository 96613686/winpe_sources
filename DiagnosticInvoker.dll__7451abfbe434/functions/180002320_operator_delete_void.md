# operator delete(void *)

- ea: `0x180002320`
- end: `0x180002325`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800022c0`
- `0x1800022d0`
- `0x1800028e0`

## callees

- `0x180002a74`

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
0x180002320  jmp     free
```
