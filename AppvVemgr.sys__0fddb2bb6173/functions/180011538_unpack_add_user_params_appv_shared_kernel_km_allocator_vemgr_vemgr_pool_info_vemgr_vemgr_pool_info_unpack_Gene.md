# unpack_add_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(uchar const *,ulong,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180011538`
- end: `0x180011bca`
- name: `??$unpack@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$unpack_add_user_params@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKAEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `1682`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012a2c`

## callees

- `0x180001398`
- `0x180001504`
- `0x180004764`
- `0x180005178`
- `0x18000a9e4`
- `0x18000ad50`
- `0x180011538`
- `0x180011e9c`
- `0x180013b78`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180011808`
- `ntoskrnl!ExAllocatePool2` at `0x180011808`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800116f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011708`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001171f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a50`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011bb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800116f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011708`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001171f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800119ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a50`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011bb7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180011584`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001159e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800115b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x180011584`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001159e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800115b9`

## pseudocode

```c
__int64 __fastcall unpack_add_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3)
{
  __int64 v6; // r12
  unsigned int v7; // edi
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // esi
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  bool v15; // r13
  unsigned int v16; // eax
  volatile signed __int32 *v17; // rbx
  int v19; // eax
  void *v20; // r14
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rcx
  void *Pool2; // rax
  void *v24; // rdi
  void *v25; // rax
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  volatile signed __int32 *v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // r10d
  int v33; // r9d
  int v34; // r8d
  int v35; // edx
  char v36; // bl
  bool v37; // zf
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int128 *v42; // [rsp+68h] [rbp-98h]
  __int128 *v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  PVOID v48; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v51; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v52; // [rsp+C8h] [rbp-38h] BYREF
  int v53; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v54; // [rsp+E0h] [rbp-20h] BYREF
  __int128 *v55; // [rsp+F0h] [rbp-10h]
  __int128 *v56; // [rsp+F8h] [rbp-8h]
  __int64 v57; // [rsp+100h] [rbp+0h] BYREF
  volatile signed __int32 *v58; // [rsp+108h] [rbp+8h]
  char v59; // [rsp+160h] [rbp+60h]

  if ( !a1 || a2 < 0x1A )
    return 3221225990LL;
  v6 = a1 + 26;
  v47 = 0;
  v7 = a2 - 26;
  v48 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v50 = 0;
  v51 = 0;
  RtlInitUnicodeString(&v52, 0);
  v44 = 0;
  P = 0;
  RtlInitUnicodeString(&v46, 0);
  v8 = *(unsigned __int16 *)(a1 + 6);
  v9 = *(unsigned __int16 *)(a1 + 4);
  v43 = &v41;
  v42 = &v41;
  v40 = 0;
  v41 = 0;
  if ( __PAIR32__(v8, v9) )
  {
    if ( (unsigned int)v9 > v7 || (int)v9 + (int)v8 > v7 )
      goto LABEL_92;
    v10 = v6 + v9;
  }
  else
  {
    v10 = 0;
  }
  v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          &v47,
          v10,
          v8 >> 1);
  if ( v11 < 0 )
    goto LABEL_93;
  v12 = *(unsigned __int16 *)(a1 + 10);
  v13 = *(unsigned __int16 *)(a1 + 8);
  if ( !__PAIR32__(v12, v13) )
  {
    v14 = 0;
    goto LABEL_14;
  }
  if ( (unsigned int)v13 > v7 || (int)v13 + (int)v12 > v7 )
  {
LABEL_92:
    v11 = -1073741811;
LABEL_93:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v21 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) )
    {
LABEL_94:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
LABEL_97:
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v51 )
      ExFreePoolWithTag(v51, 0);
    if ( v48 )
      ExFreePoolWithTag(v48, 0);
    return (unsigned int)v11;
  }
  v14 = v6 + v13;
LABEL_14:
  v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          &v50,
          v14,
          v12 >> 1);
  if ( v11 < 0 )
    goto LABEL_93;
  v59 = (*(_DWORD *)(a1 + 12) & 4) != 0;
  v15 = (*(_DWORD *)(a1 + 12) & 8) != 0;
  v16 = *(_DWORD *)(a1 + 20) + 26;
  if ( v16 > a2 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v17 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v51 )
      ExFreePoolWithTag(v51, 0);
    if ( v48 )
      ExFreePoolWithTag(v48, 0);
    return 3221225990LL;
  }
  v19 = unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(
          a1 + v16,
          a2 - v16,
          *(unsigned __int16 *)(a1 + 24),
          &v40);
  v20 = 0;
  v11 = v19;
  if ( v19 < 0 )
  {
LABEL_28:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v21 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) )
      goto LABEL_94;
    goto LABEL_97;
  }
  v22 = *(unsigned __int16 *)(a1 + 16);
  if ( *(_DWORD *)(a1 + 16) )
  {
    if ( (unsigned int)v22 > v7 || *(unsigned __int16 *)(a1 + 18) + (unsigned int)v22 > v7 )
      goto LABEL_81;
    v20 = (void *)(v6 + v22);
    if ( v6 + v22 )
    {
      v11 = appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              v20,
              (__int64)&v44);
      if ( v11 < 0 )
        goto LABEL_28;
    }
  }
  if ( (unsigned int)v47 <= 2 || (unsigned int)v44 <= 2 || !v20 )
  {
LABEL_81:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v39 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 16LL))(v39);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v51 )
      ExFreePoolWithTag(v51, 0);
    if ( v48 )
      ExFreePoolWithTag(v48, 0);
    return 3221225485LL;
  }
  Pool2 = (void *)ExAllocatePool2(256, 192, 1733125462);
  v24 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0xC0u);
    v25 = (void *)Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v24);
  }
  else
  {
    v25 = 0;
  }
  v26 = kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
          &v57,
          v25);
  v27 = *v26;
  *v26 = *a3;
  *a3 = v27;
  v28 = a3[1];
  a3[1] = v26[1];
  v26[1] = v28;
  v29 = v58;
  if ( v58 )
  {
    if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
    }
  }
  if ( *a3 && (v30 = a3[1]) != 0 && *(_DWORD *)(v30 + 8) )
  {
    v31 = *a3;
    v32 = *(unsigned __int16 *)(a1 + 18);
    v56 = &v54;
    v53 = 0;
    v55 = &v54;
    v54 = 0;
    if ( (unsigned int)v44 >> 1 > 0xFFFF || (v33 = (int)P, !(unsigned __int16)((unsigned int)v44 >> 1)) )
      v33 = 0;
    if ( (unsigned int)v50 >> 1 > 0xFFFF || (v34 = (int)v51, !(unsigned __int16)((unsigned int)v50 >> 1)) )
      v34 = 0;
    if ( (unsigned int)v47 >> 1 > 0xFFFF || (v35 = (int)v48, !(unsigned __int16)((unsigned int)v47 >> 1)) )
      v35 = 0;
    v36 = Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
            v31,
            v35,
            v34,
            v33,
            (__int64)v20,
            v32,
            (__int64)&v40,
            (__int64)&v53,
            v59,
            v15);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(&v53);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v37 = v36 == 0;
    v38 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
    if ( !v37 )
    {
      if ( *((_QWORD *)&v41 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 16LL))(v38);
        }
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( v51 )
        ExFreePoolWithTag(v51, 0);
      if ( v48 )
        ExFreePoolWithTag(v48, 0);
      return 0;
    }
  }
  else
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v40);
    v38 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
  }
  if ( v38 )
  {
    if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v51 )
    ExFreePoolWithTag(v51, 0);
  if ( v48 )
    ExFreePoolWithTag(v48, 0);
  return 3221225626LL;
}

```

## disassembly

```asm
0x180011538  push    rbp
0x18001153a  push    rbx
0x18001153b  push    rsi
0x18001153c  push    rdi
0x18001153d  push    r12
0x18001153f  push    r13
0x180011541  push    r14
0x180011543  push    r15
0x180011545  lea     rbp, [rsp-18h]
0x18001154a  sub     rsp, 118h
0x180011551  xor     r13d, r13d
0x180011554  mov     r15, r8
0x180011557  mov     r14d, edx
0x18001155a  mov     rbx, rcx
0x18001155d  test    rcx, rcx
0x180011560  jz      loc_18001172B
0x180011566  cmp     edx, 1Ah
0x180011569  jb      loc_18001172B
0x18001156f  lea     r12, [rcx+1Ah]
0x180011573  mov     [rbp+50h+var_B8], r13
0x180011577  lea     edi, [rdx-1Ah]
0x18001157a  mov     [rbp+50h+var_B0], r13
0x18001157e  xor     edx, edx; SourceString
0x180011580  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x180011584  call    cs:__imp_RtlInitUnicodeString
0x18001158b  nop     dword ptr [rax+rax+00h]
0x180011590  xor     edx, edx; SourceString
0x180011592  mov     [rbp+50h+var_98], r13
0x180011596  lea     rcx, [rbp+50h+var_88]; DestinationString
0x18001159a  mov     [rbp+50h+var_90], r13
0x18001159e  call    cs:__imp_RtlInitUnicodeString
0x1800115a5  nop     dword ptr [rax+rax+00h]
0x1800115aa  xor     edx, edx; SourceString
0x1800115ac  mov     [rsp+150h+var_D8], r13
0x1800115b1  lea     rcx, [rbp+50h+var_C8]; DestinationString
0x1800115b5  mov     [rbp+50h+P], r13
0x1800115b9  call    cs:__imp_RtlInitUnicodeString
0x1800115c0  nop     dword ptr [rax+rax+00h]
0x1800115c5  movzx   r8d, word ptr [rbx+6]
0x1800115ca  lea     rax, [rsp+150h+var_F8]
0x1800115cf  movzx   ecx, word ptr [rbx+4]
0x1800115d3  xorps   xmm0, xmm0
0x1800115d6  mov     [rsp+150h+var_E0], rax
0x1800115db  lea     rax, [rsp+150h+var_F8]
0x1800115e0  mov     [rsp+150h+var_E8], rax
0x1800115e5  mov     [rsp+150h+var_100], r13d
0x1800115ea  movdqu  [rsp+150h+var_F8], xmm0
0x1800115f0  test    r8w, r8w
0x1800115f4  jnz     short loc_180011600
0x1800115f6  test    cx, cx
0x1800115f9  jnz     short loc_180011600
0x1800115fb  mov     edx, r13d
0x1800115fe  jmp     short loc_180011618
0x180011600  cmp     ecx, edi
0x180011602  ja      loc_180011B2E
0x180011608  lea     eax, [rcx+r8]
0x18001160c  cmp     eax, edi
0x18001160e  ja      loc_180011B2E
0x180011614  lea     rdx, [r12+rcx]
0x180011618  shr     r8, 1
0x18001161b  lea     rcx, [rbp+50h+var_B8]
0x18001161f  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180011624  mov     esi, eax
0x180011626  test    eax, eax
0x180011628  js      loc_180011B33
0x18001162e  movzx   r8d, word ptr [rbx+0Ah]
0x180011633  movzx   ecx, word ptr [rbx+8]
0x180011637  test    r8w, r8w
0x18001163b  jnz     short loc_180011647
0x18001163d  test    cx, cx
0x180011640  jnz     short loc_180011647
0x180011642  mov     rdx, r13
0x180011645  jmp     short loc_18001165F
0x180011647  cmp     ecx, edi
0x180011649  ja      loc_180011B2E
0x18001164f  lea     eax, [rcx+r8]
0x180011653  cmp     eax, edi
0x180011655  ja      loc_180011B2E
0x18001165b  lea     rdx, [r12+rcx]
0x18001165f  shr     r8, 1
0x180011662  lea     rcx, [rbp+50h+var_98]
0x180011666  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18001166b  mov     esi, eax
0x18001166d  test    eax, eax
0x18001166f  js      loc_180011B33
0x180011675  mov     r13d, [rbx+0Ch]
0x180011679  mov     eax, r13d
0x18001167c  shr     eax, 2
0x18001167f  and     al, 1
0x180011681  shr     r13d, 3
0x180011685  mov     [rbp+50h+arg_0], eax
0x180011688  and     r13b, 1
0x18001168c  mov     eax, [rbx+14h]
0x18001168f  add     eax, 1Ah
0x180011692  cmp     eax, r14d
0x180011695  jbe     loc_180011745
0x18001169b  lea     rcx, [rsp+150h+var_100]
0x1800116a0  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x1800116a5  mov     rbx, qword ptr [rsp+150h+var_F8+8]
0x1800116aa  test    rbx, rbx
0x1800116ad  jz      short loc_1800116E6
0x1800116af  or      edi, 0FFFFFFFFh
0x1800116b2  mov     eax, edi
0x1800116b4  lock xadd [rbx+8], eax
0x1800116b9  add     eax, edi
0x1800116bb  jnz     short loc_1800116E6
0x1800116bd  mov     rax, [rbx]
0x1800116c0  mov     rcx, rbx
0x1800116c3  mov     rax, [rax+8]
0x1800116c7  call    _guard_dispatch_icall
0x1800116cc  mov     eax, edi
0x1800116ce  lock xadd [rbx+0Ch], eax
0x1800116d3  add     eax, edi
0x1800116d5  jnz     short loc_1800116E6
0x1800116d7  mov     rax, [rbx]
0x1800116da  mov     rcx, rbx
0x1800116dd  mov     rax, [rax+10h]
0x1800116e1  call    _guard_dispatch_icall
0x1800116e6  mov     rcx, [rbp+50h+P]; P
0x1800116ea  test    rcx, rcx
0x1800116ed  jz      short loc_1800116FD
0x1800116ef  xor     edx, edx; Tag
0x1800116f1  call    cs:__imp_ExFreePoolWithTag
0x1800116f8  nop     dword ptr [rax+rax+00h]
0x1800116fd  mov     rcx, [rbp+50h+var_90]; P
0x180011701  test    rcx, rcx
0x180011704  jz      short loc_180011714
0x180011706  xor     edx, edx; Tag
0x180011708  call    cs:__imp_ExFreePoolWithTag
0x18001170f  nop     dword ptr [rax+rax+00h]
0x180011714  mov     rcx, [rbp+50h+var_B0]; P
0x180011718  test    rcx, rcx
0x18001171b  jz      short loc_18001172B
0x18001171d  xor     edx, edx; Tag
0x18001171f  call    cs:__imp_ExFreePoolWithTag
0x180011726  nop     dword ptr [rax+rax+00h]
0x18001172b  mov     eax, 0C0000206h
0x180011730  add     rsp, 118h
0x180011737  pop     r15
0x180011739  pop     r14
0x18001173b  pop     r13
0x18001173d  pop     r12
0x18001173f  pop     rdi
0x180011740  pop     rsi
0x180011741  pop     rbx
0x180011742  pop     rbp
0x180011743  retn
0x180011745  movzx   r8d, word ptr [rbx+18h]
0x18001174a  lea     r9, [rsp+150h+var_100]
0x18001174f  sub     r14d, eax
0x180011752  mov     ecx, eax
0x180011754  add     rcx, rbx
0x180011757  mov     edx, r14d
0x18001175a  call    ??$unpack_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$unpack_vfs_mappings@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKGAEAV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(uchar const *,ulong,ushort,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18001175f  xor     r14d, r14d
0x180011762  mov     esi, eax
0x180011764  test    eax, eax
0x180011766  jns     short loc_180011791
0x180011768  lea     rcx, [rsp+150h+var_100]
0x18001176d  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180011772  mov     rbx, qword ptr [rsp+150h+var_F8+8]
0x180011777  test    rbx, rbx
0x18001177a  jz      loc_180011B7E
0x180011780  or      edi, 0FFFFFFFFh
0x180011783  mov     ecx, edi
0x180011785  lock xadd [rbx+8], ecx
0x18001178a  add     ecx, edi
0x18001178c  jmp     loc_180011B53
0x180011791  movzx   edx, word ptr [rbx+12h]
0x180011795  movzx   ecx, word ptr [rbx+10h]
0x180011799  test    edx, edx
0x18001179b  jnz     short loc_1800117A7
0x18001179d  test    cx, cx
0x1800117a0  jnz     short loc_1800117A7
0x1800117a2  xor     r12d, r12d
0x1800117a5  jmp     short loc_1800117DA
0x1800117a7  mov     eax, ecx
0x1800117a9  cmp     ecx, edi
0x1800117ab  ja      loc_180011A94
0x1800117b1  add     eax, edx
0x1800117b3  cmp     eax, edi
0x1800117b5  ja      loc_180011A94
0x1800117bb  lea     r14, [r12+rcx]
0x1800117bf  xor     r12d, r12d
0x1800117c2  test    r14, r14
0x1800117c5  jz      short loc_1800117DA
0x1800117c7  lea     rdx, [rsp+150h+var_D8]
0x1800117cc  mov     rcx, r14; Sid
0x1800117cf  call    ??$ConvertSid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800117d4  mov     esi, eax
0x1800117d6  test    eax, eax
0x1800117d8  js      short loc_180011768
0x1800117da  cmp     dword ptr [rbp+50h+var_B8], 2
0x1800117de  jbe     loc_180011A94
0x1800117e4  cmp     dword ptr [rsp+150h+var_D8], 2
0x1800117e9  jbe     loc_180011A94
0x1800117ef  test    r14, r14
0x1800117f2  jz      loc_180011A94
0x1800117f8  mov     esi, 0C0h
0x1800117fd  mov     r8d, 674D6556h
0x180011803  mov     edx, esi
0x180011805  lea     ecx, [rsi+40h]
0x180011808  call    cs:__imp_ExAllocatePool2
0x18001180f  nop     dword ptr [rax+rax+00h]
0x180011814  mov     rdi, rax
0x180011817  test    rax, rax
0x18001181a  jz      short loc_180011833
0x18001181c  mov     r8d, esi; Size
0x18001181f  xor     edx, edx; Val
0x180011821  mov     rcx, rax; void *
0x180011824  call    memset
0x180011829  mov     rcx, rdi
0x18001182c  call    ??0?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x180011831  jmp     short loc_180011836
0x180011833  mov     rax, r12
0x180011836  mov     rdx, rax
0x180011839  lea     rcx, [rbp+50h+var_50]
0x18001183d  call    ??$?0V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x180011842  mov     rcx, [r15]
0x180011845  or      edi, 0FFFFFFFFh
0x180011848  mov     rdx, [rax]
0x18001184b  mov     [rax], rcx
0x18001184e  mov     [r15], rdx
0x180011851  mov     rcx, [rax+8]
0x180011855  mov     rdx, [r15+8]
0x180011859  mov     [r15+8], rcx
0x18001185d  mov     [rax+8], rdx
0x180011861  mov     rsi, [rbp+50h+var_48]
0x180011865  test    rsi, rsi
0x180011868  jz      short loc_18001189E
0x18001186a  mov     eax, edi
0x18001186c  lock xadd [rsi+8], eax
0x180011871  add     eax, edi
0x180011873  jnz     short loc_18001189E
0x180011875  mov     rax, [rsi]
0x180011878  mov     rcx, rsi
0x18001187b  mov     rax, [rax+8]
0x18001187f  call    _guard_dispatch_icall
0x180011884  mov     eax, edi
0x180011886  lock xadd [rsi+0Ch], eax
0x18001188b  add     eax, edi
0x18001188d  jnz     short loc_18001189E
0x18001188f  mov     rax, [rsi]
0x180011892  mov     rcx, rsi
0x180011895  mov     rax, [rax+10h]
0x180011899  call    _guard_dispatch_icall
0x18001189e  cmp     [r15], r12
0x1800118a1  jz      loc_1800119FD
0x1800118a7  mov     rax, [r15+8]
0x1800118ab  test    rax, rax
0x1800118ae  jz      loc_1800119FD
0x1800118b4  mov     eax, [rax+8]
0x1800118b7  test    eax, eax
0x1800118b9  jz      loc_1800119FD
0x1800118bf  mov     rcx, [r15]
0x1800118c2  lea     rax, [rbp+50h+var_70]
0x1800118c6  movzx   r10d, word ptr [rbx+12h]
0x1800118cb  mov     edx, 0FFFFh
0x1800118d0  mov     [rbp+50h+var_58], rax
0x1800118d4  xorps   xmm0, xmm0
0x1800118d7  lea     rax, [rbp+50h+var_70]
0x1800118db  mov     [rbp+50h+var_78], r12d
0x1800118df  mov     [rbp+50h+var_60], rax
0x1800118e3  mov     eax, dword ptr [rsp+150h+var_D8]
0x1800118e7  shr     eax, 1
0x1800118e9  movdqu  [rbp+50h+var_70], xmm0
0x1800118ee  cmp     eax, edx
0x1800118f0  ja      short loc_1800118FB
0x1800118f2  mov     r9, [rbp+50h+P]
0x1800118f6  test    ax, ax
0x1800118f9  jnz     short loc_1800118FE
0x1800118fb  mov     r9, r12
0x1800118fe  mov     eax, dword ptr [rbp+50h+var_98]
0x180011901  shr     eax, 1
0x180011903  cmp     eax, edx
0x180011905  ja      short loc_180011910
0x180011907  mov     r8, [rbp+50h+var_90]
0x18001190b  test    ax, ax
0x18001190e  jnz     short loc_180011913
0x180011910  mov     r8, r12
0x180011913  mov     eax, dword ptr [rbp+50h+var_B8]
0x180011916  shr     eax, 1
0x180011918  cmp     eax, edx
0x18001191a  ja      short loc_180011925
0x18001191c  mov     rdx, [rbp+50h+var_B0]
0x180011920  test    ax, ax
0x180011923  jnz     short loc_180011928
0x180011925  mov     rdx, r12
0x180011928  mov     eax, [rbp+50h+arg_0]
0x18001192b  mov     [rsp+150h+var_108], r13b
0x180011930  mov     [rsp+150h+var_110], al
0x180011934  lea     rax, [rbp+50h+var_78]
0x180011938  mov     [rsp+150h+var_118], rax
0x18001193d  lea     rax, [rsp+150h+var_100]
0x180011942  mov     [rsp+150h+var_120], rax
0x180011947  mov     [rsp+150h+var_128], r10d
0x18001194c  mov     [rsp+150h+var_130], r14
0x180011951  call    ?init@?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_W00PEAXKAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@_N4@Z; Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,wchar_t const *,wchar_t const *,void *,ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,bool,bool)
0x180011956  lea     rcx, [rbp+50h+var_78]
0x18001195a  mov     bl, al
  ... truncated ...
```
