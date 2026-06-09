# _std::_Hash_std::_Umap_traits_void___std::shared_ptr_AppMon::AppPortEntry__std::_Uhash_compare_void___std::hash_void____std::equal_to_void______std::allocator_std::pair_void___const_std::shared_ptr_AppMon::AppPortEntry______0___::_Try_emplace_void____::_1_::dtor$1

- ea: `0x18000f887`
- end: `0x18000f893`
- name: `_std::_Hash_std::_Umap_traits_void___std::shared_ptr_AppMon::AppPortEntry__std::_Uhash_compare_void___std::hash_void____std::equal_to_void______std::allocator_std::pair_void___const_std::shared_ptr_AppMon::AppPortEntry______0___::_Try_emplace_void____::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b128`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Umap_traits_void___std::shared_ptr_AppMon::AppPortEntry__std::_Uhash_compare_void___std::hash_void____std::equal_to_void______std::allocator_std::pair_void___const_std::shared_ptr_AppMon::AppPortEntry______0___::_Try_emplace_void____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(a2 + 48);
}

```

## disassembly

```asm
0x18000f887  lea     rcx, [rdx+30h]
0x18000f88e  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(void)
```
