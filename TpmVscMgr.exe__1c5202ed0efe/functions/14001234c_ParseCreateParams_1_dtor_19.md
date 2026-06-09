# _ParseCreateParams_::_1_::dtor$19

- ea: `0x14001234c`
- end: `0x140012358`
- name: `_ParseCreateParams_::_1_::dtor$19`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 112);
}

```

## disassembly

```asm
0x14001234c  lea     rcx, [rdx+70h]
0x140012353  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
