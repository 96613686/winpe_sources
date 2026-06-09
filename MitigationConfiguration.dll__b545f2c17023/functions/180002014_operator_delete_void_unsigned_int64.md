# operator delete(void *,unsigned __int64)

- ea: `0x180002014`
- end: `0x180002019`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800037c0`
- `0x180003800`
- `0x180003840`
- `0x180003880`
- `0x180007398`
- `0x1800076b4`
- `0x180007720`
- `0x18000a5f0`
- `0x1800105a0`
- `0x180011028`
- `0x1800120e4`
- `0x1800121d4`

## callees

- `0x180002508`

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
0x180002014  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
