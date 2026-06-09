# operator delete[](void *,unsigned __int64)

- ea: `0x1800017e4`
- end: `0x1800017e9`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a0a0`
- `0x18000e73d`

## callees

- `0x180001c6c`

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
0x1800017e4  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
