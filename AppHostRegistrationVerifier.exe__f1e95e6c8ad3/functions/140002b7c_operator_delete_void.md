# operator delete(void *)

- ea: `0x140002b7c`
- end: `0x140002b81`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002504`
- `0x140002510`
- `0x140009e54`

## callees

- `0x140002d14`

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
0x140002b7c  jmp     free
```
