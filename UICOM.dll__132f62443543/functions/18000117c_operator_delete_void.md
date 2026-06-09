# operator delete[](void *)

- ea: `0x18000117c`
- end: `0x180001181`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002448`
- `0x180003580`

## callees

- `0x180001170`

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
0x18000117c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
