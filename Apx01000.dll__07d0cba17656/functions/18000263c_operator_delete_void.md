# operator delete(void *)

- ea: `0x18000263c`
- end: `0x180002641`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002100`
- `0x180002110`

## callees

- `0x1800027a4`

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
0x18000263c  jmp     free
```
