# kernel_std::detail::sp_counted_impl_p<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x180019e50`
- end: `0x180019eb4`
- name: `?dispose@?$sp_counted_impl_p@V?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005178`
- `0x180019e50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180019e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019ea1`
- `ntoskrnl!ExDeleteResourceLite` at `0x180019e68`
- `ntoskrnl!ExDeleteResourceLite` at `0x180019e68`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  struct _ERESOURCE *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8

  v3 = *(_QWORD **)(a1 + 16);
  if ( v3 )
  {
    v4 = (struct _ERESOURCE *)v3[11];
    if ( v4 )
    {
      ExDeleteResourceLite(v4);
      v5 = (void *)v3[11];
      if ( v5 )
        ExFreePoolWithTag(v5, 0);
    }
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
      v3 + 5,
      a2,
      a3);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
      v3,
      v6,
      v7);
    ExFreePoolWithTag(v3, 0);
  }
}

```

## disassembly

```asm
0x180019e50  push    rbx
0x180019e52  sub     rsp, 20h
0x180019e56  mov     rbx, [rcx+10h]
0x180019e5a  test    rbx, rbx
0x180019e5d  jz      short loc_180019EAD
0x180019e5f  mov     rcx, [rbx+58h]; Resource
0x180019e63  test    rcx, rcx
0x180019e66  jz      short loc_180019E8B
0x180019e68  call    cs:__imp_ExDeleteResourceLite
0x180019e6f  nop     dword ptr [rax+rax+00h]
0x180019e74  mov     rcx, [rbx+58h]; P
0x180019e78  test    rcx, rcx
0x180019e7b  jz      short loc_180019E8B
0x180019e7d  xor     edx, edx; Tag
0x180019e7f  call    cs:__imp_ExFreePoolWithTag
0x180019e86  nop     dword ptr [rax+rax+00h]
0x180019e8b  lea     rcx, [rbx+28h]
0x180019e8f  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019e94  mov     rcx, rbx
0x180019e97  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019e9c  xor     edx, edx; Tag
0x180019e9e  mov     rcx, rbx; P
0x180019ea1  call    cs:__imp_ExFreePoolWithTag
0x180019ea8  nop     dword ptr [rax+rax+00h]
0x180019ead  add     rsp, 20h
0x180019eb1  pop     rbx
0x180019eb2  retn
```
