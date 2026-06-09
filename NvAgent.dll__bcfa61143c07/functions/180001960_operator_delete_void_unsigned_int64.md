# operator delete(void *,unsigned __int64)

- ea: `0x180001960`
- end: `0x180001965`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002c90`
- `0x180002cd0`
- `0x180005cd0`

## callees

- `0x180001e3c`

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
0x180001960  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
