# appv::shared::kernel::avl_tree<appv::shared::kernel::pair<ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>::less_predicate_wrapper>::avl_tree_order(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x18000aca0`
- end: `0x18000acb3`
- name: `?avl_tree_order@?$avl_tree@V?$pair@KV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@234@@kernel@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `19`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, _DWORD *FirstStruct, _DWORD *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000aca0`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::avl_tree<appv::shared::kernel::pair<unsigned long,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>::less_predicate_wrapper>::avl_tree_order(
        struct _RTL_AVL_TABLE *Table,
        _DWORD *FirstStruct,
        _DWORD *SecondStruct)
{
  if ( *FirstStruct - *SecondStruct >= 0 )
    return 2 - (unsigned int)(*FirstStruct != *SecondStruct);
  else
    return 0;
}

```

## disassembly

```asm
0x18000aca0  mov     ecx, [rdx]
0x18000aca2  sub     ecx, [r8]
0x18000aca5  jns     short loc_18000ACAB
0x18000aca7  xor     eax, eax
0x18000aca9  retn
0x18000acab  neg     ecx
0x18000acad  sbb     eax, eax
0x18000acaf  add     eax, 2
0x18000acb2  retn
```
