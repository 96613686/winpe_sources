# operator delete(void *)

- ea: `0x180003f1c`
- end: `0x180003f21`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003a70`
- `0x180003a80`
- `0x18000c928`

## callees

- `0x180004030`

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
0x180003f1c  jmp     free
```
