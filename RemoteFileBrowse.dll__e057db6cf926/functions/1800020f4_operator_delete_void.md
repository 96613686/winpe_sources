# operator delete(void *)

- ea: `0x1800020f4`
- end: `0x1800020f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002054`
- `0x180002060`
- `0x180014a38`
- `0x180014b2c`

## callees

- `0x180002d94`

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
0x1800020f4  jmp     free
```
