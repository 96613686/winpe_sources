# operator delete(void *)

- ea: `0x1400029a8`
- end: `0x1400029ad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400029e4`
- `0x140002d80`

## callees

- `0x1400034f4`

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
0x1400029a8  jmp     free
```
