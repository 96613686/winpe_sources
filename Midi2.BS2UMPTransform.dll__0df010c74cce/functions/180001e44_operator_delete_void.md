# operator delete(void *)

- ea: `0x180001e44`
- end: `0x180001e49`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e84`
- `0x1800022b0`

## callees

- `0x1800028a4`

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
0x180001e44  jmp     free
```
