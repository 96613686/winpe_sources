# operator delete[](void *)

- ea: `0x180001fe8`
- end: `0x180001fed`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003291c`

## callees

- `0x180001244`

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
0x180001fe8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
