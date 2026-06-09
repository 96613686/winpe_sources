# operator delete[](void *,unsigned __int64)

- ea: `0x180002adc`
- end: `0x180002ae1`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015b38`
- `0x180015c1c`
- `0x1800197d0`
- `0x1800375f0`
- `0x180037659`

## callees

- `0x180001bf8`

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
0x180002adc  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
