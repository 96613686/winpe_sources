# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x18000199c`
- end: `0x180001be3`
- name: `??$FindPackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180001d4c`
- `0x1800071a0`
- `0x180016364`

## callees

- `0x18000129c`
- `0x18000199c`
- `0x180002e94`
- `0x18000d37c`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180001a5d`
- `ntoskrnl!ExAllocatePool2` at `0x180001a5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001a2e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001b8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001bb4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001a2e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001b8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001bb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001a3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001b96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001bc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001a3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001b96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001bc0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800019e8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800019e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800019d1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800019d1`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 *a3)
{
  bool v7; // bp
  __int64 **v8; // rbx
  struct _ERESOURCE *v9; // rcx
  _QWORD *Pool2; // rax
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rsi
  __int64 v17; // rax
  __int64 *v18; // rsi
  __int64 v19; // r14
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rbx
  _QWORD *v24; // rsi
  struct _ERESOURCE *v25; // rcx
  struct _ERESOURCE *v26; // rcx
  _BYTE v27[8]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v28; // [rsp+28h] [rbp-30h]
  const UNICODE_STRING *v29; // [rsp+68h] [rbp+10h] BYREF
  __int64 **v30; // [rsp+78h] [rbp+20h] BYREF

  if ( *(_DWORD *)&a2->Length <= 2u )
    return 3221225485LL;
  v7 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v7 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v29 = a2;
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a1 + 40,
    (__int64)&v30,
    &v29);
  v8 = v30;
  if ( v30 == (__int64 **)(a1 + 48) )
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
    Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1715758931);
    v11 = Pool2;
    if ( Pool2 )
    {
      Pool2[2] = 0;
      Pool2[7] = 0;
      *Pool2 = 0;
      Pool2[1] = 0;
      v12 = Pool2 + 3;
      *v12 = 0;
      v12[1] = 0;
      v12[3] = v12;
      v12[2] = v12;
    }
    else
    {
      v11 = 0;
    }
    v13 = (__int64 *)kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
                       v27,
                       v11);
    v14 = *v13;
    *v13 = *a3;
    *a3 = v14;
    v15 = a3[1];
    a3[1] = v13[1];
    v13[1] = v15;
    v16 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    if ( *a3
      && (v17 = a3[1]) != 0
      && *(_DWORD *)(v17 + 8)
      && ((v18 = *v8, v19 = *a3, v20 = **v8, v21 = *(_DWORD *)v20 >> 1, v21 > 0xFFFF) || !(_WORD)v21
        ? (v22 = 0)
        : (v22 = *(_QWORD *)(v20 + 8)),
          (unsigned __int8)Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
                             v19,
                             v22,
                             *((unsigned int *)*v8 + 14))
       && *((_DWORD *)v18 + 4)) )
    {
      v23 = (_QWORD *)v18[6];
      v24 = v18 + 3;
      while ( v23 != v24 )
      {
        if ( (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                    v19 + 16,
                    v23) < 0 )
          goto LABEL_34;
        v23 = (_QWORD *)v23[3];
      }
      if ( v7 )
      {
        v25 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v25 )
        {
          ExReleaseResourceLite(v25);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
    else
    {
LABEL_34:
      if ( v7 )
      {
        v26 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v26 )
        {
          ExReleaseResourceLite(v26);
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
0x18000199c  mov     [rsp+arg_0], rbx
0x1800019a1  push    rbp
0x1800019a2  push    rsi
0x1800019a3  push    rdi
0x1800019a4  push    r14
0x1800019a6  push    r15
0x1800019a8  sub     rsp, 30h
0x1800019ac  cmp     dword ptr [rdx], 2
0x1800019af  mov     r14, r8
0x1800019b2  mov     rbx, rdx
0x1800019b5  mov     rdi, rcx
0x1800019b8  ja      short loc_1800019C4
0x1800019ba  mov     eax, 0C000000Dh
0x1800019bf  jmp     loc_180001BD1
0x1800019c4  xor     r15d, r15d
0x1800019c7  movzx   ebp, r15b
0x1800019cb  cmp     [rcx+58h], r15
0x1800019cf  jz      short loc_1800019FA
0x1800019d1  call    cs:__imp_KeEnterCriticalRegion
0x1800019d8  nop     dword ptr [rax+rax+00h]
0x1800019dd  mov     rcx, [rdi+58h]; Resource
0x1800019e1  lea     esi, [r15+1]
0x1800019e5  mov     dl, sil; Wait
0x1800019e8  call    cs:__imp_ExAcquireResourceSharedLite
0x1800019ef  nop     dword ptr [rax+rax+00h]
0x1800019f4  cmp     al, sil
0x1800019f7  cmovz   ebp, esi
0x1800019fa  lea     rcx, [rdi+28h]
0x1800019fe  mov     [rsp+58h+arg_8], rbx
0x180001a03  lea     r8, [rsp+58h+arg_8]
0x180001a08  lea     rdx, [rsp+58h+arg_18]
0x180001a0d  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180001a12  mov     rbx, [rsp+58h+arg_18]
0x180001a17  lea     rax, [rdi+30h]
0x180001a1b  cmp     rbx, rax
0x180001a1e  jnz     short loc_180001A50
0x180001a20  test    bpl, bpl
0x180001a23  jz      short loc_180001A46
0x180001a25  mov     rcx, [rdi+58h]; Resource
0x180001a29  test    rcx, rcx
0x180001a2c  jz      short loc_180001A46
0x180001a2e  call    cs:__imp_ExReleaseResourceLite
0x180001a35  nop     dword ptr [rax+rax+00h]
0x180001a3a  call    cs:__imp_KeLeaveCriticalRegion
0x180001a41  nop     dword ptr [rax+rax+00h]
0x180001a46  mov     eax, 0C0000034h
0x180001a4b  jmp     loc_180001BD1
0x180001a50  mov     ecx, 40h ; '@'
0x180001a55  mov     r8d, 66446753h
0x180001a5b  mov     edx, ecx
0x180001a5d  call    cs:__imp_ExAllocatePool2
0x180001a64  nop     dword ptr [rax+rax+00h]
0x180001a69  mov     rdx, rax
0x180001a6c  test    rax, rax
0x180001a6f  jz      short loc_180001A95
0x180001a71  mov     [rax+10h], r15
0x180001a75  mov     [rax+38h], r15
0x180001a79  mov     [rax], r15
0x180001a7c  mov     [rax+8], r15
0x180001a80  add     rax, 18h
0x180001a84  mov     [rax], r15
0x180001a87  mov     [rax+8], r15
0x180001a8b  mov     [rax+18h], rax
0x180001a8f  mov     [rax+10h], rax
0x180001a93  jmp     short loc_180001A98
0x180001a95  mov     rdx, r15
0x180001a98  lea     rcx, [rsp+58h+var_38]
0x180001a9d  call    ??$?0V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x180001aa2  mov     rcx, [r14]
0x180001aa5  mov     rdx, [rax]
0x180001aa8  mov     [rax], rcx
0x180001aab  mov     [r14], rdx
0x180001aae  mov     rcx, [rax+8]
0x180001ab2  mov     rdx, [r14+8]
0x180001ab6  mov     [r14+8], rcx
0x180001aba  mov     [rax+8], rdx
0x180001abe  mov     rsi, [rsp+58h+var_30]
0x180001ac3  test    rsi, rsi
0x180001ac6  jz      short loc_180001B00
0x180001ac8  or      eax, 0FFFFFFFFh
0x180001acb  lock xadd [rsi+8], eax
0x180001ad0  cmp     eax, 1
0x180001ad3  jnz     short loc_180001B00
0x180001ad5  mov     rax, [rsi]
0x180001ad8  mov     rcx, rsi
0x180001adb  mov     rax, [rax+8]
0x180001adf  call    _guard_dispatch_icall
0x180001ae4  or      eax, 0FFFFFFFFh
0x180001ae7  lock xadd [rsi+0Ch], eax
0x180001aec  cmp     eax, 1
0x180001aef  jnz     short loc_180001B00
0x180001af1  mov     rax, [rsi]
0x180001af4  mov     rcx, rsi
0x180001af7  mov     rax, [rax+10h]
0x180001afb  call    _guard_dispatch_icall
0x180001b00  cmp     [r14], r15
0x180001b03  jz      loc_180001BA6
0x180001b09  mov     rax, [r14+8]
0x180001b0d  test    rax, rax
0x180001b10  jz      loc_180001BA6
0x180001b16  mov     eax, [rax+8]
0x180001b19  test    eax, eax
0x180001b1b  jz      loc_180001BA6
0x180001b21  mov     rsi, [rbx]
0x180001b24  mov     r14, [r14]
0x180001b27  mov     rdx, [rsi]
0x180001b2a  mov     r8d, [rsi+38h]
0x180001b2e  mov     eax, [rdx]
0x180001b30  shr     eax, 1
0x180001b32  cmp     eax, 0FFFFh
0x180001b37  ja      short loc_180001B44
0x180001b39  test    ax, ax
0x180001b3c  jz      short loc_180001B44
0x180001b3e  mov     rdx, [rdx+8]
0x180001b42  jmp     short loc_180001B47
0x180001b44  mov     rdx, r15
0x180001b47  mov     rcx, r14
0x180001b4a  call    ?init@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_WI@Z; Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,uint)
0x180001b4f  test    al, al
0x180001b51  jz      short loc_180001BA6
0x180001b53  cmp     [rsi+10h], r15d
0x180001b57  jz      short loc_180001BA6
0x180001b59  mov     rbx, [rsi+30h]
0x180001b5d  add     rsi, 18h
0x180001b61  cmp     rbx, rsi
0x180001b64  jz      short loc_180001B7C
0x180001b66  mov     rdx, rbx
0x180001b69  lea     rcx, [r14+10h]
0x180001b6d  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180001b72  test    eax, eax
0x180001b74  js      short loc_180001BA6
0x180001b76  mov     rbx, [rbx+18h]
0x180001b7a  jmp     short loc_180001B61
0x180001b7c  test    bpl, bpl
0x180001b7f  jz      short loc_180001BA2
0x180001b81  mov     rcx, [rdi+58h]; Resource
0x180001b85  test    rcx, rcx
0x180001b88  jz      short loc_180001BA2
0x180001b8a  call    cs:__imp_ExReleaseResourceLite
0x180001b91  nop     dword ptr [rax+rax+00h]
0x180001b96  call    cs:__imp_KeLeaveCriticalRegion
0x180001b9d  nop     dword ptr [rax+rax+00h]
0x180001ba2  xor     eax, eax
0x180001ba4  jmp     short loc_180001BD1
0x180001ba6  test    bpl, bpl
0x180001ba9  jz      short loc_180001BCC
0x180001bab  mov     rcx, [rdi+58h]; Resource
0x180001baf  test    rcx, rcx
0x180001bb2  jz      short loc_180001BCC
0x180001bb4  call    cs:__imp_ExReleaseResourceLite
0x180001bbb  nop     dword ptr [rax+rax+00h]
0x180001bc0  call    cs:__imp_KeLeaveCriticalRegion
0x180001bc7  nop     dword ptr [rax+rax+00h]
0x180001bcc  mov     eax, 0C000009Ah
0x180001bd1  mov     rbx, [rsp+58h+arg_0]
0x180001bd6  add     rsp, 30h
0x180001bda  pop     r15
0x180001bdc  pop     r14
0x180001bde  pop     rdi
0x180001bdf  pop     rsi
0x180001be0  pop     rbp
0x180001be1  retn
```
