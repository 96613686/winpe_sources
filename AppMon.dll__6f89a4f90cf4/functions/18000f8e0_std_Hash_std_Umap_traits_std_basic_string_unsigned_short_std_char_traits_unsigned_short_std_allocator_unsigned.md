# _std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0____::_1_::dtor$0

- ea: `0x18000f8e0`
- end: `0x18000f8f0`
- name: `_std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0____::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b2f4`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0___::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::shared_ptr_AppMon::AppPrinterEndPointBase__std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::shared_ptr_AppMon::AppPrinterEndPointBase______0____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::~list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(*(_QWORD *)(a2 + 48) + 8LL);
}

```

## disassembly

```asm
0x18000f8e0  mov     rcx, [rdx+30h]
0x18000f8e7  add     rcx, 8
0x18000f8eb  jmp     ??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::~list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(void)
```
