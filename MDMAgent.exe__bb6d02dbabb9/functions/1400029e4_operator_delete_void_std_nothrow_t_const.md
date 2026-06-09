# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400029e4`
- end: `0x1400029e9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400044e8`
- `0x140004ac0`
- `0x140004c54`
- `0x140004da0`
- `0x140004de0`
- `0x140006954`
- `0x140008cd0`
- `0x140009790`
- `0x1400097d0`
- `0x140009ae8`
- `0x14000a51c`
- `0x14000c314`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`
- `0x140011ab4`
- `0x140013440`
- `0x140013480`
- `0x1400151d8`
- `0x140018180`
- `0x140018468`
- `0x140019522`

## callees

- `0x1400029a8`

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
0x1400029e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
