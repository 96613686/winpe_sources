# operator delete(void *)

- ea: `0x180001478`
- end: `0x18000147d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001420`
- `0x180008cf0`
- `0x18001fe18`

## callees

- `0x180002114`

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
0x180001478  jmp     free
```
