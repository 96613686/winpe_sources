# operator delete(void *)

- ea: `0x140002988`
- end: `0x14000298d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400023f4`
- `0x140002400`
- `0x140002d70`

## callees

- `0x140002f84`

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
0x140002988  jmp     free
```
