# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400016c4`
- end: `0x1400016c9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002d70`
- `0x140002f18`
- `0x14000350c`
- `0x140003594`
- `0x140003600`
- `0x140003d70`
- `0x140003db0`
- `0x140003df0`
- `0x140003e30`
- `0x140006b40`
- `0x140006eb0`
- `0x1400094e0`
- `0x14000c7b0`
- `0x14000d184`
- `0x14000d1f4`
- `0x14000d370`
- `0x14000d3c4`
- `0x14000dd04`
- `0x14000ddf0`
- `0x14000dfc4`
- `0x14000e30c`
- `0x14000e3d8`
- `0x14000e480`
- `0x14000e4cc`
- `0x14000e694`
- `0x14000e908`
- `0x14000eaa0`
- `0x14000ead0`
- `0x140010540`
- `0x1400105a0`
- `0x140010ecf`
- `0x140010f8f`
- `0x140010fb4`
- `0x14001100d`
- `0x140011100`

## callees

- `0x140001688`

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
0x1400016c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
