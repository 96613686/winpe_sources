# _std::_Tree_std::_Tmap_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo____std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________0___::emplace_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________::_1_::dtor$2

- ea: `0x140017646`
- end: `0x140017652`
- name: `_std::_Tree_std::_Tmap_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo____std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________0___::emplace_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000f6a8`

## pseudocode

```c
void __fastcall std::_Tree_std::_Tmap_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo____std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________0___::emplace_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::unique_ptr_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo_std::default_delete_Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo________::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x140017646  lea     rcx, [rdx+20h]
0x14001764d  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(void)
```
