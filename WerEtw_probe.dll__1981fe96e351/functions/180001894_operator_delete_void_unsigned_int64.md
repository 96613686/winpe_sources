# operator delete(void *,unsigned __int64)

- ea: `0x180001894`
- end: `0x180001899`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `112`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800018e4`
- `0x18000296c`
- `0x180002a70`
- `0x180002ab0`
- `0x180003fb8`
- `0x180004150`
- `0x1800041e0`
- `0x180004240`
- `0x1800042d0`
- `0x1800055e0`
- `0x180006dc0`
- `0x18000b534`
- `0x18000b5f0`
- `0x18000b680`
- `0x18000bf98`
- `0x18000c1bc`
- `0x18000c46c`
- `0x18000c4c8`
- `0x18000c564`
- `0x18000c5c0`
- `0x18000c6b8`
- `0x18000c7d4`
- `0x18000c94c`
- `0x18000ca50`
- `0x18000cb90`
- `0x18000d770`
- `0x18000df34`
- `0x18000df9c`
- `0x18000dfc0`
- `0x18000dfe4`
- `0x18000e008`
- `0x18000e02c`
- `0x18000e050`
- `0x18000e0d8`
- `0x18000e148`
- `0x18000e1cc`
- `0x18000e234`
- `0x18000e2dc`
- `0x18000e30c`
- `0x18000e364`
- `0x18000e3d0`
- `0x18000e474`
- `0x18000e530`
- `0x18000e594`
- `0x18000e6cc`
- `0x18000e920`
- `0x18000e9b0`
- `0x18000ed60`
- `0x18000edc4`
- `0x18000f1d8`

## callees

- `0x180001854`

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
0x180001894  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
