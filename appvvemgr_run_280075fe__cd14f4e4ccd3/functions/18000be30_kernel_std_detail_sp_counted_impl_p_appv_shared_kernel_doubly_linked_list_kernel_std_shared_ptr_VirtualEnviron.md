# kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x18000be30`
- end: `0x18000be5f`
- name: `?dispose@?$sp_counted_impl_p@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@detail@kernel_std@@UEAAXXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005178`
- `0x18000be30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000be4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000be4c`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(*(_QWORD *)(a1 + 16));
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x18000be30  push    rbx
0x18000be32  sub     rsp, 20h
0x18000be36  mov     rbx, [rcx+10h]
0x18000be3a  test    rbx, rbx
0x18000be3d  jz      short loc_18000BE58
0x18000be3f  mov     rcx, rbx
0x18000be42  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000be47  xor     edx, edx; Tag
0x18000be49  mov     rcx, rbx; P
0x18000be4c  call    cs:__imp_ExFreePoolWithTag
0x18000be53  nop     dword ptr [rax+rax+00h]
0x18000be58  add     rsp, 20h
0x18000be5c  pop     rbx
0x18000be5d  retn
```
