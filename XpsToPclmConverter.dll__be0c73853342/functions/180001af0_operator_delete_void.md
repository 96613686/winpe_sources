# operator delete(void *)

- ea: `0x180001af0`
- end: `0x180001af5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a90`
- `0x180001aa0`
- `0x18000d9fc`

## callees

- `0x1800020f4`

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
0x180001af0  jmp     free
```
