# operator delete(void *,unsigned __int64)

- ea: `0x180001d30`
- end: `0x180001d35`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003720`
- `0x180003760`

## callees

- `0x1800021dc`

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
0x180001d30  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
