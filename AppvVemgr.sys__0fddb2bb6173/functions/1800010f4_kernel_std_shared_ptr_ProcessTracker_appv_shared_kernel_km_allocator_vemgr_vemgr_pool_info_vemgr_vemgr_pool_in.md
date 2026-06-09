# kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>(ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue *)

- ea: `0x1800010f4`
- end: `0x1800011e6`
- name: `??$?0UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAUProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `242`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a30`

## callees

- `0x1800010f4`
- `0x180005178`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000111f`
- `ntoskrnl!ExAllocatePool2` at `0x18000111f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x18000117f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x18000117f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000119b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800011b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000119b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800011b4`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000116d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000116d`

## pseudocode

```c
_QWORD *__fastcall kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 Pool2; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  PVOID v6; // rax
  struct _RTL_AVL_TABLE *v7; // rcx
  __int64 v8; // rax

  *a1 = a2;
  a1[1] = 0;
  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::`vftable';
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)(Pool2 + 16) = a2;
    a1[1] = Pool2;
  }
  else
  {
    a1[1] = 0;
    if ( a2 )
    {
      v5 = (struct _RTL_AVL_TABLE *)a2[6];
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = RtlEnumerateGenericTableAvl(v5, 1u);
          v7 = (struct _RTL_AVL_TABLE *)a2[6];
          if ( !v6 )
            break;
          RtlDeleteElementGenericTableAvl(v7, v6);
          v5 = (struct _RTL_AVL_TABLE *)a2[6];
        }
        if ( v7 )
          ExFreePoolWithTag(v7, 0);
      }
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(a2);
      ExFreePoolWithTag(a2, 0);
    }
  }
  v8 = a1[1];
  if ( !v8 || !*(_DWORD *)(v8 + 8) )
    *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800010f4  mov     [rsp+arg_0], rbx
0x1800010f9  push    rdi
0x1800010fa  sub     rsp, 20h
0x1800010fe  mov     [rcx], rdx
0x180001101  mov     rbx, rdx
0x180001104  mov     qword ptr [rcx+8], 0
0x18000110c  mov     rdi, rcx
0x18000110f  mov     ecx, 100h
0x180001114  mov     edx, 18h
0x180001119  mov     r8d, 66446753h
0x18000111f  call    cs:__imp_ExAllocatePool2
0x180001126  nop     dword ptr [rax+rax+00h]
0x18000112b  test    rax, rax
0x18000112e  jz      short loc_180001152
0x180001130  lea     rcx, ??_7?$sp_counted_impl_p@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>::`vftable'
0x180001137  mov     dword ptr [rax+8], 1
0x18000113e  mov     [rax], rcx
0x180001141  mov     dword ptr [rax+0Ch], 1
0x180001148  mov     [rax+10h], rbx
0x18000114c  mov     [rdi+8], rax
0x180001150  jmp     short loc_1800011C0
0x180001152  mov     qword ptr [rdi+8], 0
0x18000115a  test    rbx, rbx
0x18000115d  jz      short loc_1800011C0
0x18000115f  mov     rcx, [rbx+30h]
0x180001163  test    rcx, rcx
0x180001166  jz      short loc_1800011A7
0x180001168  jmp     short loc_18000117D
0x18000116a  mov     rdx, rax; Buffer
0x18000116d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180001174  nop     dword ptr [rax+rax+00h]
0x180001179  mov     rcx, [rbx+30h]; Table
0x18000117d  mov     dl, 1; Restart
0x18000117f  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180001186  nop     dword ptr [rax+rax+00h]
0x18000118b  mov     rcx, [rbx+30h]; P
0x18000118f  test    rax, rax
0x180001192  jnz     short loc_18000116A
0x180001194  test    rcx, rcx
0x180001197  jz      short loc_1800011A7
0x180001199  xor     edx, edx; Tag
0x18000119b  call    cs:__imp_ExFreePoolWithTag
0x1800011a2  nop     dword ptr [rax+rax+00h]
0x1800011a7  mov     rcx, rbx
0x1800011aa  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x1800011af  xor     edx, edx; Tag
0x1800011b1  mov     rcx, rbx; P
0x1800011b4  call    cs:__imp_ExFreePoolWithTag
0x1800011bb  nop     dword ptr [rax+rax+00h]
0x1800011c0  mov     rax, [rdi+8]
0x1800011c4  test    rax, rax
0x1800011c7  jz      short loc_1800011D0
0x1800011c9  mov     eax, [rax+8]
0x1800011cc  test    eax, eax
0x1800011ce  jnz     short loc_1800011D7
0x1800011d0  mov     qword ptr [rdi], 0
0x1800011d7  mov     rbx, [rsp+28h+arg_0]
0x1800011dc  mov     rax, rdi
0x1800011df  add     rsp, 20h
0x1800011e3  pop     rdi
0x1800011e4  retn
```
