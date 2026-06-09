# _ATL::CComObject_Windows::CComEnumOnOwnedSTL_IEnumString_&_GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________ATL::CComMultiThreadModel___::CreateInstance_::_1_::dtor$0

- ea: `0x140012210`
- end: `0x14001221e`
- name: `_ATL::CComObject_Windows::CComEnumOnOwnedSTL_IEnumString_&_GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________ATL::CComMultiThreadModel___::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140012217`

## pseudocode

```c
void __fastcall ATL::CComObject_Windows::CComEnumOnOwnedSTL_IEnumString___GUID_00000101_0000_0000_c000_000000000046_unsigned_short___Windows::CopyFromPairWstringToLpolestr_std::map_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________ATL::CComMultiThreadModel___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
}

```

## disassembly

```asm
0x140012210  mov     rcx, [rdx+78h]
0x140012217  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
