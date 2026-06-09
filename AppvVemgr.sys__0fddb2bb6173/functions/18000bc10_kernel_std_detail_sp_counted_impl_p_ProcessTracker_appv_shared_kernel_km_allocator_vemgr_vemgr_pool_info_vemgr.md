# kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::dispose(void)

- ea: `0x18000bc10`
- end: `0x18000bc87`
- name: `?dispose@?$sp_counted_impl_p@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005178`
- `0x18000bc10`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x18000bc3f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x18000bc3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc74`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc74`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000bc2d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000bc2d`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::dispose(
        __int64 a1)
{
  _QWORD *v1; // rbx
  struct _RTL_AVL_TABLE *v2; // rcx
  PVOID v3; // rax
  struct _RTL_AVL_TABLE *v4; // rcx

  v1 = *(_QWORD **)(a1 + 16);
  if ( v1 )
  {
    v2 = (struct _RTL_AVL_TABLE *)v1[6];
    if ( v2 )
    {
      while ( 1 )
      {
        v3 = RtlEnumerateGenericTableAvl(v2, 1u);
        v4 = (struct _RTL_AVL_TABLE *)v1[6];
        if ( !v3 )
          break;
        RtlDeleteElementGenericTableAvl(v4, v3);
        v2 = (struct _RTL_AVL_TABLE *)v1[6];
      }
      if ( v4 )
        ExFreePoolWithTag(v4, 0);
    }
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)v1);
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x18000bc10  push    rbx
0x18000bc12  sub     rsp, 20h
0x18000bc16  mov     rbx, [rcx+10h]
0x18000bc1a  test    rbx, rbx
0x18000bc1d  jz      short loc_18000BC80
0x18000bc1f  mov     rcx, [rbx+30h]
0x18000bc23  test    rcx, rcx
0x18000bc26  jz      short loc_18000BC67
0x18000bc28  jmp     short loc_18000BC3D
0x18000bc2a  mov     rdx, rax; Buffer
0x18000bc2d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000bc34  nop     dword ptr [rax+rax+00h]
0x18000bc39  mov     rcx, [rbx+30h]; Table
0x18000bc3d  mov     dl, 1; Restart
0x18000bc3f  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000bc46  nop     dword ptr [rax+rax+00h]
0x18000bc4b  mov     rcx, [rbx+30h]; P
0x18000bc4f  test    rax, rax
0x18000bc52  jnz     short loc_18000BC2A
0x18000bc54  test    rcx, rcx
0x18000bc57  jz      short loc_18000BC67
0x18000bc59  xor     edx, edx; Tag
0x18000bc5b  call    cs:__imp_ExFreePoolWithTag
0x18000bc62  nop     dword ptr [rax+rax+00h]
0x18000bc67  mov     rcx, rbx
0x18000bc6a  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000bc6f  xor     edx, edx; Tag
0x18000bc71  mov     rcx, rbx; P
0x18000bc74  call    cs:__imp_ExFreePoolWithTag
0x18000bc7b  nop     dword ptr [rax+rax+00h]
0x18000bc80  add     rsp, 20h
0x18000bc84  pop     rbx
0x18000bc85  retn
```
