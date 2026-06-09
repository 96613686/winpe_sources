# operator delete(void *)

- ea: `0x180002560`
- end: `0x180002565`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002434`
- `0x180002440`
- `0x180006aa8`

## callees

- `0x180002b24`

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
0x180002560  jmp     free
```
