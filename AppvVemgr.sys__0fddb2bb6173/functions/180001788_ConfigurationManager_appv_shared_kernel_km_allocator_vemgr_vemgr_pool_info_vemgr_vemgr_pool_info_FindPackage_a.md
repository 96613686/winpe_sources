# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180001788`
- end: `0x180001994`
- name: `??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180007840`

## callees

- `0x1800011ec`
- `0x180001788`
- `0x180002f20`
- `0x1800046d4`
- `0x18000d184`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180001877`
- `ntoskrnl!ExAllocatePool2` at `0x180001877`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001842`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000193f`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001969`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001842`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000193f`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001969`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000184e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000194b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001975`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000184e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000194b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001975`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800017cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800017cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800017b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800017b7`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  bool v8; // si
  _QWORD *v9; // rbx
  struct _ERESOURCE *v10; // rcx
  void *Pool2; // rax
  void *v12; // rbp
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // r14
  __int64 v17; // rax
  struct _ERESOURCE *v18; // rcx
  struct _ERESOURCE *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-58h] BYREF
  volatile signed __int32 *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  char v23; // [rsp+38h] [rbp-40h]
  _QWORD *v24; // [rsp+88h] [rbp+10h] BYREF

  if ( *(_DWORD *)a2 <= 2u )
    return 3221225485LL;
  v8 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v8 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v20 = a2;
  v23 = 0;
  if ( a2 != -16 )
  {
    v22 = *(_QWORD *)(a2 + 24);
    WORD1(v21) = *(_WORD *)(a2 + 16);
    LOWORD(v21) = WORD1(v21);
  }
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a1,
    (__int64)&v24,
    (__int64)&v20);
  v9 = v24;
  if ( v24 == (_QWORD *)(a1 + 8) )
  {
    if ( v8 )
    {
      v10 = *(struct _ERESOURCE **)(a1 + 88);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
  else
  {
    Pool2 = (void *)ExAllocatePool2(64, 136, 1715758931);
    v12 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x88u);
      Pool2 = (void *)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v12);
    }
    v13 = kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
            &v20,
            Pool2);
    v14 = *v13;
    *v13 = *a4;
    *a4 = v14;
    v15 = a4[1];
    a4[1] = v13[1];
    v13[1] = v15;
    v16 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    if ( *a4
      && (v17 = a4[1]) != 0
      && *(_DWORD *)(v17 + 8)
      && (unsigned __int8)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
                            *a4,
                            *v9) )
    {
      if ( v8 )
      {
        v18 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v18 )
        {
          ExReleaseResourceLite(v18);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
    else
    {
      if ( v8 )
      {
        v19 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v19 )
        {
          ExReleaseResourceLite(v19);
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
0x180001788  push    rbx
0x18000178a  push    rbp
0x18000178b  push    rsi
0x18000178c  push    rdi
0x18000178d  push    r14
0x18000178f  push    r15
0x180001791  sub     rsp, 48h
0x180001795  cmp     dword ptr [rdx], 2
0x180001798  mov     r15, r9
0x18000179b  mov     rbx, rdx
0x18000179e  mov     rdi, rcx
0x1800017a1  ja      short loc_1800017AD
0x1800017a3  mov     eax, 0C000000Dh
0x1800017a8  jmp     loc_180001986
0x1800017ad  xor     sil, sil
0x1800017b0  cmp     qword ptr [rcx+58h], 0
0x1800017b5  jz      short loc_1800017E5
0x1800017b7  call    cs:__imp_KeEnterCriticalRegion
0x1800017be  nop     dword ptr [rax+rax+00h]
0x1800017c3  mov     rcx, [rdi+58h]; Resource
0x1800017c7  mov     ebp, 1
0x1800017cc  mov     dl, bpl; Wait
0x1800017cf  call    cs:__imp_ExAcquireResourceSharedLite
0x1800017d6  nop     dword ptr [rax+rax+00h]
0x1800017db  cmp     al, bpl
0x1800017de  movzx   esi, sil
0x1800017e2  cmovz   esi, ebp
0x1800017e5  lea     rcx, [rbx+10h]
0x1800017e9  mov     [rsp+78h+var_58], rbx
0x1800017ee  mov     [rsp+78h+var_40], 0
0x1800017f3  test    rcx, rcx
0x1800017f6  jz      short loc_18000180E
0x1800017f8  mov     rax, [rbx+18h]
0x1800017fc  mov     [rsp+78h+var_48], rax
0x180001801  movzx   eax, word ptr [rcx]
0x180001804  mov     word ptr [rsp+78h+var_50+2], ax
0x180001809  mov     word ptr [rsp+78h+var_50], ax
0x18000180e  lea     r8, [rsp+78h+var_58]
0x180001813  mov     rcx, rdi
0x180001816  lea     rdx, [rsp+78h+arg_8]
0x18000181e  call    ??$find_first_element@U?$find_by_package_root@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_package_root@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180001823  mov     rbx, [rsp+78h+arg_8]
0x18000182b  lea     rax, [rdi+8]
0x18000182f  cmp     rbx, rax
0x180001832  jnz     short loc_180001864
0x180001834  test    sil, sil
0x180001837  jz      short loc_18000185A
0x180001839  mov     rcx, [rdi+58h]; Resource
0x18000183d  test    rcx, rcx
0x180001840  jz      short loc_18000185A
0x180001842  call    cs:__imp_ExReleaseResourceLite
0x180001849  nop     dword ptr [rax+rax+00h]
0x18000184e  call    cs:__imp_KeLeaveCriticalRegion
0x180001855  nop     dword ptr [rax+rax+00h]
0x18000185a  mov     eax, 0C0000034h
0x18000185f  jmp     loc_180001986
0x180001864  mov     r14d, 88h
0x18000186a  mov     r8d, 66446753h
0x180001870  mov     edx, r14d
0x180001873  lea     ecx, [r14-48h]
0x180001877  call    cs:__imp_ExAllocatePool2
0x18000187e  nop     dword ptr [rax+rax+00h]
0x180001883  mov     rbp, rax
0x180001886  test    rax, rax
0x180001889  jz      short loc_1800018A0
0x18000188b  mov     r8d, r14d; Size
0x18000188e  xor     edx, edx; Val
0x180001890  mov     rcx, rax; void *
0x180001893  call    memset
0x180001898  mov     rcx, rbp
0x18000189b  call    ??0?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x1800018a0  mov     rdx, rax
0x1800018a3  lea     rcx, [rsp+78h+var_58]
0x1800018a8  call    ??$?0V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x1800018ad  mov     rcx, [r15]
0x1800018b0  mov     rdx, [rax]
0x1800018b3  mov     [rax], rcx
0x1800018b6  mov     [r15], rdx
0x1800018b9  mov     rcx, [rax+8]
0x1800018bd  mov     rdx, [r15+8]
0x1800018c1  mov     [r15+8], rcx
0x1800018c5  mov     [rax+8], rdx
0x1800018c9  mov     r14, [rsp+78h+var_50]
0x1800018ce  test    r14, r14
0x1800018d1  jz      short loc_18000190C
0x1800018d3  or      ebp, 0FFFFFFFFh
0x1800018d6  mov     eax, ebp
0x1800018d8  lock xadd [r14+8], eax
0x1800018de  add     eax, ebp
0x1800018e0  jnz     short loc_18000190C
0x1800018e2  mov     rax, [r14]
0x1800018e5  mov     rcx, r14
0x1800018e8  mov     rax, [rax+8]
0x1800018ec  call    _guard_dispatch_icall
0x1800018f1  mov     eax, ebp
0x1800018f3  lock xadd [r14+0Ch], eax
0x1800018f9  add     eax, ebp
0x1800018fb  jnz     short loc_18000190C
0x1800018fd  mov     rax, [r14]
0x180001900  mov     rcx, r14
0x180001903  mov     rax, [rax+10h]
0x180001907  call    _guard_dispatch_icall
0x18000190c  cmp     qword ptr [r15], 0
0x180001910  jz      short loc_18000195B
0x180001912  mov     rax, [r15+8]
0x180001916  test    rax, rax
0x180001919  jz      short loc_18000195B
0x18000191b  mov     eax, [rax+8]
0x18000191e  test    eax, eax
0x180001920  jz      short loc_18000195B
0x180001922  mov     rdx, [rbx]
0x180001925  mov     rcx, [r15]
0x180001928  call    ?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV1@@Z; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> const &)
0x18000192d  test    al, al
0x18000192f  jz      short loc_18000195B
0x180001931  test    sil, sil
0x180001934  jz      short loc_180001957
0x180001936  mov     rcx, [rdi+58h]; Resource
0x18000193a  test    rcx, rcx
0x18000193d  jz      short loc_180001957
0x18000193f  call    cs:__imp_ExReleaseResourceLite
0x180001946  nop     dword ptr [rax+rax+00h]
0x18000194b  call    cs:__imp_KeLeaveCriticalRegion
0x180001952  nop     dword ptr [rax+rax+00h]
0x180001957  xor     eax, eax
0x180001959  jmp     short loc_180001986
0x18000195b  test    sil, sil
0x18000195e  jz      short loc_180001981
0x180001960  mov     rcx, [rdi+58h]; Resource
0x180001964  test    rcx, rcx
0x180001967  jz      short loc_180001981
0x180001969  call    cs:__imp_ExReleaseResourceLite
0x180001970  nop     dword ptr [rax+rax+00h]
0x180001975  call    cs:__imp_KeLeaveCriticalRegion
0x18000197c  nop     dword ptr [rax+rax+00h]
0x180001981  mov     eax, 0C000009Ah
0x180001986  add     rsp, 48h
0x18000198a  pop     r15
0x18000198c  pop     r14
0x18000198e  pop     rdi
0x18000198f  pop     rsi
0x180001990  pop     rbp
0x180001991  pop     rbx
0x180001992  retn
```
