# operator delete(void *,unsigned __int64)

- ea: `0x1400023b4`
- end: `0x1400023b9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400039b0`
- `0x1400039f0`
- `0x1400073c0`
- `0x1400074b8`
- `0x14000760c`
- `0x140007710`
- `0x14000782c`
- `0x1400079a0`
- `0x140007ad8`
- `0x140007c18`
- `0x140007ec8`
- `0x14000877c`
- `0x1400087e4`
- `0x140008f20`
- `0x140008f60`
- `0x140008fa0`
- `0x140009010`
- `0x140009070`
- `0x1400090d0`
- `0x140009100`
- `0x140009150`
- `0x140009d9c`

## callees

- `0x140002a80`

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
0x1400023b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
