# operator delete(void *,unsigned __int64)

- ea: `0x180008e50`
- end: `0x180008e55`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001450`
- `0x180002690`
- `0x180007b80`
- `0x180007bc0`

## callees

- `0x1800092fc`

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
0x180008e50  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
