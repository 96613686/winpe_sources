# _std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Try_emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor$0

- ea: `0x18000f899`
- end: `0x18000f8a5`
- name: `_std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Try_emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b248`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Try_emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(a2 + 48);
}

```

## disassembly

```asm
0x18000f899  lea     rcx, [rdx+30h]
0x18000f8a0  jmp     ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(void)
```
