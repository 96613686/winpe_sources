# _ParseCreateParams_::_1_::dtor$28

- ea: `0x140012370`
- end: `0x14001237c`
- name: `_ParseCreateParams_::_1_::dtor$28`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000eef8`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  return std::tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(a2 + 672);
}

```

## disassembly

```asm
0x140012370  lea     rcx, [rdx+2A0h]
0x140012377  jmp     ??1?$tuple@V?$range@PEBG@rangelib@@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@std@@QEAA@XZ; std::tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
```
