# _ParseCreateParams_::_1_::dtor$18

- ea: `0x14001233a`
- end: `0x140012346`
- name: `_ParseCreateParams_::_1_::dtor$18`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000eef8`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_18(__int64 a1, __int64 a2)
{
  return std::tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(a2 + 624);
}

```

## disassembly

```asm
0x14001233a  lea     rcx, [rdx+270h]
0x140012341  jmp     ??1?$tuple@V?$range@PEBG@rangelib@@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@std@@QEAA@XZ; std::tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
```
