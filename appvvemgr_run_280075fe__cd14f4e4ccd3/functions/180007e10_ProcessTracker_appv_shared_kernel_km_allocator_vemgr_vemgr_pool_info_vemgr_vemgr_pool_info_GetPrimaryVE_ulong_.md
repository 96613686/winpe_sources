# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180007e10`
- end: `0x180007f7f`
- name: `?GetPrimaryVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `367`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008048`
- `0x180008dd4`
- `0x180019624`

## callees

- `0x180005430`
- `0x180007e10`
- `0x18000c768`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180007ed3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007f5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007ed3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007f5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007edf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007f67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007edf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007f67`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007e44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007e44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007e2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007e2c`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(
        __int64 a1,
        int a2,
        __int64 a3)
{
  bool v3; // bp
  volatile signed __int32 *v6; // rdi
  struct _ERESOURCE *v7; // rcx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rdi
  struct _ERESOURCE *v11; // rcx
  __int128 v12; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = a2;
  v3 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v12 = 0;
  if ( appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
         (struct _RTL_AVL_TABLE **)a1,
         &v13,
         (__int64)&v12)
    && *(_BYTE *)(v12 + 40) )
  {
    v9 = *(_QWORD *)(v12 + 32);
    *(_QWORD *)a3 = *(_QWORD *)v9;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)(a3 + 8),
      (volatile signed __int32 **)(v9 + 8));
    v10 = (volatile signed __int32 *)*((_QWORD *)&v12 + 1);
    if ( *((_QWORD *)&v12 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    if ( v3 )
    {
      v11 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v11 )
      {
        ExReleaseResourceLite(v11);
        KeLeaveCriticalRegion();
      }
    }
    return 0;
  }
  else
  {
    v6 = (volatile signed __int32 *)*((_QWORD *)&v12 + 1);
    if ( *((_QWORD *)&v12 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    if ( v3 )
    {
      v7 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x180007e10  mov     [rsp+arg_8], edx
0x180007e14  push    rbx
0x180007e15  push    rbp
0x180007e16  push    rsi
0x180007e17  push    rdi
0x180007e18  sub     rsp, 38h
0x180007e1c  xor     bpl, bpl
0x180007e1f  mov     rbx, r8
0x180007e22  cmp     qword ptr [rcx+10h], 0
0x180007e27  mov     rsi, rcx
0x180007e2a  jz      short loc_180007E5A
0x180007e2c  call    cs:__imp_KeEnterCriticalRegion
0x180007e33  nop     dword ptr [rax+rax+00h]
0x180007e38  mov     rcx, [rsi+10h]; Resource
0x180007e3c  mov     edi, 1
0x180007e41  mov     dl, dil; Wait
0x180007e44  call    cs:__imp_ExAcquireResourceSharedLite
0x180007e4b  nop     dword ptr [rax+rax+00h]
0x180007e50  cmp     al, dil
0x180007e53  movzx   ebp, bpl
0x180007e57  cmovz   ebp, edi
0x180007e5a  xorps   xmm0, xmm0
0x180007e5d  lea     r8, [rsp+58h+var_38]
0x180007e62  lea     rdx, [rsp+58h+arg_8]
0x180007e67  mov     rcx, rsi
0x180007e6a  movdqu  [rsp+58h+var_38], xmm0
0x180007e70  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x180007e75  test    al, al
0x180007e77  jz      short loc_180007E84
0x180007e79  mov     rdx, qword ptr [rsp+58h+var_38]
0x180007e7e  cmp     byte ptr [rdx+28h], 0
0x180007e82  jnz     short loc_180007EF5
0x180007e84  mov     rdi, qword ptr [rsp+58h+var_38+8]
0x180007e89  test    rdi, rdi
0x180007e8c  jz      short loc_180007EC5
0x180007e8e  or      ebx, 0FFFFFFFFh
0x180007e91  mov     eax, ebx
0x180007e93  lock xadd [rdi+8], eax
0x180007e98  add     eax, ebx
0x180007e9a  jnz     short loc_180007EC5
0x180007e9c  mov     rax, [rdi]
0x180007e9f  mov     rcx, rdi
0x180007ea2  mov     rax, [rax+8]
0x180007ea6  call    _guard_dispatch_icall
0x180007eab  mov     eax, ebx
0x180007ead  lock xadd [rdi+0Ch], eax
0x180007eb2  add     eax, ebx
0x180007eb4  jnz     short loc_180007EC5
0x180007eb6  mov     rax, [rdi]
0x180007eb9  mov     rcx, rdi
0x180007ebc  mov     rax, [rax+10h]
0x180007ec0  call    _guard_dispatch_icall
0x180007ec5  test    bpl, bpl
0x180007ec8  jz      short loc_180007EEB
0x180007eca  mov     rcx, [rsi+10h]; Resource
0x180007ece  test    rcx, rcx
0x180007ed1  jz      short loc_180007EEB
0x180007ed3  call    cs:__imp_ExReleaseResourceLite
0x180007eda  nop     dword ptr [rax+rax+00h]
0x180007edf  call    cs:__imp_KeLeaveCriticalRegion
0x180007ee6  nop     dword ptr [rax+rax+00h]
0x180007eeb  mov     eax, 0C0000034h
0x180007ef0  jmp     loc_180007F75
0x180007ef5  mov     rdx, [rdx+20h]
0x180007ef9  lea     rcx, [rbx+8]
0x180007efd  mov     rax, [rdx]
0x180007f00  add     rdx, 8
0x180007f04  mov     [rbx], rax
0x180007f07  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180007f0c  mov     rdi, qword ptr [rsp+58h+var_38+8]
0x180007f11  test    rdi, rdi
0x180007f14  jz      short loc_180007F4D
0x180007f16  or      ebx, 0FFFFFFFFh
0x180007f19  mov     eax, ebx
0x180007f1b  lock xadd [rdi+8], eax
0x180007f20  add     eax, ebx
0x180007f22  jnz     short loc_180007F4D
0x180007f24  mov     rax, [rdi]
0x180007f27  mov     rcx, rdi
0x180007f2a  mov     rax, [rax+8]
0x180007f2e  call    _guard_dispatch_icall
0x180007f33  mov     eax, ebx
0x180007f35  lock xadd [rdi+0Ch], eax
0x180007f3a  add     eax, ebx
0x180007f3c  jnz     short loc_180007F4D
0x180007f3e  mov     rax, [rdi]
0x180007f41  mov     rcx, rdi
0x180007f44  mov     rax, [rax+10h]
0x180007f48  call    _guard_dispatch_icall
0x180007f4d  test    bpl, bpl
0x180007f50  jz      short loc_180007F73
0x180007f52  mov     rcx, [rsi+10h]; Resource
0x180007f56  test    rcx, rcx
0x180007f59  jz      short loc_180007F73
0x180007f5b  call    cs:__imp_ExReleaseResourceLite
0x180007f62  nop     dword ptr [rax+rax+00h]
0x180007f67  call    cs:__imp_KeLeaveCriticalRegion
0x180007f6e  nop     dword ptr [rax+rax+00h]
0x180007f73  xor     eax, eax
0x180007f75  add     rsp, 38h
0x180007f79  pop     rdi
0x180007f7a  pop     rsi
0x180007f7b  pop     rbp
0x180007f7c  pop     rbx
0x180007f7d  retn
```
