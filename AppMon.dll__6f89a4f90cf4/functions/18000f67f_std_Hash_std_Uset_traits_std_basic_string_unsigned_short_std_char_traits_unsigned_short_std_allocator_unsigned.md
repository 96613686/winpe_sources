# _std::_Hash_std::_Uset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const_&__::_1_::dtor$0

- ea: `0x18000f67f`
- end: `0x18000f68b`
- name: `_std::_Hash_std::_Uset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const_&__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086d8`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Uset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18000f67f  lea     rcx, [rdx+20h]
0x18000f686  jmp     ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
```
