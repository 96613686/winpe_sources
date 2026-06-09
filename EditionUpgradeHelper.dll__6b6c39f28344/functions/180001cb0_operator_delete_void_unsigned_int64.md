# operator delete(void *,unsigned __int64)

- ea: `0x180001cb0`
- end: `0x180001cb5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003680`
- `0x1800036c0`
- `0x180008480`
- `0x1800084e0`
- `0x180008510`
- `0x180008540`
- `0x180008570`
- `0x1800085d0`
- `0x180009cac`

## callees

- `0x180001d30`

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
0x180001cb0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
