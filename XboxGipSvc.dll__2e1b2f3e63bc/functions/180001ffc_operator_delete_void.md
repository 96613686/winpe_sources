# operator delete(void *)

- ea: `0x180001ffc`
- end: `0x180002001`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b6c`
- `0x1800021d0`
- `0x18000c888`

## callees

- `0x180002110`

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
0x180001ffc  jmp     free
```
