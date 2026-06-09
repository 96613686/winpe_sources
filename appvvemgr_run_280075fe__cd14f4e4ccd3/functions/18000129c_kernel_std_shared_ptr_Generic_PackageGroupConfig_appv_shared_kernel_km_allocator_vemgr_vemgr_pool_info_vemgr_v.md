# kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)

- ea: `0x18000129c`
- end: `0x18000138f`
- name: `??$?0V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000199c`
- `0x18000ef74`
- `0x1800110e8`

## callees

- `0x18000129c`
- `0x180005178`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800012cc`
- `ntoskrnl!ExAllocatePool2` at `0x1800012cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001358`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001358`

## pseudocode

```c
_QWORD *__fastcall kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 Pool2; // rax
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rax

  *a1 = a2;
  a1[1] = 0;
  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
    a1[1] = Pool2;
  }
  else
  {
    a1[1] = 0;
    if ( a2 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)(a2 + 2));
      v5 = (volatile signed __int32 *)a2[1];
      if ( v5 )
      {
        if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
          if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 16LL))(v5);
        }
      }
      ExFreePoolWithTag(a2, 0);
    }
  }
  v6 = a1[1];
  if ( !v6 || !*(_DWORD *)(v6 + 8) )
    *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000129c  mov     [rsp+arg_0], rbx
0x1800012a1  mov     [rsp+arg_8], rsi
0x1800012a6  push    rdi
0x1800012a7  sub     rsp, 20h
0x1800012ab  mov     [rcx], rdx
0x1800012ae  mov     rsi, rdx
0x1800012b1  mov     qword ptr [rcx+8], 0
0x1800012b9  mov     rbx, rcx
0x1800012bc  mov     ecx, 100h
0x1800012c1  mov     edx, 18h
0x1800012c6  mov     r8d, 66446753h
0x1800012cc  call    cs:__imp_ExAllocatePool2
0x1800012d3  nop     dword ptr [rax+rax+00h]
0x1800012d8  test    rax, rax
0x1800012db  jz      short loc_1800012FC
0x1800012dd  mov     ecx, 1
0x1800012e2  mov     [rax+10h], rsi
0x1800012e6  mov     [rax+8], ecx
0x1800012e9  mov     [rax+0Ch], ecx
0x1800012ec  lea     rcx, ??_7?$sp_counted_impl_p@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x1800012f3  mov     [rax], rcx
0x1800012f6  mov     [rbx+8], rax
0x1800012fa  jmp     short loc_180001364
0x1800012fc  mov     qword ptr [rbx+8], 0
0x180001304  test    rsi, rsi
0x180001307  jz      short loc_180001364
0x180001309  lea     rcx, [rsi+10h]
0x18000130d  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180001312  mov     rdi, [rsi+8]
0x180001316  test    rdi, rdi
0x180001319  jz      short loc_180001353
0x18000131b  or      eax, 0FFFFFFFFh
0x18000131e  lock xadd [rdi+8], eax
0x180001323  cmp     eax, 1
0x180001326  jnz     short loc_180001353
0x180001328  mov     rax, [rdi]
0x18000132b  mov     rcx, rdi
0x18000132e  mov     rax, [rax+8]
0x180001332  call    _guard_dispatch_icall
0x180001337  or      eax, 0FFFFFFFFh
0x18000133a  lock xadd [rdi+0Ch], eax
0x18000133f  cmp     eax, 1
0x180001342  jnz     short loc_180001353
0x180001344  mov     rax, [rdi]
0x180001347  mov     rcx, rdi
0x18000134a  mov     rax, [rax+10h]
0x18000134e  call    _guard_dispatch_icall
0x180001353  xor     edx, edx; Tag
0x180001355  mov     rcx, rsi; P
0x180001358  call    cs:__imp_ExFreePoolWithTag
0x18000135f  nop     dword ptr [rax+rax+00h]
0x180001364  mov     rax, [rbx+8]
0x180001368  test    rax, rax
0x18000136b  jz      short loc_180001374
0x18000136d  mov     eax, [rax+8]
0x180001370  test    eax, eax
0x180001372  jnz     short loc_18000137B
0x180001374  mov     qword ptr [rbx], 0
0x18000137b  mov     rsi, [rsp+28h+arg_8]
0x180001380  mov     rax, rbx
0x180001383  mov     rbx, [rsp+28h+arg_0]
0x180001388  add     rsp, 20h
0x18000138c  pop     rdi
0x18000138d  retn
```
