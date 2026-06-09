# operator delete(void *)

- ea: `0x180002b2c`
- end: `0x180002b31`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002af0`
- `0x180002b00`

## callees

- `0x180003274`

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
0x180002b2c  jmp     free
```
