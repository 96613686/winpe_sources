# operator delete(void *,std::nothrow_t const &)

- ea: `0x180003a34`
- end: `0x180003a39`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `78`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006380`
- `0x1800067f4`
- `0x1800068b0`
- `0x180006940`
- `0x180006970`
- `0x1800069b0`
- `0x1800069f0`
- `0x180006a30`
- `0x18000a254`
- `0x18000c45c`
- `0x18000ca94`
- `0x18000d11c`
- `0x18000d2b4`
- `0x18000d6c4`
- `0x18000e860`
- `0x18000e978`
- `0x18000eab4`
- `0x18000ebfc`
- `0x18000ed90`
- `0x18000ef00`
- `0x180012160`
- `0x18001233c`
- `0x180012360`
- `0x180012394`
- `0x180012404`
- `0x180012490`
- `0x1800125ec`
- `0x18001266c`
- `0x1800126fc`
- `0x180012808`
- `0x180012870`
- `0x180012984`
- `0x180012b94`
- `0x180012c04`
- `0x180012c8c`
- `0x180012cfc`
- `0x1800135d4`
- `0x180013724`
- `0x1800137b4`
- `0x180013a04`
- `0x180014d10`
- `0x180014d50`
- `0x180014d90`
- `0x180014de0`
- `0x180014e20`
- `0x180014e54`
- `0x180014ef0`
- `0x180014f30`
- `0x180014f90`
- `0x180014fd0`

## callees

- `0x180003a28`

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
0x180003a34  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
