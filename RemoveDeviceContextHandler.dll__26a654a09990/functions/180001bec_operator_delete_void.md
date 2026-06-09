# operator delete[](void *)

- ea: `0x180001bec`
- end: `0x180001bf1`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006468`
- `0x180006e1c`

## callees

- `0x180001be0`

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
0x180001bec  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
