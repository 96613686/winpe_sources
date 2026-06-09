# operator delete(void *,unsigned __int64)

- ea: `0x180001484`
- end: `0x180001489`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002210`
- `0x180002250`

## callees

- `0x1800019a0`

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
0x180001484  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
