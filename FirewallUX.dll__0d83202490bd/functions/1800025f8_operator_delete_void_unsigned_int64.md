# operator delete(void *,unsigned __int64)

- ea: `0x1800025f8`
- end: `0x1800025fd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `78`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800056ec`
- `0x1800058ec`
- `0x180005974`
- `0x180005ee0`
- `0x180005f1c`
- `0x180005f5c`
- `0x180005f98`
- `0x180005fe0`
- `0x180006040`
- `0x1800060a0`
- `0x1800060e0`
- `0x180006b20`
- `0x180008db0`
- `0x180008e74`
- `0x180008f10`
- `0x180008f90`
- `0x18000b57c`
- `0x18000c4f0`
- `0x18000c730`
- `0x18000c8c4`
- `0x18000e324`
- `0x18000f098`
- `0x18000f30c`
- `0x18000fa60`
- `0x1800130e0`
- `0x180016448`
- `0x1800165b4`
- `0x1800165e8`
- `0x1800166a8`
- `0x1800166cc`
- `0x180016948`
- `0x1800170e0`
- `0x180017150`
- `0x1800171c0`
- `0x180017210`
- `0x180017250`
- `0x180017290`
- `0x1800172d0`
- `0x180017310`
- `0x180017350`
- `0x180017390`
- `0x1800173d0`
- `0x180017410`
- `0x180017438`
- `0x180017470`
- `0x1800174b0`
- `0x1800174f0`
- `0x180017530`
- `0x180018060`
- `0x1800180f0`

## callees

- `0x180002ad4`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800025f8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
