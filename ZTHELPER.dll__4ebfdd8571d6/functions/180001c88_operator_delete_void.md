# operator delete(void *)

- ea: `0x180001c88`
- end: `0x180001c8d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001518`
- `0x180001bd0`
- `0x180001f50`

## callees

- `0x180002046`

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
0x180001c88  jmp     free
```
