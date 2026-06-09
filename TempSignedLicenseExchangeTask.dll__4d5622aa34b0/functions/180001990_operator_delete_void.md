# operator delete(void *)

- ea: `0x180001990`
- end: `0x180001995`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001424`
- `0x180001ad0`
- `0x180001e50`

## callees

- `0x180001f3a`

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
0x180001990  jmp     free
```
