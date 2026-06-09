# SRCache_Free

- ea: `0x18000de80`
- end: `0x18000de85`
- name: `SRCache_Free`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800022a0`

## pseudocode

```c
// attributes: thunk
void __fastcall SRCache_Free(void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x18000de80  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
