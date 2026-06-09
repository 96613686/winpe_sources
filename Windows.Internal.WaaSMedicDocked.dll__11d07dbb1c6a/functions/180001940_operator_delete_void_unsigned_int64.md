# operator delete(void *,unsigned __int64)

- ea: `0x180001940`
- end: `0x180001945`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e30`
- `0x180002e70`
- `0x180006830`
- `0x1800068d0`
- `0x180006a80`
- `0x180006ac0`
- `0x180006b30`
- `0x180006ba0`
- `0x180008230`
- `0x180008d58`
- `0x180008df0`
- `0x180008f20`
- `0x180008fa0`
- `0x180009c04`
- `0x180009fc0`
- `0x18000a160`
- `0x18000a768`
- `0x18000a7d0`
- `0x18000ade0`
- `0x18000ba53`

## callees

- `0x180001e8c`

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
0x180001940  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
