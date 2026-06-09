# operator delete(void *)

- ea: `0x18000343c`
- end: `0x180003441`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002f90`
- `0x180002fa0`

## callees

- `0x180003534`

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
0x18000343c  jmp     free
```
