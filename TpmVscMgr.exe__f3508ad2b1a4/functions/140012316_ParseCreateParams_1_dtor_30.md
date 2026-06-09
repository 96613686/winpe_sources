# _ParseCreateParams_::_1_::dtor$30

- ea: `0x140012316`
- end: `0x140012322`
- name: `_ParseCreateParams_::_1_::dtor$30`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000dab8`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_30(__int64 a1, __int64 a2)
{
  return std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((_QWORD *)(a2 + 216));
}

```

## disassembly

```asm
0x140012316  lea     rcx, [rdx+0D8h]
0x14001231d  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
