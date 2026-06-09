# operator delete(void *)

- ea: `0x1800022a0`
- end: `0x1800022a5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001cd4`
- `0x1800026e0`
- `0x1800027b0`
- `0x180003fa0`

## callees

- `0x1800028b4`

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
0x1800022a0  jmp     free
```
