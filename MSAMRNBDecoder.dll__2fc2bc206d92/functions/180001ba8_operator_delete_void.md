# operator delete(void *)

- ea: `0x180001ba8`
- end: `0x180001bad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001468`
- `0x180001af0`
- `0x180001e70`

## callees

- `0x180001f36`

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
0x180001ba8  jmp     free
```
