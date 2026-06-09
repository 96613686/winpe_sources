# operator delete(void *)

- ea: `0x1800014a8`
- end: `0x1800014ad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001450`
- `0x180008db0`
- `0x18001fed8`

## callees

- `0x180002144`

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
0x1800014a8  jmp     free
```
