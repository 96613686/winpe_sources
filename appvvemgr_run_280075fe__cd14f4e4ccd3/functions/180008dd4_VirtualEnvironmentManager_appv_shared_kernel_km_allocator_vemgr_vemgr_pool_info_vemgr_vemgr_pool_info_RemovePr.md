# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessVEFromProcessTracker(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180008dd4`
- end: `0x180008fc1`
- name: `?RemoveProcessVEFromProcessTracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008778`

## callees

- `0x180007e10`
- `0x180008b90`
- `0x180008dd4`
- `0x18000e610`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180008ede`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008f06`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008ede`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008f06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008eea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008f12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008eea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008f12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008ea8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008ea8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008e8f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008e8f`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessVEFromProcessTracker(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rcx
  int v6; // r14d
  unsigned int PrimaryVE; // esi
  unsigned int v8; // ebp
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rdi
  bool v11; // si
  struct _ERESOURCE *v12; // rcx
  struct _ERESOURCE *v13; // rcx
  __int128 v15; // [rsp+20h] [rbp-48h] BYREF
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  v6 = a2;
  v15 = 0;
  PrimaryVE = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(
                v5,
                a2,
                &v15);
  v8 = -1073741772;
  if ( (int)(PrimaryVE + 0x80000000) >= 0 && PrimaryVE != -1073741772 )
  {
    v9 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
    if ( !*((_QWORD *)&v15 + 1)
      || _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL), 0xFFFFFFFF) != 1 )
    {
      return PrimaryVE;
    }
    goto LABEL_27;
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
  if ( !*((_QWORD *)&v15 + 1)
    || !*(_DWORD *)(*((_QWORD *)&v15 + 1) + 8LL)
    || !(_QWORD)v15
    || *(_DWORD *)(v15 + 112) != *(_DWORD *)(*(_QWORD *)a3 + 112LL) )
  {
    PrimaryVE = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessReference(
                  *(_QWORD *)(a1 + 16),
                  v6,
                  *(const UNICODE_STRING **)(*(_QWORD *)a3 + 120LL));
    if ( !v9 || _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) != 1 )
      return PrimaryVE;
LABEL_27:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    return PrimaryVE;
  }
  v10 = *(_QWORD *)(a1 + 16);
  v11 = 0;
  v16 = v6;
  if ( *(_QWORD *)(v10 + 16) )
  {
    KeEnterCriticalRegion();
    v11 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v10 + 16), 1u) == 1;
  }
  if ( appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(
         (PRTL_AVL_TABLE *)v10,
         &v16) )
  {
    if ( v11 )
    {
      v13 = *(struct _ERESOURCE **)(v10 + 16);
      if ( v13 )
      {
        ExReleaseResourceLite(v13);
        KeLeaveCriticalRegion();
      }
    }
    v8 = 0;
  }
  else if ( v11 )
  {
    v12 = *(struct _ERESOURCE **)(v10 + 16);
    if ( v12 )
    {
      ExReleaseResourceLite(v12);
      KeLeaveCriticalRegion();
    }
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180008dd4  push    rbx
0x180008dd6  push    rbp
0x180008dd7  push    rsi
0x180008dd8  push    rdi
0x180008dd9  push    r14
0x180008ddb  push    r15
0x180008ddd  sub     rsp, 38h
0x180008de1  mov     r15, r8
0x180008de4  mov     rdi, rcx
0x180008de7  mov     rcx, [rcx+10h]
0x180008deb  lea     r8, [rsp+68h+var_48]
0x180008df0  xorps   xmm0, xmm0
0x180008df3  mov     r14d, edx
0x180008df6  movdqu  [rsp+68h+var_48], xmm0
0x180008dfc  call    ?GetPrimaryVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180008e01  mov     esi, eax
0x180008e03  mov     ebp, 0C0000034h
0x180008e08  mov     eax, 80000000h
0x180008e0d  lea     r8d, [rsi+rax]
0x180008e11  test    eax, r8d
0x180008e14  jnz     short loc_180008E46
0x180008e16  cmp     esi, ebp
0x180008e18  jz      short loc_180008E46
0x180008e1a  mov     rbx, qword ptr [rsp+68h+var_48+8]
0x180008e1f  test    rbx, rbx
0x180008e22  jz      loc_180008FB1
0x180008e28  or      edi, 0FFFFFFFFh
0x180008e2b  mov     eax, edi
0x180008e2d  lock xadd [rbx+8], eax
0x180008e32  add     eax, edi
0x180008e34  jnz     loc_180008FB1
0x180008e3a  mov     rax, [rbx]
0x180008e3d  mov     rax, [rax+8]
0x180008e41  jmp     loc_180008F8F
0x180008e46  mov     rbx, qword ptr [rsp+68h+var_48+8]
0x180008e4b  test    rbx, rbx
0x180008e4e  jz      loc_180008F60
0x180008e54  mov     eax, [rbx+8]
0x180008e57  test    eax, eax
0x180008e59  jz      loc_180008F60
0x180008e5f  mov     rdx, qword ptr [rsp+68h+var_48]
0x180008e64  test    rdx, rdx
0x180008e67  jz      loc_180008F60
0x180008e6d  mov     rax, [r15]
0x180008e70  mov     ecx, [rax+70h]
0x180008e73  cmp     [rdx+70h], ecx
0x180008e76  jnz     loc_180008F60
0x180008e7c  mov     rdi, [rdi+10h]
0x180008e80  xor     sil, sil
0x180008e83  mov     [rsp+68h+arg_0], r14d
0x180008e88  cmp     qword ptr [rdi+10h], 0
0x180008e8d  jz      short loc_180008EBF
0x180008e8f  call    cs:__imp_KeEnterCriticalRegion
0x180008e96  nop     dword ptr [rax+rax+00h]
0x180008e9b  mov     rcx, [rdi+10h]; Resource
0x180008e9f  mov     r14d, 1
0x180008ea5  mov     dl, r14b; Wait
0x180008ea8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008eaf  nop     dword ptr [rax+rax+00h]
0x180008eb4  cmp     al, r14b
0x180008eb7  movzx   esi, sil
0x180008ebb  cmovz   esi, r14d
0x180008ebf  lea     rdx, [rsp+68h+arg_0]
0x180008ec4  mov     rcx, rdi
0x180008ec7  call    ?remove@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBK@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(ulong const &)
0x180008ecc  test    al, al
0x180008ece  jnz     short loc_180008EF8
0x180008ed0  test    sil, sil
0x180008ed3  jz      short loc_180008F20
0x180008ed5  mov     rcx, [rdi+10h]; Resource
0x180008ed9  test    rcx, rcx
0x180008edc  jz      short loc_180008F20
0x180008ede  call    cs:__imp_ExReleaseResourceLite
0x180008ee5  nop     dword ptr [rax+rax+00h]
0x180008eea  call    cs:__imp_KeLeaveCriticalRegion
0x180008ef1  nop     dword ptr [rax+rax+00h]
0x180008ef6  jmp     short loc_180008F20
0x180008ef8  test    sil, sil
0x180008efb  jz      short loc_180008F1E
0x180008efd  mov     rcx, [rdi+10h]; Resource
0x180008f01  test    rcx, rcx
0x180008f04  jz      short loc_180008F1E
0x180008f06  call    cs:__imp_ExReleaseResourceLite
0x180008f0d  nop     dword ptr [rax+rax+00h]
0x180008f12  call    cs:__imp_KeLeaveCriticalRegion
0x180008f19  nop     dword ptr [rax+rax+00h]
0x180008f1e  xor     ebp, ebp
0x180008f20  test    rbx, rbx
0x180008f23  jz      short loc_180008F5C
0x180008f25  or      edi, 0FFFFFFFFh
0x180008f28  mov     eax, edi
0x180008f2a  lock xadd [rbx+8], eax
0x180008f2f  add     eax, edi
0x180008f31  jnz     short loc_180008F5C
0x180008f33  mov     rax, [rbx]
0x180008f36  mov     rcx, rbx
0x180008f39  mov     rax, [rax+8]
0x180008f3d  call    _guard_dispatch_icall
0x180008f42  mov     ecx, edi
0x180008f44  lock xadd [rbx+0Ch], ecx
0x180008f49  add     ecx, edi
0x180008f4b  jnz     short loc_180008F5C
0x180008f4d  mov     rcx, [rbx]
0x180008f50  mov     rax, [rcx+10h]
0x180008f54  mov     rcx, rbx
0x180008f57  call    _guard_dispatch_icall
0x180008f5c  mov     eax, ebp
0x180008f5e  jmp     short loc_180008FB3
0x180008f60  mov     r8, [r15]
0x180008f63  mov     edx, r14d
0x180008f66  mov     rcx, [rdi+10h]
0x180008f6a  mov     r8, [r8+78h]
0x180008f6e  call    ?RemoveProcessReference@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessReference(ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180008f73  mov     esi, eax
0x180008f75  test    rbx, rbx
0x180008f78  jz      short loc_180008FB1
0x180008f7a  or      edi, 0FFFFFFFFh
0x180008f7d  mov     ecx, edi
0x180008f7f  lock xadd [rbx+8], ecx
0x180008f84  add     ecx, edi
0x180008f86  jnz     short loc_180008FB1
0x180008f88  mov     rdx, [rbx]
0x180008f8b  mov     rax, [rdx+8]
0x180008f8f  mov     rcx, rbx
0x180008f92  call    _guard_dispatch_icall
0x180008f97  mov     eax, edi
0x180008f99  lock xadd [rbx+0Ch], eax
0x180008f9e  add     eax, edi
0x180008fa0  jnz     short loc_180008FB1
0x180008fa2  mov     rax, [rbx]
0x180008fa5  mov     rcx, rbx
0x180008fa8  mov     rax, [rax+10h]
0x180008fac  call    _guard_dispatch_icall
0x180008fb1  mov     eax, esi
0x180008fb3  add     rsp, 38h
0x180008fb7  pop     r15
0x180008fb9  pop     r14
0x180008fbb  pop     rdi
0x180008fbc  pop     rsi
0x180008fbd  pop     rbp
0x180008fbe  pop     rbx
0x180008fbf  retn
```
