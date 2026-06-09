# appv::shared::kernel::avl_tree<appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::less_predicate_wrapper>::avl_tree_order(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180019ae0`
- end: `0x180019b16`
- name: `?avl_tree_order@?$avl_tree@V?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@2@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@8@@234@@kernel@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `54`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, const UNICODE_STRING **FirstStruct, const UNICODE_STRING **SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019ae0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180019af5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180019af5`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::avl_tree<appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::less_predicate_wrapper>::avl_tree_order(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING **FirstStruct,
        const UNICODE_STRING **SecondStruct)
{
  LONG v3; // eax

  v3 = RtlCompareUnicodeString(*FirstStruct + 1, *SecondStruct + 1, 1u);
  if ( v3 >= 0 )
    return 2 - (unsigned int)(v3 != 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180019ae0  sub     rsp, 28h
0x180019ae4  mov     rax, [r8]
0x180019ae7  mov     r8b, 1; CaseInSensitive
0x180019aea  mov     rcx, [rdx]
0x180019aed  add     rcx, 10h; String1
0x180019af1  lea     rdx, [rax+10h]; String2
0x180019af5  call    cs:__imp_RtlCompareUnicodeString
0x180019afc  nop     dword ptr [rax+rax+00h]
0x180019b01  test    eax, eax
0x180019b03  jns     short loc_180019B09
0x180019b05  xor     eax, eax
0x180019b07  jmp     short loc_180019B10
0x180019b09  neg     eax
0x180019b0b  sbb     eax, eax
0x180019b0d  add     eax, 2
0x180019b10  add     rsp, 28h
0x180019b14  retn
```
