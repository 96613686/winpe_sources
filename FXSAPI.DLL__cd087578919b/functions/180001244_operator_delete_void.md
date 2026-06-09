# operator delete(void *)

- ea: `0x180001244`
- end: `0x180001249`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001750`
- `0x180001fe8`
- `0x1800035e0`
- `0x180003610`

## callees

- `0x180001b74`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001244  jmp     free_0
```
