# kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)

- ea: `0x180016684`
- end: `0x180016792`
- name: `??$reset@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAAXPEAV?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64 *, struct _RTL_AVL_TABLE **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800168b0`

## callees

- `0x180016684`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800166a3`
- `ntoskrnl!ExAllocatePool2` at `0x1800166a3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1800166ff`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1800166ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001671a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001672b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001671a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001672b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1800166ee`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1800166ee`

## pseudocode

```c
__int64 __fastcall kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        __int64 *a1,
        struct _RTL_AVL_TABLE **a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdi
  int v6; // ecx
  struct _RTL_AVL_TABLE *v7; // rcx
  PVOID v8; // rax
  struct _RTL_AVL_TABLE *v9; // rcx
  __int64 result; // rax
  volatile signed __int32 *v11; // rbx
  signed __int32 v12; // eax
  bool v13; // zf

  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  v5 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
    *(_QWORD *)(Pool2 + 16) = a2;
    v6 = *(_DWORD *)(Pool2 + 8);
  }
  else
  {
    v5 = 0;
    if ( a2 )
    {
      v7 = *a2;
      if ( *a2 )
      {
        while ( 1 )
        {
          v8 = RtlEnumerateGenericTableAvl(v7, 1u);
          v9 = *a2;
          if ( !v8 )
            break;
          RtlDeleteElementGenericTableAvl(v9, v8);
          v7 = *a2;
        }
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
      }
      ExFreePoolWithTag(a2, 0);
    }
    v6 = 0;
  }
  result = 0;
  if ( v6 )
    result = (__int64)a2;
  v11 = (volatile signed __int32 *)a1[1];
  *a1 = result;
  a1[1] = v5;
  if ( v11 )
  {
    v12 = _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF);
    v13 = v12 == 1;
    result = (unsigned int)(v12 - 1);
    if ( v13 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      result = (unsigned int)_InterlockedDecrement(v11 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016684  push    rbx
0x180016686  push    rbp
0x180016687  push    rsi
0x180016688  push    rdi
0x180016689  sub     rsp, 28h
0x18001668d  mov     rbx, rdx
0x180016690  mov     rsi, rcx
0x180016693  mov     edx, 18h
0x180016698  mov     ecx, 100h
0x18001669d  mov     r8d, 66446753h
0x1800166a3  call    cs:__imp_ExAllocatePool2
0x1800166aa  nop     dword ptr [rax+rax+00h]
0x1800166af  mov     rdi, rax
0x1800166b2  test    rax, rax
0x1800166b5  jz      short loc_1800166D8
0x1800166b7  mov     dword ptr [rax+8], 1
0x1800166be  mov     dword ptr [rax+0Ch], 1
0x1800166c5  lea     rax, ??_7?$sp_counted_impl_p@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x1800166cc  mov     [rdi], rax
0x1800166cf  mov     [rdi+10h], rbx
0x1800166d3  mov     ecx, [rdi+8]
0x1800166d6  jmp     short loc_180016739
0x1800166d8  xor     edi, edi
0x1800166da  test    rbx, rbx
0x1800166dd  jz      short loc_180016737
0x1800166df  mov     rcx, [rbx]
0x1800166e2  test    rcx, rcx
0x1800166e5  jz      short loc_180016726
0x1800166e7  xor     ebp, ebp
0x1800166e9  jmp     short loc_1800166FD
0x1800166eb  mov     rdx, rax; Buffer
0x1800166ee  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800166f5  nop     dword ptr [rax+rax+00h]
0x1800166fa  mov     rcx, [rbx]; Table
0x1800166fd  mov     dl, 1; Restart
0x1800166ff  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180016706  nop     dword ptr [rax+rax+00h]
0x18001670b  mov     rcx, [rbx]; P
0x18001670e  test    rax, rax
0x180016711  jnz     short loc_1800166EB
0x180016713  test    rcx, rcx
0x180016716  jz      short loc_180016726
0x180016718  xor     edx, edx; Tag
0x18001671a  call    cs:__imp_ExFreePoolWithTag
0x180016721  nop     dword ptr [rax+rax+00h]
0x180016726  xor     edx, edx; Tag
0x180016728  mov     rcx, rbx; P
0x18001672b  call    cs:__imp_ExFreePoolWithTag
0x180016732  nop     dword ptr [rax+rax+00h]
0x180016737  xor     ecx, ecx
0x180016739  xor     eax, eax
0x18001673b  test    ecx, ecx
0x18001673d  cmovnz  rax, rbx
0x180016741  mov     rbx, [rsi+8]
0x180016745  mov     [rsi], rax
0x180016748  mov     [rsi+8], rdi
0x18001674c  test    rbx, rbx
0x18001674f  jz      short loc_180016788
0x180016751  or      edi, 0FFFFFFFFh
0x180016754  mov     eax, edi
0x180016756  lock xadd [rbx+8], eax
0x18001675b  add     eax, edi
0x18001675d  jnz     short loc_180016788
0x18001675f  mov     rax, [rbx]
0x180016762  mov     rcx, rbx
0x180016765  mov     rax, [rax+8]
0x180016769  call    _guard_dispatch_icall
0x18001676e  mov     eax, edi
0x180016770  lock xadd [rbx+0Ch], eax
0x180016775  add     eax, edi
0x180016777  jnz     short loc_180016788
0x180016779  mov     rax, [rbx]
0x18001677c  mov     rcx, rbx
0x18001677f  mov     rax, [rax+10h]
0x180016783  call    _guard_dispatch_icall
0x180016788  add     rsp, 28h
0x18001678c  pop     rdi
0x18001678d  pop     rsi
0x18001678e  pop     rbp
0x18001678f  pop     rbx
0x180016790  retn
```
