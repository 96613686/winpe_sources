# operator delete(void *,unsigned __int64)

- ea: `0x140001714`
- end: `0x140001719`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002ca0`
- `0x140002ce0`
- `0x140006314`
- `0x140006420`
- `0x140006444`
- `0x140007650`

## callees

- `0x140001468`

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
0x140001714  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
