# operator delete[](void *)

- ea: `0x180004d44`
- end: `0x180004d49`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005230`
- `0x180005474`
- `0x1800056d4`
- `0x180005b70`
- `0x180005f60`
- `0x180006210`

## callees

- `0x18000437c`

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
0x180004d44  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
