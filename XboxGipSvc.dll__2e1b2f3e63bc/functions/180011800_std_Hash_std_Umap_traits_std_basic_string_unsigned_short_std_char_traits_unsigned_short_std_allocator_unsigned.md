# _std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor$2

- ea: `0x180011800`
- end: `0x18001180c`
- name: `_std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009bf8`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 128));
}

```

## disassembly

```asm
0x180011800  mov     rcx, [rdx+80h]
0x180011807  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
