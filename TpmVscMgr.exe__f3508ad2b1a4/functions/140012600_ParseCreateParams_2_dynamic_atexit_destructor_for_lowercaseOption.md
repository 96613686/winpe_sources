# _ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__lowercaseOption__

- ea: `0x140012600`
- end: `0x14001260c`
- name: `_ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__lowercaseOption__`
- size: `12`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000dab8`

## pseudocode

```c
void __fastcall ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__lowercaseOption__()
{
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&qword_14001A870);
}

```

## disassembly

```asm
0x140012600  lea     rcx, qword_14001A870
0x140012607  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
