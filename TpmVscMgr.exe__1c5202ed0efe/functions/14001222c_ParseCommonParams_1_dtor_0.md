# _ParseCommonParams_::_1_::dtor$0

- ea: `0x14001222c`
- end: `0x140012238`
- name: `_ParseCommonParams_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000dab8`

## pseudocode

```c
__int64 __fastcall ParseCommonParams_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x14001222c  lea     rcx, [rdx+20h]
0x140012233  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
