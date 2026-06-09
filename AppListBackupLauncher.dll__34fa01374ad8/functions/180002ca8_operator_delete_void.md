# operator delete(void *)

- ea: `0x180002ca8`
- end: `0x180002cad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002738`
- `0x180002750`

## callees

- `0x180002da4`

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
0x180002ca8  jmp     free
```
