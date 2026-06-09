# operator delete(void *)

- ea: `0x140001688`
- end: `0x14000168d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400016c4`
- `0x1400019c0`

## callees

- `0x140002114`

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
0x140001688  jmp     free
```
