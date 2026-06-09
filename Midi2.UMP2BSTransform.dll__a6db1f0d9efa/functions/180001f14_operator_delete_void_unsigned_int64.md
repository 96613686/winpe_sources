# operator delete(void *,unsigned __int64)

- ea: `0x180001f14`
- end: `0x180001f19`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003494`
- `0x1800037d0`
- `0x180003840`
- `0x1800038b0`
- `0x1800038f0`
- `0x180003930`
- `0x180003d48`
- `0x180004820`
- `0x180004d70`
- `0x1800074f0`
- `0x180008c2c`
- `0x180008dc0`
- `0x180008e20`
- `0x180008ea0`
- `0x180008f00`
- `0x180009f2c`
- `0x180009fa0`
- `0x180009fd0`
- `0x18000a4f0`
- `0x18000a65c`
- `0x18000a8ec`
- `0x18000e1ec`

## callees

- `0x180001ed4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001f14  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
