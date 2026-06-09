# operator delete(void *)

- ea: `0x180001d30`
- end: `0x180001d35`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001cb0`
- `0x1800022e0`
- `0x1800023a0`

## callees

- `0x1800024a4`

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
0x180001d30  jmp     free
```
