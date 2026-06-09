# operator delete(void *)

- ea: `0x180001cbc`
- end: `0x180001cc1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e70`
- `0x180001f30`
- `0x1800028b0`

## callees

- `0x180001c96`

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
0x180001cbc  jmp     free
```
