# operator delete(void *)

- ea: `0x140002b10`
- end: `0x140002b15`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400025a4`
- `0x14002606c`

## callees

- `0x140002ca4`

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
0x140002b10  jmp     free
```
