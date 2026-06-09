# _ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__specialCharsOption__

- ea: `0x1400126c0`
- end: `0x1400126cc`
- name: `_ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__specialCharsOption__`
- size: `12`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000dab8`

## pseudocode

```c
void __fastcall ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__specialCharsOption__()
{
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(qword_14001A8D0);
}

```

## disassembly

```asm
0x1400126c0  lea     rcx, qword_14001A8D0
0x1400126c7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
