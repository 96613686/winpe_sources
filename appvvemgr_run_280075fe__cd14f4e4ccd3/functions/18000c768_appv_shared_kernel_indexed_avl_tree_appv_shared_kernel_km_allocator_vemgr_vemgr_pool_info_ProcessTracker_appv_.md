# appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)

- ea: `0x18000c768`
- end: `0x18000c8c6`
- name: `?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `350`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000566c`
- `0x180005a30`
- `0x180007b88`
- `0x180007e10`
- `0x180008358`
- `0x180008b90`
- `0x180017a64`
- `0x180019624`

## callees

- `0x180005430`
- `0x18000c768`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000c7a3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000c7a3`

## pseudocode

```c
char __fastcall appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
        struct _RTL_AVL_TABLE **a1,
        int *a2,
        __int64 a3)
{
  struct _RTL_AVL_TABLE *v3; // rcx
  char v5; // di
  PVOID v6; // rax
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v10; // rbx
  __int128 v11; // [rsp+28h] [rbp-28h] BYREF
  int Buffer; // [rsp+38h] [rbp-18h] BYREF
  __int128 v13; // [rsp+40h] [rbp-10h]

  v3 = *a1;
  Buffer = *a2;
  v11 = 0;
  v13 = 0;
  if ( v3 && (v6 = RtlLookupElementGenericTableAvl(v3, &Buffer), (a2 = (int *)v6) != 0) )
  {
    *(_QWORD *)&v11 = *((_QWORD *)v6 + 1);
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)&v11 + 1,
      (volatile signed __int32 **)v6 + 2);
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
  v7 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
  if ( *((_QWORD *)&v13 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *, int *))(*(_QWORD *)v7 + 8LL))(v7, a2);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  if ( v5 )
  {
    *(_QWORD *)a3 = v11;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)(a3 + 8),
      (volatile signed __int32 **)&v11 + 1);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v11 + 1);
    if ( *((_QWORD *)&v11 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v11 + 1) + 8LL)) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    return 1;
  }
  else
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)&v11 + 1);
    if ( *((_QWORD *)&v11 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v11 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *, int *))(*(_QWORD *)v8 + 8LL))(v8, a2);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000c768  push    rbp
0x18000c76a  push    rbx
0x18000c76b  push    rsi
0x18000c76c  push    rdi
0x18000c76d  push    r14
0x18000c76f  mov     rbp, rsp
0x18000c772  sub     rsp, 50h
0x18000c776  mov     rcx, [rcx]; Table
0x18000c779  xorps   xmm0, xmm0
0x18000c77c  mov     eax, [rdx]
0x18000c77e  mov     rsi, r8
0x18000c781  mov     [rbp+var_30], 0
0x18000c788  mov     [rbp+Buffer], eax
0x18000c78b  movdqu  [rbp+var_28], xmm0
0x18000c790  movdqu  [rbp+var_10], xmm0
0x18000c795  test    rcx, rcx
0x18000c798  jnz     short loc_18000C79F
0x18000c79a  xor     dil, dil
0x18000c79d  jmp     short loc_18000C7D4
0x18000c79f  lea     rdx, [rbp+Buffer]; Buffer
0x18000c7a3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000c7aa  nop     dword ptr [rax+rax+00h]
0x18000c7af  mov     rdx, rax
0x18000c7b2  test    rax, rax
0x18000c7b5  jz      short loc_18000C79A
0x18000c7b7  mov     eax, [rax]
0x18000c7b9  lea     rcx, [rbp+var_28+8]
0x18000c7bd  mov     [rbp+var_30], eax
0x18000c7c0  mov     rax, [rdx+8]
0x18000c7c4  add     rdx, 10h
0x18000c7c8  mov     qword ptr [rbp+var_28], rax
0x18000c7cc  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000c7d1  mov     dil, 1
0x18000c7d4  mov     rbx, qword ptr [rbp+var_10+8]
0x18000c7d8  or      r14d, 0FFFFFFFFh
0x18000c7dc  test    rbx, rbx
0x18000c7df  jz      short loc_18000C819
0x18000c7e1  mov     eax, r14d
0x18000c7e4  lock xadd [rbx+8], eax
0x18000c7e9  add     eax, r14d
0x18000c7ec  jnz     short loc_18000C819
0x18000c7ee  mov     rax, [rbx]
0x18000c7f1  mov     rcx, rbx
0x18000c7f4  mov     rax, [rax+8]
0x18000c7f8  call    _guard_dispatch_icall
0x18000c7fd  mov     eax, r14d
0x18000c800  lock xadd [rbx+0Ch], eax
0x18000c805  add     eax, r14d
0x18000c808  jnz     short loc_18000C819
0x18000c80a  mov     rax, [rbx]
0x18000c80d  mov     rcx, rbx
0x18000c810  mov     rax, [rax+10h]
0x18000c814  call    _guard_dispatch_icall
0x18000c819  test    dil, dil
0x18000c81c  jnz     short loc_18000C863
0x18000c81e  mov     rbx, qword ptr [rbp+var_28+8]
0x18000c822  test    rbx, rbx
0x18000c825  jz      short loc_18000C85F
0x18000c827  mov     eax, r14d
0x18000c82a  lock xadd [rbx+8], eax
0x18000c82f  add     eax, r14d
0x18000c832  jnz     short loc_18000C85F
0x18000c834  mov     rax, [rbx]
0x18000c837  mov     rcx, rbx
0x18000c83a  mov     rax, [rax+8]
0x18000c83e  call    _guard_dispatch_icall
0x18000c843  mov     eax, r14d
0x18000c846  lock xadd [rbx+0Ch], eax
0x18000c84b  add     eax, r14d
0x18000c84e  jnz     short loc_18000C85F
0x18000c850  mov     rax, [rbx]
0x18000c853  mov     rcx, rbx
0x18000c856  mov     rax, [rax+10h]
0x18000c85a  call    _guard_dispatch_icall
0x18000c85f  xor     al, al
0x18000c861  jmp     short loc_18000C8BA
0x18000c863  mov     rax, qword ptr [rbp+var_28]
0x18000c867  lea     rcx, [rsi+8]
0x18000c86b  lea     rdx, [rbp+var_28+8]
0x18000c86f  mov     [rsi], rax
0x18000c872  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000c877  mov     rbx, qword ptr [rbp+var_28+8]
0x18000c87b  test    rbx, rbx
0x18000c87e  jz      short loc_18000C8B8
0x18000c880  mov     eax, r14d
0x18000c883  lock xadd [rbx+8], eax
0x18000c888  add     eax, r14d
0x18000c88b  jnz     short loc_18000C8B8
0x18000c88d  mov     rax, [rbx]
0x18000c890  mov     rcx, rbx
0x18000c893  mov     rax, [rax+8]
0x18000c897  call    _guard_dispatch_icall
0x18000c89c  mov     edx, r14d
0x18000c89f  lock xadd [rbx+0Ch], edx
0x18000c8a4  add     edx, r14d
0x18000c8a7  jnz     short loc_18000C8B8
0x18000c8a9  mov     rdx, [rbx]
0x18000c8ac  mov     rcx, rbx
0x18000c8af  mov     rax, [rdx+10h]
0x18000c8b3  call    _guard_dispatch_icall
0x18000c8b8  mov     al, 1
0x18000c8ba  add     rsp, 50h
0x18000c8be  pop     r14
0x18000c8c0  pop     rdi
0x18000c8c1  pop     rsi
0x18000c8c2  pop     rbx
0x18000c8c3  pop     rbp
0x18000c8c4  retn
```
