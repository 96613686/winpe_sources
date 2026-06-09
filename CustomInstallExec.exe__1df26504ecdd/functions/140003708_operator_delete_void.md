# operator delete(void *)

- ea: `0x140003708`
- end: `0x14000370d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003644`
- `0x140003650`
- `0x14000c600`

## callees

- `0x140003f44`

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
0x140003708  jmp     free
```
