# operator delete(void *,unsigned __int64)

- ea: `0x140002ba4`
- end: `0x140002ba9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003e70`
- `0x140003eb0`

## callees

- `0x140003170`

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
0x140002ba4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
