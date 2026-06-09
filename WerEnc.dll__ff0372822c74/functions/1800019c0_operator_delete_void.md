# operator delete(void *)

- ea: `0x1800019c0`
- end: `0x1800019c5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001424`
- `0x180001e10`
- `0x180001ee0`

## callees

- `0x180001fb4`

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
0x1800019c0  jmp     free
```
