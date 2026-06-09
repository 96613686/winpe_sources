# _ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__minLenOption__

- ea: `0x140012640`
- end: `0x14001264c`
- name: `_ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__minLenOption__`
- size: `12`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000dab8`

## pseudocode

```c
void __fastcall ParseCreateParams_::_2_::_dynamic_atexit_destructor_for__minLenOption__()
{
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&qword_14001A7E0);
}

```

## disassembly

```asm
0x140012640  lea     rcx, qword_14001A7E0
0x140012647  jmp     ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
```
