# operator delete(void *,unsigned __int64)

- ea: `0x140001354`
- end: `0x140001359`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400022e0`
- `0x140002310`

## callees

- `0x140001920`

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
0x140001354  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
