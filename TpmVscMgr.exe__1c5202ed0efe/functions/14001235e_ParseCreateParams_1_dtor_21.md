# _ParseCreateParams_::_1_::dtor$21

- ea: `0x14001235e`
- end: `0x14001236a`
- name: `_ParseCreateParams_::_1_::dtor$21`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000dab8`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  return std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((_QWORD *)(a2 + 560));
}

```

## disassembly

```asm
0x14001235e  lea     rcx, [rdx+230h]
0x140012365  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
