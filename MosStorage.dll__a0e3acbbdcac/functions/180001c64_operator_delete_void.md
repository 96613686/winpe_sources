# operator delete(void *)

- ea: `0x180001c64`
- end: `0x180001c69`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002050`
- `0x18000207c`
- `0x180003b90`
- `0x180003bd0`
- `0x180006f80`

## callees

- `0x1800027c6`

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
0x180001c64  jmp     free
```
