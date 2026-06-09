# operator delete(void *)

- ea: `0x180001d0c`
- end: `0x180001d11`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001cc8`
- `0x180001ce0`

## callees

- `0x1800026b4`

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
0x180001d0c  jmp     free
```
