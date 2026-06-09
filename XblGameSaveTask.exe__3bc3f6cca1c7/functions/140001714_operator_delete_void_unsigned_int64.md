# operator delete(void *,unsigned __int64)

- ea: `0x140001714`
- end: `0x140001719`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002cd0`
- `0x140002d10`
- `0x14000593c`
- `0x140005ba0`
- `0x140005c30`

## callees

- `0x140001d20`

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
0x140001714  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
