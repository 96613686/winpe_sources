# std::tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)

- ea: `0x14000eef8`
- end: `0x14000eefd`
- name: `??1?$tuple@V?$range@PEBG@rangelib@@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001233a`
- `0x140012370`
- `0x140012382`
- `0x1400123dc`
- `0x1400123ee`

## callees

- `0x14000dab8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~tuple<rangelib::range<unsigned short const *>,std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(
        _QWORD *a1)
{
  return std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(a1);
}

```

## disassembly

```asm
0x14000eef8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
