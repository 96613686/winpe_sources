# operator delete[](void *,unsigned __int64)

- ea: `0x180002714`
- end: `0x180002719`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d860`
- `0x18001791a`

## callees

- `0x180002b9c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180002714  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
