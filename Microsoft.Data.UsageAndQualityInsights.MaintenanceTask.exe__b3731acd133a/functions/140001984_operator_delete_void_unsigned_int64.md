# operator delete(void *,unsigned __int64)

- ea: `0x140001984`
- end: `0x140001989`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003970`
- `0x1400039b0`
- `0x1400039f0`
- `0x140003a30`
- `0x1400095cc`
- `0x140009760`
- `0x14000a428`

## callees

- `0x1400019bc`

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
0x140001984  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
