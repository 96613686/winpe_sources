# operator delete(void *,unsigned __int64)

- ea: `0x140002674`
- end: `0x140002679`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `50`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140006af0`
- `0x140006b30`
- `0x140006b70`
- `0x140006bb0`
- `0x140006be0`
- `0x140006c20`
- `0x140006c60`
- `0x140006c90`
- `0x140009650`
- `0x14000b920`
- `0x14000b980`
- `0x14000b9e0`
- `0x14000ba20`
- `0x14000c3e0`
- `0x14000d5c8`
- `0x14000e510`
- `0x14000e774`
- `0x14000e7c0`
- `0x14000e7fc`
- `0x14000e840`
- `0x14000e8a0`
- `0x14000e900`
- `0x14000e960`
- `0x14000e9c0`
- `0x14000ea20`
- `0x14000ea5c`
- `0x14000eaa0`
- `0x14000eae0`
- `0x14000ee94`
- `0x1400131ac`
- `0x140013270`
- `0x1400132d0`
- `0x140013414`
- `0x140013724`
- `0x140014160`
- `0x1400141a0`
- `0x140014200`
- `0x140014240`
- `0x1400148e8`
- `0x140017c20`
- `0x14001b210`
- `0x14001bf60`
- `0x14001c7a8`
- `0x14001ee54`
- `0x14001f134`
- `0x140021594`
- `0x140021ba0`
- `0x140021be0`
- `0x1400259a0`
- `0x140026d60`

## callees

- `0x140002bf0`

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
0x140002674  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
