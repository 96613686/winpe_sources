# operator delete[](void *)

- ea: `0x180001fd4`
- end: `0x180001fd9`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005c9c`

## callees

- `0x180001fbc`

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
0x180001fd4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
