# operator delete(void *,std::nothrow_t const &)

- ea: `0x140002954`
- end: `0x140002959`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004424`
- `0x140004a40`
- `0x140004bc0`
- `0x140004d00`
- `0x140004d40`
- `0x1400066fc`
- `0x1400088e0`
- `0x1400093a0`
- `0x1400093e0`
- `0x1400096dc`
- `0x14000a0b8`
- `0x14000bdc4`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`
- `0x140011238`
- `0x140012b00`
- `0x140012b40`
- `0x14001464c`
- `0x1400174b4`
- `0x14001778c`
- `0x1400187c2`

## callees

- `0x140002918`

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
0x140002954  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
