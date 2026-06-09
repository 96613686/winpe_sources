# operator delete(void *)

- ea: `0x180001544`
- end: `0x180001549`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001930`
- `0x180001940`
- `0x1800020f0`

## callees

- `0x180001ece`

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
0x180001544  jmp     free
```
