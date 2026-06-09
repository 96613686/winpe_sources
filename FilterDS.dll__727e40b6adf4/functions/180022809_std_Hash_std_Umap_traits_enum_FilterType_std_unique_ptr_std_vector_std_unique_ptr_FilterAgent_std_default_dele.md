# _std::_Hash_std::_Umap_traits_enum_FilterType_std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____________std::_Uhash_compare_enum_FilterType_std::hash_enum_FilterType__std::equal_to_enum_FilterType____std::allocator_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________________0___::_Insert_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______________&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______________________::_1_::catch$1

- ea: `0x180022809`
- end: `0x18002283d`
- name: `_std::_Hash_std::_Umap_traits_enum_FilterType_std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____________std::_Uhash_compare_enum_FilterType_std::hash_enum_FilterType__std::equal_to_enum_FilterType____std::allocator_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________________0___::_Insert_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______________&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______________________::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000230c`
- `0x18000ca64`
- `0x1800113dc`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Umap_traits_enum_FilterType_std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____________std::_Uhash_compare_enum_FilterType_std::hash_enum_FilterType__std::equal_to_enum_FilterType____std::allocator_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________________0___::_Insert_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________________std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair_enum_FilterType_const__std::unique_ptr_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________std::default_delete_std::vector_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent____std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______________________::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  _QWORD *iter; // rax

  iter = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Make_iter(
           a1,
           (_QWORD *)(a2 + 32),
           *(_QWORD *)(a2 + 32));
  std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::erase(
    *(_QWORD **)(a2 + 96),
    (_QWORD *)(a2 + 40),
    (_QWORD *)*iter);
  throw;
}

```

## disassembly

```asm
0x180022809  mov     [rsp+arg_8], rdx
0x18002280e  push    rbp
0x18002280f  sub     rsp, 20h
0x180022813  mov     rbp, rdx
0x180022816  mov     r8, [rbp+20h]
0x18002281a  lea     rdx, [rbp+20h]
0x18002281e  call    ?_Make_iter@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Make_iter(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180022823  mov     r8, [rax]
0x180022826  lea     rdx, [rbp+28h]
0x18002282a  mov     rcx, [rbp+60h]
0x18002282e  call    ?erase@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>>>)
0x180022833  xor     edx, edx; pThrowInfo
0x180022835  xor     ecx, ecx; pExceptionObject
0x180022837  call    _CxxThrowException_0
```
