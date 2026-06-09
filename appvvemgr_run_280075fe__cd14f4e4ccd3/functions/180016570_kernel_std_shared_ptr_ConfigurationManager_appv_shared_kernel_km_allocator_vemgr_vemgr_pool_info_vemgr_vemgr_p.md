# kernel_std::shared_ptr<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)

- ea: `0x180016570`
- end: `0x18001667b`
- name: `??$reset@V?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAAXPEAV?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017334`

## callees

- `0x180005178`
- `0x180016570`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180016590`
- `ntoskrnl!ExAllocatePool2` at `0x180016590`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800165ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001660f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800165ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001660f`
- `ntoskrnl!ExDeleteResourceLite` at `0x1800165d6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1800165d6`

## pseudocode

```c
__int64 __fastcall kernel_std::shared_ptr<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ecx
  struct _ERESOURCE *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 result; // rax
  volatile signed __int32 *v13; // rbx
  signed __int32 v14; // eax
  bool v15; // zf

  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  v6 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
    v7 = *(_DWORD *)(Pool2 + 8);
  }
  else
  {
    v6 = 0;
    if ( a2 )
    {
      v8 = (struct _ERESOURCE *)a2[11];
      if ( v8 )
      {
        ExDeleteResourceLite(v8);
        v9 = (void *)a2[11];
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
      }
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        a2 + 5,
        v5,
        v6);
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        a2,
        v10,
        v11);
      ExFreePoolWithTag(a2, 0);
      v6 = 0;
    }
    v7 = 0;
  }
  result = 0;
  if ( v7 )
    result = (__int64)a2;
  v13 = (volatile signed __int32 *)a1[1];
  *a1 = result;
  a1[1] = v6;
  if ( v13 )
  {
    v14 = _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF);
    v15 = v14 == 1;
    result = (unsigned int)(v14 - 1);
    if ( v15 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      result = (unsigned int)_InterlockedDecrement(v13 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016570  mov     [rsp+arg_0], rbx
0x180016575  push    rdi
0x180016576  sub     rsp, 20h
0x18001657a  mov     rbx, rdx
0x18001657d  mov     rdi, rcx
0x180016580  mov     edx, 18h
0x180016585  mov     ecx, 100h
0x18001658a  mov     r8d, 66446753h
0x180016590  call    cs:__imp_ExAllocatePool2
0x180016597  nop     dword ptr [rax+rax+00h]
0x18001659c  mov     r8, rax
0x18001659f  test    rax, rax
0x1800165a2  jz      short loc_1800165C5
0x1800165a4  mov     eax, 1
0x1800165a9  mov     [r8+10h], rbx
0x1800165ad  mov     [r8+8], eax
0x1800165b1  mov     [r8+0Ch], eax
0x1800165b5  lea     rax, ??_7?$sp_counted_impl_p@V?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x1800165bc  mov     [r8], rax
0x1800165bf  mov     ecx, [r8+8]
0x1800165c3  jmp     short loc_180016620
0x1800165c5  xor     r8d, r8d
0x1800165c8  test    rbx, rbx
0x1800165cb  jz      short loc_18001661E
0x1800165cd  mov     rcx, [rbx+58h]; Resource
0x1800165d1  test    rcx, rcx
0x1800165d4  jz      short loc_1800165F9
0x1800165d6  call    cs:__imp_ExDeleteResourceLite
0x1800165dd  nop     dword ptr [rax+rax+00h]
0x1800165e2  mov     rcx, [rbx+58h]; P
0x1800165e6  test    rcx, rcx
0x1800165e9  jz      short loc_1800165F9
0x1800165eb  xor     edx, edx; Tag
0x1800165ed  call    cs:__imp_ExFreePoolWithTag
0x1800165f4  nop     dword ptr [rax+rax+00h]
0x1800165f9  lea     rcx, [rbx+28h]
0x1800165fd  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180016602  mov     rcx, rbx
0x180016605  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001660a  xor     edx, edx; Tag
0x18001660c  mov     rcx, rbx; P
0x18001660f  call    cs:__imp_ExFreePoolWithTag
0x180016616  nop     dword ptr [rax+rax+00h]
0x18001661b  xor     r8d, r8d
0x18001661e  xor     ecx, ecx
0x180016620  xor     eax, eax
0x180016622  test    ecx, ecx
0x180016624  cmovnz  rax, rbx
0x180016628  mov     rbx, [rdi+8]
0x18001662c  mov     [rdi], rax
0x18001662f  mov     [rdi+8], r8
0x180016633  test    rbx, rbx
0x180016636  jz      short loc_18001666F
0x180016638  or      edi, 0FFFFFFFFh
0x18001663b  mov     eax, edi
0x18001663d  lock xadd [rbx+8], eax
0x180016642  add     eax, edi
0x180016644  jnz     short loc_18001666F
0x180016646  mov     rax, [rbx]
0x180016649  mov     rcx, rbx
0x18001664c  mov     rax, [rax+8]
0x180016650  call    _guard_dispatch_icall
0x180016655  mov     eax, edi
0x180016657  lock xadd [rbx+0Ch], eax
0x18001665c  add     eax, edi
0x18001665e  jnz     short loc_18001666F
0x180016660  mov     rax, [rbx]
0x180016663  mov     rcx, rbx
0x180016666  mov     rax, [rax+10h]
0x18001666a  call    _guard_dispatch_icall
0x18001666f  mov     rbx, [rsp+28h+arg_0]
0x180016674  add     rsp, 20h
0x180016678  pop     rdi
0x180016679  retn
```
