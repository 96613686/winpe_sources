# operator delete[](void *)

- ea: `0x180006b80`
- end: `0x180006b85`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007a38`
- `0x180007cdc`
- `0x1800085d4`

## callees

- `0x180006b74`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180006b80  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
