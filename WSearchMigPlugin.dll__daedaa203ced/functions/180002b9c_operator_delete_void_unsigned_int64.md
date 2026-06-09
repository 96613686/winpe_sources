# operator delete(void *,unsigned __int64)

- ea: `0x180002b9c`
- end: `0x180002ba1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002714`
- `0x180004cf0`
- `0x180004d30`
- `0x180004d70`
- `0x180004db0`
- `0x18000a91c`
- `0x18000aa00`
- `0x18000aa90`
- `0x18000aaf0`
- `0x18000cb14`
- `0x18000cdd0`
- `0x18000ce40`
- `0x18000ce80`
- `0x18000cf00`
- `0x18000d2b0`
- `0x18000d8f0`
- `0x18000dc60`
- `0x180011220`
- `0x180012010`
- `0x1800124d8`
- `0x180012654`
- `0x1800154d0`
- `0x180017a4e`

## callees

- `0x1800026d4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002b9c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
