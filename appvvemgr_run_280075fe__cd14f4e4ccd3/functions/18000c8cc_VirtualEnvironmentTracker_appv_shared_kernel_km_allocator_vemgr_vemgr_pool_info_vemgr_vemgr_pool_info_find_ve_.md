# VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>> &)

- ea: `0x18000c8cc`
- end: `0x18000c9a2`
- name: `?find_ve_list@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@3@@Z`
- size: `214`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030f4`
- `0x18000a218`
- `0x18000e6c0`
- `0x180015978`

## callees

- `0x1800052e0`
- `0x180005430`
- `0x18000c8cc`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000c919`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000c919`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(
        struct _RTL_AVL_TABLE **a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v3; // rax
  char v5; // bl
  struct _RTL_AVL_TABLE *v6; // rcx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  char v9; // di
  __int128 v11; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF
  _QWORD Buffer[2]; // [rsp+40h] [rbp-28h] BYREF
  __int128 v14; // [rsp+50h] [rbp-18h]

  Buffer[0] = *a2;
  v3 = a2[1];
  Buffer[1] = v3;
  v5 = 1;
  v11 = 0;
  v12 = 0;
  if ( v3 )
    _InterlockedAdd((volatile signed __int32 *)(v3 + 8), 1u);
  v6 = *a1;
  v14 = 0;
  if ( v6 && (v7 = RtlLookupElementGenericTableAvl(v6, Buffer), (v8 = v7) != 0) )
  {
    *(_QWORD *)&v11 = *v7;
    kernel_std::detail::shared_count::operator=((char *)&v11 + 8, v7 + 1);
    *(_QWORD *)&v12 = v8[2];
    kernel_std::detail::shared_count::operator=((char *)&v12 + 8, v8 + 3);
    v9 = 0;
  }
  else
  {
    v9 = 1;
  }
  appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>((__int64)Buffer);
  if ( v9 )
  {
    v5 = 0;
  }
  else
  {
    *a3 = v12;
    kernel_std::detail::shared_count::operator=(a3 + 1, (char *)&v12 + 8);
  }
  appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>((__int64)&v11);
  return v5 == 0 ? 0xC0000034 : 0;
}

```

## disassembly

```asm
0x18000c8cc  push    rbp
0x18000c8ce  push    rbx
0x18000c8cf  push    rsi
0x18000c8d0  push    rdi
0x18000c8d1  mov     rbp, rsp
0x18000c8d4  sub     rsp, 68h
0x18000c8d8  mov     rax, [rdx]
0x18000c8db  xorps   xmm0, xmm0
0x18000c8de  mov     [rbp+Buffer], rax
0x18000c8e2  xorps   xmm1, xmm1
0x18000c8e5  mov     rax, [rdx+8]
0x18000c8e9  mov     rsi, r8
0x18000c8ec  mov     [rbp+var_20], rax
0x18000c8f0  mov     ebx, 1
0x18000c8f5  movdqu  [rbp+var_48], xmm0
0x18000c8fa  movdqu  [rbp+var_38], xmm1
0x18000c8ff  test    rax, rax
0x18000c902  jz      short loc_18000C908
0x18000c904  lock add [rax+8], ebx
0x18000c908  mov     rcx, [rcx]; Table
0x18000c90b  movdqu  [rbp+var_18], xmm0
0x18000c910  test    rcx, rcx
0x18000c913  jz      short loc_18000C95B
0x18000c915  lea     rdx, [rbp+Buffer]; Buffer
0x18000c919  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000c920  nop     dword ptr [rax+rax+00h]
0x18000c925  mov     rdi, rax
0x18000c928  test    rax, rax
0x18000c92b  jz      short loc_18000C95B
0x18000c92d  mov     rcx, [rax]
0x18000c930  lea     rdx, [rax+8]
0x18000c934  mov     qword ptr [rbp+var_48], rcx
0x18000c938  lea     rcx, [rbp+var_48+8]
0x18000c93c  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000c941  mov     rcx, [rdi+10h]
0x18000c945  lea     rdx, [rdi+18h]
0x18000c949  mov     qword ptr [rbp+var_38], rcx
0x18000c94d  lea     rcx, [rbp+var_38+8]
0x18000c951  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000c956  xor     dil, dil
0x18000c959  jmp     short loc_18000C95E
0x18000c95b  mov     dil, bl
0x18000c95e  lea     rcx, [rbp+Buffer]
0x18000c962  call    ??1?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(void)
0x18000c967  test    dil, dil
0x18000c96a  jz      short loc_18000C970
0x18000c96c  xor     bl, bl
0x18000c96e  jmp     short loc_18000C984
0x18000c970  mov     rax, qword ptr [rbp+var_38]
0x18000c974  lea     rcx, [rsi+8]
0x18000c978  lea     rdx, [rbp+var_38+8]
0x18000c97c  mov     [rsi], rax
0x18000c97f  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000c984  lea     rcx, [rbp+var_48]
0x18000c988  call    ??1?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(void)
0x18000c98d  neg     bl
0x18000c98f  sbb     eax, eax
0x18000c991  not     eax
0x18000c993  and     eax, 0C0000034h
0x18000c998  add     rsp, 68h
0x18000c99c  pop     rdi
0x18000c99d  pop     rsi
0x18000c99e  pop     rbx
0x18000c99f  pop     rbp
0x18000c9a0  retn
```
