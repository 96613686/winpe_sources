# _TokenizedString::TokenizedString_::_1_::dtor$1

- ea: `0x14000e0c7`
- end: `0x14000e0d7`
- name: `_TokenizedString::TokenizedString_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400039d0`

## pseudocode

```c
void __fastcall TokenizedString::TokenizedString_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::vector<unsigned short const *>::~vector<unsigned short const *>(*(_QWORD *)(a2 + 96) + 24LL);
}

```

## disassembly

```asm
0x14000e0c7  mov     rcx, [rdx+60h]
0x14000e0ce  add     rcx, 18h
0x14000e0d2  jmp     ??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::~vector<ushort const *>(void)
```
