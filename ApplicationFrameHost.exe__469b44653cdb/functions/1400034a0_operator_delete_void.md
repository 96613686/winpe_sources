# operator delete(void *)

- ea: `0x1400034a0`
- end: `0x1400034a5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003444`
- `0x140003450`
- `0x140003bb0`

## callees

- `0x140003d94`

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
0x1400034a0  jmp     free
```
