# _std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor$7

- ea: `0x180011812`
- end: `0x18001181e`
- name: `_std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ee1c`

## pseudocode

```c
void __fastcall std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_XinputHid::XInputHidDevice__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_XinputHid::XInputHidDevice______0___::emplace_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____XinputHid::XInputHidDevice______::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  std::_Temporary_owner<XinputHid::XInputHidDevice>::~_Temporary_owner<XinputHid::XInputHidDevice>((_QWORD **)(a2 + 144));
}

```

## disassembly

```asm
0x180011812  lea     rcx, [rdx+90h]
0x180011819  jmp     ??1?$_Temporary_owner@UXInputHidDevice@XinputHid@@@std@@QEAA@XZ; std::_Temporary_owner<XinputHid::XInputHidDevice>::~_Temporary_owner<XinputHid::XInputHidDevice>(void)
```
