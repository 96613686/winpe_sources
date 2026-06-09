# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)

- ea: `0x18000c5f4`
- end: `0x18000c68b`
- name: `?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z`
- size: `151`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180005178`
- `0x180008b90`
- `0x180009710`
- `0x18000b478`
- `0x18000c9a8`
- `0x18000e6c0`
- `0x1800101e4`
- `0x180010374`
- `0x180015978`
- `0x180017a64`
- `0x180018270`

## callees

- `0x18000c5f4`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000c66f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c66f`

## pseudocode

```c
_QWORD *__fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v3; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r8
  volatile signed __int32 *v9; // rbx

  v3 = *(_QWORD **)a3;
  *a2 = *(_QWORD *)a3;
  *a2 = v3[3];
  v6 = *(_QWORD **)a3;
  v7 = *(_QWORD *)(*(_QWORD *)a3 + 16LL);
  v8 = *(_QWORD *)(*(_QWORD *)a3 + 24LL);
  *(_QWORD *)(v7 + 24) = v8;
  *(_QWORD *)(v8 + 16) = v7;
  if ( v6 )
  {
    v9 = (volatile signed __int32 *)v6[1];
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    ExFreePoolWithTag(v6, 0);
  }
  --*a1;
  return a2;
}

```

## disassembly

```asm
0x18000c5f4  push    rbx
0x18000c5f6  push    rsi
0x18000c5f7  push    rdi
0x18000c5f8  push    r14
0x18000c5fa  sub     rsp, 28h
0x18000c5fe  mov     rax, [r8]
0x18000c601  mov     r14, rdx
0x18000c604  mov     [rdx], rax
0x18000c607  mov     rsi, rcx
0x18000c60a  mov     rax, [rax+18h]
0x18000c60e  mov     [rdx], rax
0x18000c611  mov     rdi, [r8]
0x18000c614  mov     rax, [rdi+10h]
0x18000c618  mov     r8, [rdi+18h]
0x18000c61c  mov     [rax+18h], r8
0x18000c620  mov     [r8+10h], rax
0x18000c624  test    rdi, rdi
0x18000c627  jz      short loc_18000C67B
0x18000c629  mov     rbx, [rdi+8]
0x18000c62d  test    rbx, rbx
0x18000c630  jz      short loc_18000C66A
0x18000c632  or      eax, 0FFFFFFFFh
0x18000c635  lock xadd [rbx+8], eax
0x18000c63a  cmp     eax, 1
0x18000c63d  jnz     short loc_18000C66A
0x18000c63f  mov     rax, [rbx]
0x18000c642  mov     rcx, rbx
0x18000c645  mov     rax, [rax+8]
0x18000c649  call    _guard_dispatch_icall
0x18000c64e  or      eax, 0FFFFFFFFh
0x18000c651  lock xadd [rbx+0Ch], eax
0x18000c656  cmp     eax, 1
0x18000c659  jnz     short loc_18000C66A
0x18000c65b  mov     rax, [rbx]
0x18000c65e  mov     rcx, rbx
0x18000c661  mov     rax, [rax+10h]
0x18000c665  call    _guard_dispatch_icall
0x18000c66a  xor     edx, edx; Tag
0x18000c66c  mov     rcx, rdi; P
0x18000c66f  call    cs:__imp_ExFreePoolWithTag
0x18000c676  nop     dword ptr [rax+rax+00h]
0x18000c67b  dec     dword ptr [rsi]
0x18000c67d  mov     rax, r14
0x18000c680  add     rsp, 28h
0x18000c684  pop     r14
0x18000c686  pop     rdi
0x18000c687  pop     rsi
0x18000c688  pop     rbx
0x18000c689  retn
```
