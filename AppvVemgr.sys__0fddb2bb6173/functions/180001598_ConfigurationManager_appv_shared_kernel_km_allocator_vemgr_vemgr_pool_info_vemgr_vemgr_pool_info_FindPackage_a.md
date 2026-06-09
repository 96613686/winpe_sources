# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180001598`
- end: `0x180001781`
- name: `??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, __int64 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800071a0`
- `0x180018964`
- `0x180018b9c`

## callees

- `0x1800011ec`
- `0x180001598`
- `0x180002e94`
- `0x1800046d4`
- `0x18000d184`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180001660`
- `ntoskrnl!ExAllocatePool2` at `0x180001660`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000162b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001728`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001752`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000162b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001728`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001752`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001637`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001734`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000175e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001637`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001734`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000175e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800015e2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800015e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800015ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800015ca`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 *a3)
{
  bool v7; // si
  _QWORD *v8; // rbx
  struct _ERESOURCE *v9; // rcx
  void *Pool2; // rax
  void *v11; // rbp
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  volatile signed __int32 *v15; // r14
  __int64 v16; // rax
  struct _ERESOURCE *v17; // rcx
  struct _ERESOURCE *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v20; // [rsp+28h] [rbp-30h]
  const UNICODE_STRING *v21; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v22; // [rsp+78h] [rbp+20h] BYREF

  if ( *(_DWORD *)&a2->Length <= 2u )
    return 3221225485LL;
  v7 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v7 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v21 = a2;
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a1,
    (__int64)&v22,
    &v21);
  v8 = v22;
  if ( v22 == (_QWORD *)(a1 + 8) )
  {
    if ( v7 )
    {
      v9 = *(struct _ERESOURCE **)(a1 + 88);
      if ( v9 )
      {
        ExReleaseResourceLite(v9);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
  else
  {
    Pool2 = (void *)ExAllocatePool2(64, 136, 1715758931);
    v11 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x88u);
      Pool2 = (void *)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v11);
    }
    v12 = kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
            &v19,
            Pool2);
    v13 = *v12;
    *v12 = *a3;
    *a3 = v13;
    v14 = a3[1];
    a3[1] = v12[1];
    v12[1] = v14;
    v15 = v20;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    if ( *a3
      && (v16 = a3[1]) != 0
      && *(_DWORD *)(v16 + 8)
      && (unsigned __int8)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
                            *a3,
                            *v8) )
    {
      if ( v7 )
      {
        v17 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v17 )
        {
          ExReleaseResourceLite(v17);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
    else
    {
      if ( v7 )
      {
        v18 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v18 )
        {
          ExReleaseResourceLite(v18);
          KeLeaveCriticalRegion();
        }
      }
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x180001598  mov     [rsp+arg_0], rbx
0x18000159d  push    rbp
0x18000159e  push    rsi
0x18000159f  push    rdi
0x1800015a0  push    r14
0x1800015a2  push    r15
0x1800015a4  sub     rsp, 30h
0x1800015a8  cmp     dword ptr [rdx], 2
0x1800015ab  mov     r15, r8
0x1800015ae  mov     rbx, rdx
0x1800015b1  mov     rdi, rcx
0x1800015b4  ja      short loc_1800015C0
0x1800015b6  mov     eax, 0C000000Dh
0x1800015bb  jmp     loc_18000176F
0x1800015c0  xor     sil, sil
0x1800015c3  cmp     qword ptr [rcx+58h], 0
0x1800015c8  jz      short loc_1800015F8
0x1800015ca  call    cs:__imp_KeEnterCriticalRegion
0x1800015d1  nop     dword ptr [rax+rax+00h]
0x1800015d6  mov     rcx, [rdi+58h]; Resource
0x1800015da  mov     ebp, 1
0x1800015df  mov     dl, bpl; Wait
0x1800015e2  call    cs:__imp_ExAcquireResourceSharedLite
0x1800015e9  nop     dword ptr [rax+rax+00h]
0x1800015ee  cmp     al, bpl
0x1800015f1  movzx   esi, sil
0x1800015f5  cmovz   esi, ebp
0x1800015f8  lea     r8, [rsp+58h+arg_8]
0x1800015fd  mov     [rsp+58h+arg_8], rbx
0x180001602  lea     rdx, [rsp+58h+arg_18]
0x180001607  mov     rcx, rdi
0x18000160a  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000160f  mov     rbx, [rsp+58h+arg_18]
0x180001614  lea     rax, [rdi+8]
0x180001618  cmp     rbx, rax
0x18000161b  jnz     short loc_18000164D
0x18000161d  test    sil, sil
0x180001620  jz      short loc_180001643
0x180001622  mov     rcx, [rdi+58h]; Resource
0x180001626  test    rcx, rcx
0x180001629  jz      short loc_180001643
0x18000162b  call    cs:__imp_ExReleaseResourceLite
0x180001632  nop     dword ptr [rax+rax+00h]
0x180001637  call    cs:__imp_KeLeaveCriticalRegion
0x18000163e  nop     dword ptr [rax+rax+00h]
0x180001643  mov     eax, 0C0000034h
0x180001648  jmp     loc_18000176F
0x18000164d  mov     r14d, 88h
0x180001653  mov     r8d, 66446753h
0x180001659  mov     edx, r14d
0x18000165c  lea     ecx, [r14-48h]
0x180001660  call    cs:__imp_ExAllocatePool2
0x180001667  nop     dword ptr [rax+rax+00h]
0x18000166c  mov     rbp, rax
0x18000166f  test    rax, rax
0x180001672  jz      short loc_180001689
0x180001674  mov     r8d, r14d; Size
0x180001677  xor     edx, edx; Val
0x180001679  mov     rcx, rax; void *
0x18000167c  call    memset
0x180001681  mov     rcx, rbp
0x180001684  call    ??0?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x180001689  mov     rdx, rax
0x18000168c  lea     rcx, [rsp+58h+var_38]
0x180001691  call    ??$?0V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x180001696  mov     rcx, [r15]
0x180001699  mov     rdx, [rax]
0x18000169c  mov     [rax], rcx
0x18000169f  mov     [r15], rdx
0x1800016a2  mov     rcx, [rax+8]
0x1800016a6  mov     rdx, [r15+8]
0x1800016aa  mov     [r15+8], rcx
0x1800016ae  mov     [rax+8], rdx
0x1800016b2  mov     r14, [rsp+58h+var_30]
0x1800016b7  test    r14, r14
0x1800016ba  jz      short loc_1800016F5
0x1800016bc  or      ebp, 0FFFFFFFFh
0x1800016bf  mov     eax, ebp
0x1800016c1  lock xadd [r14+8], eax
0x1800016c7  add     eax, ebp
0x1800016c9  jnz     short loc_1800016F5
0x1800016cb  mov     rax, [r14]
0x1800016ce  mov     rcx, r14
0x1800016d1  mov     rax, [rax+8]
0x1800016d5  call    _guard_dispatch_icall
0x1800016da  mov     eax, ebp
0x1800016dc  lock xadd [r14+0Ch], eax
0x1800016e2  add     eax, ebp
0x1800016e4  jnz     short loc_1800016F5
0x1800016e6  mov     rax, [r14]
0x1800016e9  mov     rcx, r14
0x1800016ec  mov     rax, [rax+10h]
0x1800016f0  call    _guard_dispatch_icall
0x1800016f5  cmp     qword ptr [r15], 0
0x1800016f9  jz      short loc_180001744
0x1800016fb  mov     rax, [r15+8]
0x1800016ff  test    rax, rax
0x180001702  jz      short loc_180001744
0x180001704  mov     eax, [rax+8]
0x180001707  test    eax, eax
0x180001709  jz      short loc_180001744
0x18000170b  mov     rdx, [rbx]
0x18000170e  mov     rcx, [r15]
0x180001711  call    ?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV1@@Z; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> const &)
0x180001716  test    al, al
0x180001718  jz      short loc_180001744
0x18000171a  test    sil, sil
0x18000171d  jz      short loc_180001740
0x18000171f  mov     rcx, [rdi+58h]; Resource
0x180001723  test    rcx, rcx
0x180001726  jz      short loc_180001740
0x180001728  call    cs:__imp_ExReleaseResourceLite
0x18000172f  nop     dword ptr [rax+rax+00h]
0x180001734  call    cs:__imp_KeLeaveCriticalRegion
0x18000173b  nop     dword ptr [rax+rax+00h]
0x180001740  xor     eax, eax
0x180001742  jmp     short loc_18000176F
0x180001744  test    sil, sil
0x180001747  jz      short loc_18000176A
0x180001749  mov     rcx, [rdi+58h]; Resource
0x18000174d  test    rcx, rcx
0x180001750  jz      short loc_18000176A
0x180001752  call    cs:__imp_ExReleaseResourceLite
0x180001759  nop     dword ptr [rax+rax+00h]
0x18000175e  call    cs:__imp_KeLeaveCriticalRegion
0x180001765  nop     dword ptr [rax+rax+00h]
0x18000176a  mov     eax, 0C000009Ah
0x18000176f  mov     rbx, [rsp+58h+arg_0]
0x180001774  add     rsp, 30h
0x180001778  pop     r15
0x18000177a  pop     r14
0x18000177c  pop     rdi
0x18000177d  pop     rsi
0x18000177e  pop     rbp
0x18000177f  retn
```
