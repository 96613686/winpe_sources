# operator delete(void *,unsigned __int64)

- ea: `0x180001468`
- end: `0x18000146d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003030`
- `0x180003310`

## callees

- `0x180001ba8`

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
0x180001468  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
