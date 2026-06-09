# operator delete(void *,unsigned __int64)

- ea: `0x1400017c4`
- end: `0x1400017c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002c90`
- `0x140002cd0`
- `0x140005ff0`
- `0x140006030`

## callees

- `0x140001dc0`

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
0x1400017c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
