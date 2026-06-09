# VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_or_decrement_ve(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)

- ea: `0x18000e6c0`
- end: `0x18000e8ce`
- name: `?remove_or_decrement_ve@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@1@@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE **, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800090c4`

## callees

- `0x180003034`
- `0x1800052e0`
- `0x18000c5f4`
- `0x18000c8cc`
- `0x18000e6c0`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000e84b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000e84b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000e862`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000e862`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_or_decrement_ve(
        struct _RTL_AVL_TABLE **a1,
        __int64 *a2,
        _DWORD *a3)
{
  _QWORD *v5; // rdx
  int ve_list; // r15d
  volatile signed __int32 *v8; // rdi
  __int64 v10; // rcx
  _DWORD *v11; // rbx
  const UNICODE_STRING *v12; // rcx
  const UNICODE_STRING *v13; // rax
  volatile signed __int32 *v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rax
  struct _RTL_AVL_TABLE *v18; // rcx
  bool v19; // bl
  PVOID v20; // rax
  volatile signed __int32 *v21; // rdi
  __int128 v22; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Buffer[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v24; // [rsp+40h] [rbp-10h]
  PCUNICODE_STRING v25; // [rsp+88h] [rbp+38h] BYREF
  const UNICODE_STRING *v26; // [rsp+98h] [rbp+48h] BYREF

  v5 = (_QWORD *)(*a2 + 120);
  v22 = 0;
  ve_list = VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(
              a1,
              v5,
              (__int64)&v22);
  if ( ve_list < 0 )
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)ve_list;
  }
  v10 = *a2;
  v11 = (_DWORD *)v22;
  if ( *(_DWORD *)(*a2 + 40) )
    v12 = (const UNICODE_STRING *)(**(_QWORD **)(v10 + 72) + 64LL);
  else
    v12 = (const UNICODE_STRING *)(v10 + 152);
  v25 = v12;
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(
    v22,
    (__int64)&v26,
    &v25);
  v13 = v26;
  if ( v26 != (const UNICODE_STRING *)(v11 + 2) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)&v26->Length + 16LL))-- != 1 )
    {
      *a3 = 0;
LABEL_13:
      v15 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
      if ( *((_QWORD *)&v22 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      return 0;
    }
    *a3 = 1;
    v25 = v13;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
      v11,
      &v26,
      (__int64)&v25);
    if ( *v11 )
      goto LABEL_13;
    v16 = *a2;
    *a3 = 2;
    Buffer[0] = *(_QWORD *)(v16 + 120);
    v17 = *(_QWORD *)(v16 + 128);
    Buffer[1] = v17;
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    v18 = *a1;
    v24 = 0;
    v19 = v18
       && (v20 = RtlLookupElementGenericTableAvl(v18, Buffer)) != 0
       && RtlDeleteElementGenericTableAvl(*a1, v20) != 0;
    appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>((__int64)Buffer);
    if ( v19 )
      goto LABEL_13;
  }
  v21 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  if ( *((_QWORD *)&v22 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  return 3221225524LL;
}

```

## disassembly

```asm
0x18000e6c0  mov     [rsp-28h+arg_0], rbx
0x18000e6c5  push    rbp
0x18000e6c6  push    rsi
0x18000e6c7  push    rdi
0x18000e6c8  push    r14
0x18000e6ca  push    r15
0x18000e6cc  mov     rbp, rsp
0x18000e6cf  sub     rsp, 50h
0x18000e6d3  mov     rsi, rdx
0x18000e6d6  mov     rdi, r8
0x18000e6d9  mov     rdx, [rdx]
0x18000e6dc  lea     r8, [rbp+var_30]
0x18000e6e0  xorps   xmm0, xmm0
0x18000e6e3  add     rdx, 78h ; 'x'
0x18000e6e7  mov     r14, rcx
0x18000e6ea  movdqu  [rbp+var_30], xmm0
0x18000e6ef  call    ?find_ve_list@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@3@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>> &)
0x18000e6f4  mov     r15d, eax
0x18000e6f7  test    eax, eax
0x18000e6f9  jns     short loc_18000E743
0x18000e6fb  mov     rdi, qword ptr [rbp+var_30+8]
0x18000e6ff  test    rdi, rdi
0x18000e702  jz      short loc_18000E73B
0x18000e704  or      ebx, 0FFFFFFFFh
0x18000e707  mov     ecx, ebx
0x18000e709  lock xadd [rdi+8], ecx
0x18000e70e  add     ecx, ebx
0x18000e710  jnz     short loc_18000E73B
0x18000e712  mov     rax, [rdi]
0x18000e715  mov     rcx, rdi
0x18000e718  mov     rax, [rax+8]
0x18000e71c  call    _guard_dispatch_icall
0x18000e721  mov     eax, ebx
0x18000e723  lock xadd [rdi+0Ch], eax
0x18000e728  add     eax, ebx
0x18000e72a  jnz     short loc_18000E73B
0x18000e72c  mov     rax, [rdi]
0x18000e72f  mov     rcx, rdi
0x18000e732  mov     rax, [rax+10h]
0x18000e736  call    _guard_dispatch_icall
0x18000e73b  mov     eax, r15d
0x18000e73e  jmp     loc_18000E7DA
0x18000e743  mov     rcx, [rsi]
0x18000e746  mov     rbx, qword ptr [rbp+var_30]
0x18000e74a  cmp     dword ptr [rcx+28h], 0
0x18000e74e  jz      short loc_18000E75D
0x18000e750  mov     rax, [rcx+48h]
0x18000e754  mov     rcx, [rax]
0x18000e757  add     rcx, 40h ; '@'
0x18000e75b  jmp     short loc_18000E764
0x18000e75d  add     rcx, 98h
0x18000e764  mov     [rbp+arg_8], rcx
0x18000e768  lea     r8, [rbp+arg_8]
0x18000e76c  mov     rcx, rbx
0x18000e76f  lea     rdx, [rbp+arg_18]
0x18000e773  call    ??$find_first_element@Ufind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAUfind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate &)
0x18000e778  mov     rax, [rbp+arg_18]
0x18000e77c  lea     rcx, [rbx+8]
0x18000e780  cmp     rax, rcx
0x18000e783  jz      loc_18000E884
0x18000e789  mov     rcx, [rax]
0x18000e78c  add     dword ptr [rcx+10h], 0FFFFFFFFh
0x18000e790  jz      short loc_18000E7EF
0x18000e792  mov     dword ptr [rdi], 0
0x18000e798  mov     rdi, qword ptr [rbp+var_30+8]
0x18000e79c  test    rdi, rdi
0x18000e79f  jz      short loc_18000E7D8
0x18000e7a1  or      ebx, 0FFFFFFFFh
0x18000e7a4  mov     eax, ebx
0x18000e7a6  lock xadd [rdi+8], eax
0x18000e7ab  add     eax, ebx
0x18000e7ad  jnz     short loc_18000E7D8
0x18000e7af  mov     rax, [rdi]
0x18000e7b2  mov     rcx, rdi
0x18000e7b5  mov     rax, [rax+8]
0x18000e7b9  call    _guard_dispatch_icall
0x18000e7be  mov     eax, ebx
0x18000e7c0  lock xadd [rdi+0Ch], eax
0x18000e7c5  add     eax, ebx
0x18000e7c7  jnz     short loc_18000E7D8
0x18000e7c9  mov     rax, [rdi]
0x18000e7cc  mov     rcx, rdi
0x18000e7cf  mov     rax, [rax+10h]
0x18000e7d3  call    _guard_dispatch_icall
0x18000e7d8  xor     eax, eax
0x18000e7da  mov     rbx, [rsp+50h+arg_0]
0x18000e7e2  add     rsp, 50h
0x18000e7e6  pop     r15
0x18000e7e8  pop     r14
0x18000e7ea  pop     rdi
0x18000e7eb  pop     rsi
0x18000e7ec  pop     rbp
0x18000e7ed  retn
0x18000e7ef  lea     r8, [rbp+arg_8]
0x18000e7f3  mov     dword ptr [rdi], 1
0x18000e7f9  lea     rdx, [rbp+arg_18]
0x18000e7fd  mov     [rbp+arg_8], rax
0x18000e801  mov     rcx, rbx
0x18000e804  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18000e809  cmp     dword ptr [rbx], 0
0x18000e80c  jnz     short loc_18000E798
0x18000e80e  mov     rcx, [rsi]
0x18000e811  mov     dword ptr [rdi], 2
0x18000e817  mov     rax, [rcx+78h]
0x18000e81b  mov     [rbp+Buffer], rax
0x18000e81f  mov     rax, [rcx+80h]
0x18000e826  mov     [rbp+var_18], rax
0x18000e82a  test    rax, rax
0x18000e82d  jz      short loc_18000E833
0x18000e82f  lock inc dword ptr [rax+8]
0x18000e833  mov     rcx, [r14]; Table
0x18000e836  xorps   xmm0, xmm0
0x18000e839  movdqu  [rbp+var_10], xmm0
0x18000e83e  test    rcx, rcx
0x18000e841  jnz     short loc_18000E847
0x18000e843  xor     bl, bl
0x18000e845  jmp     short loc_18000E873
0x18000e847  lea     rdx, [rbp+Buffer]; Buffer
0x18000e84b  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000e852  nop     dword ptr [rax+rax+00h]
0x18000e857  test    rax, rax
0x18000e85a  jz      short loc_18000E843
0x18000e85c  mov     rcx, [r14]; Table
0x18000e85f  mov     rdx, rax; Buffer
0x18000e862  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000e869  nop     dword ptr [rax+rax+00h]
0x18000e86e  test    al, al
0x18000e870  setnz   bl
0x18000e873  lea     rcx, [rbp+Buffer]
0x18000e877  call    ??1?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(void)
0x18000e87c  test    bl, bl
0x18000e87e  jnz     loc_18000E798
0x18000e884  mov     rdi, qword ptr [rbp+var_30+8]
0x18000e888  test    rdi, rdi
0x18000e88b  jz      short loc_18000E8C4
0x18000e88d  or      ebx, 0FFFFFFFFh
0x18000e890  mov     eax, ebx
0x18000e892  lock xadd [rdi+8], eax
0x18000e897  add     eax, ebx
0x18000e899  jnz     short loc_18000E8C4
0x18000e89b  mov     rax, [rdi]
0x18000e89e  mov     rcx, rdi
0x18000e8a1  mov     rax, [rax+8]
0x18000e8a5  call    _guard_dispatch_icall
0x18000e8aa  mov     eax, ebx
0x18000e8ac  lock xadd [rdi+0Ch], eax
0x18000e8b1  add     eax, ebx
0x18000e8b3  jnz     short loc_18000E8C4
0x18000e8b5  mov     rax, [rdi]
0x18000e8b8  mov     rcx, rdi
0x18000e8bb  mov     rax, [rax+10h]
0x18000e8bf  call    _guard_dispatch_icall
0x18000e8c4  mov     eax, 0C0000034h
0x18000e8c9  jmp     loc_18000E7DA
```
