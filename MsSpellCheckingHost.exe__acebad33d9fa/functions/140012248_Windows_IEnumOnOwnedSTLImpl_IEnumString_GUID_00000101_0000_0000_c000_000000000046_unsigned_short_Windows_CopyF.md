# _Windows::IEnumOnOwnedSTLImpl_IEnumString_&_GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________::Init_::_1_::catch$1

- ea: `0x140012248`
- end: `0x14001226d`
- name: `_Windows::IEnumOnOwnedSTLImpl_IEnumString_&_GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________::Init_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl_IEnumString___GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________::Init_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x140012248  mov     [rsp+arg_8], rdx
0x14001224d  push    rbp
0x14001224e  sub     rsp, 20h
0x140012252  mov     rbp, rdx
0x140012255  mov     dword ptr [rbp+48h], 8007000Eh
0x14001225c  mov     rax, 0
0x140012266  add     rsp, 20h
0x14001226a  pop     rbp
0x14001226b  retn
```
