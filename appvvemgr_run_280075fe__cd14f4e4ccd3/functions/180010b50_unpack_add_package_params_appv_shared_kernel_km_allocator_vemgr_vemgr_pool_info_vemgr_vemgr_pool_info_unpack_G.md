# unpack_add_package_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(uchar const *,ulong,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180010b50`
- end: `0x1800110e0`
- name: `??$unpack@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$unpack_add_package_params@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKAEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `1424`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180012804`

## callees

- `0x1800011ec`
- `0x1800046d4`
- `0x18000a9e4`
- `0x18000ad50`
- `0x18000d250`
- `0x180010b50`
- `0x180011e9c`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180010ddc`
- `ntoskrnl!ExAllocatePool2` at `0x180010ddc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010da5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010fc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011030`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011047`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800110b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800110cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010da5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010fc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011030`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011047`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800110b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800110cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x180010b9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180010bb6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180010b9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180010bb6`

## pseudocode

```c
__int64 __fastcall unpack_add_package_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3)
{
  __int64 v6; // r12
  unsigned int v7; // r14d
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // edi
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // r12d
  unsigned int v16; // eax
  char v17; // r14
  volatile signed __int32 *v18; // rdi
  int v20; // esi
  volatile signed __int32 *v21; // rdi
  void *Pool2; // rax
  void *v23; // rbx
  __int64 v24; // rax
  __int64 *v25; // rax
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rdx
  volatile signed __int32 *v29; // rdi
  __int64 v30; // rax
  char v31; // r12
  int v32; // r8d
  int v33; // edx
  volatile signed __int32 *v34; // rdi
  volatile signed __int32 *v35; // rdi
  volatile signed __int32 *v36; // rdi
  volatile signed __int32 *v37; // rsi
  _BYTE v38[8]; // [rsp+30h] [rbp-69h] BYREF
  volatile signed __int32 *v39; // [rsp+38h] [rbp-61h]
  __int64 v40; // [rsp+40h] [rbp-59h] BYREF
  PVOID P; // [rsp+48h] [rbp-51h]
  struct _UNICODE_STRING v42; // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+60h] [rbp-39h] BYREF
  PVOID v44; // [rsp+68h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  int v46; // [rsp+80h] [rbp-19h] BYREF
  __int128 v47; // [rsp+88h] [rbp-11h] BYREF
  __int128 *v48; // [rsp+98h] [rbp-1h]
  __int128 *v49; // [rsp+A0h] [rbp+7h]

  if ( !a1 || a2 < 0x16 )
    return 3221225990LL;
  v6 = a1 + 22;
  v43 = 0;
  v7 = a2 - 22;
  v44 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v40 = 0;
  P = 0;
  RtlInitUnicodeString(&v42, 0);
  v8 = *(unsigned __int16 *)(a1 + 6);
  v9 = *(unsigned __int16 *)(a1 + 4);
  v49 = &v47;
  v48 = &v47;
  v46 = 0;
  v47 = 0;
  if ( __PAIR32__(v8, v9) )
  {
    if ( (unsigned int)v9 > v7 || (int)v9 + (int)v8 > v7 )
      goto LABEL_81;
    v10 = v6 + v9;
  }
  else
  {
    v10 = 0;
  }
  v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          &v43,
          v10,
          v8 >> 1);
  if ( v11 < 0 )
    goto LABEL_82;
  v12 = *(unsigned __int16 *)(a1 + 10);
  v13 = *(unsigned __int16 *)(a1 + 8);
  if ( !__PAIR32__(v12, v13) )
  {
    v14 = 0;
    goto LABEL_14;
  }
  if ( (unsigned int)v13 > v7 || (int)v13 + (int)v12 > v7 )
  {
LABEL_81:
    v11 = -1073741811;
LABEL_82:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
    v37 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v44 )
      ExFreePoolWithTag(v44, 0);
    return (unsigned int)v11;
  }
  v14 = v6 + v13;
LABEL_14:
  v11 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          &v40,
          v14,
          v12 >> 1);
  if ( v11 < 0 )
    goto LABEL_82;
  v15 = *(_DWORD *)(a1 + 12);
  v16 = *(_DWORD *)(a1 + 16) + 22;
  v17 = (v15 & 2) != 0;
  if ( v16 > a2 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v44 )
      ExFreePoolWithTag(v44, 0);
    return 3221225990LL;
  }
  v20 = unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(
          a1 + v16,
          a2 - v16,
          *(unsigned __int16 *)(a1 + 20),
          &v46);
  if ( v20 >= 0 )
  {
    if ( (unsigned int)v43 <= 2 || (unsigned int)v40 <= 2 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
      v36 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 16LL))(v36);
        }
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( v44 )
        ExFreePoolWithTag(v44, 0);
      return 3221225485LL;
    }
    else
    {
      Pool2 = (void *)ExAllocatePool2(256, 136, 1733125462);
      v23 = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, 0x88u);
        v24 = Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v23);
      }
      else
      {
        v24 = 0;
      }
      v25 = (__int64 *)kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
                         v38,
                         v24);
      v27 = *v25;
      *v25 = *a3;
      *a3 = v27;
      v28 = a3[1];
      a3[1] = v25[1];
      v25[1] = v28;
      v29 = v39;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
        }
      }
      if ( !*a3 )
        goto LABEL_63;
      v30 = a3[1];
      if ( !v30 || !*(_DWORD *)(v30 + 8) )
        goto LABEL_63;
      v31 = v15 & 1;
      if ( (unsigned int)v40 >> 1 > 0xFFFF || (v32 = (int)P, !(unsigned __int16)((unsigned int)v40 >> 1)) )
        v32 = 0;
      if ( (unsigned int)v43 >> 1 > 0xFFFF || (v33 = (int)v44, !(unsigned __int16)((unsigned int)v43 >> 1)) )
        v33 = 0;
      LOBYTE(v26) = v31;
      if ( (unsigned __int8)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
                              *a3,
                              v33,
                              v32,
                              v26,
                              v17,
                              (__int64)&v46) )
      {
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
        v34 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 16LL))(v34);
          }
        }
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v44 )
          ExFreePoolWithTag(v44, 0);
        return 0;
      }
      else
      {
LABEL_63:
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
        v35 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
            if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 16LL))(v35);
          }
        }
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v44 )
          ExFreePoolWithTag(v44, 0);
        return 3221225626LL;
      }
    }
  }
  else
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(&v46);
    v21 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v44 )
      ExFreePoolWithTag(v44, 0);
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x180010b50  push    rbp
0x180010b52  push    rbx
0x180010b53  push    rsi
0x180010b54  push    rdi
0x180010b55  push    r12
0x180010b57  push    r13
0x180010b59  push    r14
0x180010b5b  push    r15
0x180010b5d  lea     rbp, [rsp-1Fh]
0x180010b62  sub     rsp, 0B8h
0x180010b69  xor     r13d, r13d
0x180010b6c  mov     r15, r8
0x180010b6f  mov     esi, edx
0x180010b71  mov     rbx, rcx
0x180010b74  test    rcx, rcx
0x180010b77  jz      loc_180010D03
0x180010b7d  cmp     edx, 16h
0x180010b80  jb      loc_180010D03
0x180010b86  lea     r12, [rcx+16h]
0x180010b8a  mov     [rbp+57h+var_90], r13
0x180010b8e  lea     r14d, [rdx-16h]
0x180010b92  mov     [rbp+57h+var_88], r13
0x180010b96  xor     edx, edx; SourceString
0x180010b98  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180010b9c  call    cs:__imp_RtlInitUnicodeString
0x180010ba3  nop     dword ptr [rax+rax+00h]
0x180010ba8  xor     edx, edx; SourceString
0x180010baa  mov     [rbp+57h+var_B0], r13
0x180010bae  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x180010bb2  mov     [rbp+57h+P], r13
0x180010bb6  call    cs:__imp_RtlInitUnicodeString
0x180010bbd  nop     dword ptr [rax+rax+00h]
0x180010bc2  movzx   r8d, word ptr [rbx+6]
0x180010bc7  lea     rax, [rbp+57h+var_68]
0x180010bcb  movzx   ecx, word ptr [rbx+4]
0x180010bcf  xorps   xmm0, xmm0
0x180010bd2  mov     [rbp+57h+var_50], rax
0x180010bd6  lea     rax, [rbp+57h+var_68]
0x180010bda  mov     [rbp+57h+var_58], rax
0x180010bde  mov     [rbp+57h+var_70], r13d
0x180010be2  movdqu  [rbp+57h+var_68], xmm0
0x180010be7  test    r8w, r8w
0x180010beb  jnz     short loc_180010BF7
0x180010bed  test    cx, cx
0x180010bf0  jnz     short loc_180010BF7
0x180010bf2  mov     edx, r13d
0x180010bf5  jmp     short loc_180010C11
0x180010bf7  cmp     ecx, r14d
0x180010bfa  ja      loc_18001105D
0x180010c00  lea     eax, [rcx+r8]
0x180010c04  cmp     eax, r14d
0x180010c07  ja      loc_18001105D
0x180010c0d  lea     rdx, [r12+rcx]
0x180010c11  shr     r8, 1
0x180010c14  lea     rcx, [rbp+57h+var_90]
0x180010c18  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180010c1d  mov     edi, eax
0x180010c1f  test    eax, eax
0x180010c21  js      loc_180011062
0x180010c27  movzx   r8d, word ptr [rbx+0Ah]
0x180010c2c  movzx   ecx, word ptr [rbx+8]
0x180010c30  test    r8w, r8w
0x180010c34  jnz     short loc_180010C40
0x180010c36  test    cx, cx
0x180010c39  jnz     short loc_180010C40
0x180010c3b  mov     rdx, r13
0x180010c3e  jmp     short loc_180010C5A
0x180010c40  cmp     ecx, r14d
0x180010c43  ja      loc_18001105D
0x180010c49  lea     eax, [rcx+r8]
0x180010c4d  cmp     eax, r14d
0x180010c50  ja      loc_18001105D
0x180010c56  lea     rdx, [r12+rcx]
0x180010c5a  shr     r8, 1
0x180010c5d  lea     rcx, [rbp+57h+var_B0]
0x180010c61  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180010c66  mov     edi, eax
0x180010c68  test    eax, eax
0x180010c6a  js      loc_180011062
0x180010c70  mov     r12d, [rbx+0Ch]
0x180010c74  mov     r14d, r12d
0x180010c77  mov     eax, [rbx+10h]
0x180010c7a  shr     r14d, 1
0x180010c7d  add     eax, 16h
0x180010c80  and     r14b, 1
0x180010c84  cmp     eax, esi
0x180010c86  jbe     loc_180010D1D
0x180010c8c  lea     rcx, [rbp+57h+var_70]
0x180010c90  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180010c95  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x180010c99  test    rdi, rdi
0x180010c9c  jz      short loc_180010CD5
0x180010c9e  or      ebx, 0FFFFFFFFh
0x180010ca1  mov     eax, ebx
0x180010ca3  lock xadd [rdi+8], eax
0x180010ca8  add     eax, ebx
0x180010caa  jnz     short loc_180010CD5
0x180010cac  mov     rax, [rdi]
0x180010caf  mov     rcx, rdi
0x180010cb2  mov     rax, [rax+8]
0x180010cb6  call    _guard_dispatch_icall
0x180010cbb  mov     eax, ebx
0x180010cbd  lock xadd [rdi+0Ch], eax
0x180010cc2  add     eax, ebx
0x180010cc4  jnz     short loc_180010CD5
0x180010cc6  mov     rax, [rdi]
0x180010cc9  mov     rcx, rdi
0x180010ccc  mov     rax, [rax+10h]
0x180010cd0  call    _guard_dispatch_icall
0x180010cd5  mov     rcx, [rbp+57h+P]; P
0x180010cd9  test    rcx, rcx
0x180010cdc  jz      short loc_180010CEC
0x180010cde  xor     edx, edx; Tag
0x180010ce0  call    cs:__imp_ExFreePoolWithTag
0x180010ce7  nop     dword ptr [rax+rax+00h]
0x180010cec  mov     rcx, [rbp+57h+var_88]; P
0x180010cf0  test    rcx, rcx
0x180010cf3  jz      short loc_180010D03
0x180010cf5  xor     edx, edx; Tag
0x180010cf7  call    cs:__imp_ExFreePoolWithTag
0x180010cfe  nop     dword ptr [rax+rax+00h]
0x180010d03  mov     eax, 0C0000206h
0x180010d08  add     rsp, 0B8h
0x180010d0f  pop     r15
0x180010d11  pop     r14
0x180010d13  pop     r13
0x180010d15  pop     r12
0x180010d17  pop     rdi
0x180010d18  pop     rsi
0x180010d19  pop     rbx
0x180010d1a  pop     rbp
0x180010d1b  retn
0x180010d1d  movzx   r8d, word ptr [rbx+14h]
0x180010d22  lea     r9, [rbp+57h+var_70]
0x180010d26  sub     esi, eax
0x180010d28  mov     ecx, eax
0x180010d2a  add     rcx, rbx
0x180010d2d  mov     edx, esi
0x180010d2f  call    ??$unpack_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$unpack_vfs_mappings@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKGAEAV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(uchar const *,ulong,ushort,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180010d34  mov     esi, eax
0x180010d36  test    eax, eax
0x180010d38  jns     short loc_180010DB8
0x180010d3a  lea     rcx, [rbp+57h+var_70]
0x180010d3e  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180010d43  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x180010d47  test    rdi, rdi
0x180010d4a  jz      short loc_180010D83
0x180010d4c  or      ebx, 0FFFFFFFFh
0x180010d4f  mov     ecx, ebx
0x180010d51  lock xadd [rdi+8], ecx
0x180010d56  add     ecx, ebx
0x180010d58  jnz     short loc_180010D83
0x180010d5a  mov     rax, [rdi]
0x180010d5d  mov     rcx, rdi
0x180010d60  mov     rax, [rax+8]
0x180010d64  call    _guard_dispatch_icall
0x180010d69  mov     eax, ebx
0x180010d6b  lock xadd [rdi+0Ch], eax
0x180010d70  add     eax, ebx
0x180010d72  jnz     short loc_180010D83
0x180010d74  mov     rax, [rdi]
0x180010d77  mov     rcx, rdi
0x180010d7a  mov     rax, [rax+10h]
0x180010d7e  call    _guard_dispatch_icall
0x180010d83  mov     rcx, [rbp+57h+P]; P
0x180010d87  test    rcx, rcx
0x180010d8a  jz      short loc_180010D9A
0x180010d8c  xor     edx, edx; Tag
0x180010d8e  call    cs:__imp_ExFreePoolWithTag
0x180010d95  nop     dword ptr [rax+rax+00h]
0x180010d9a  mov     rcx, [rbp+57h+var_88]; P
0x180010d9e  test    rcx, rcx
0x180010da1  jz      short loc_180010DB1
0x180010da3  xor     edx, edx; Tag
0x180010da5  call    cs:__imp_ExFreePoolWithTag
0x180010dac  nop     dword ptr [rax+rax+00h]
0x180010db1  mov     eax, esi
0x180010db3  jmp     loc_180010D08
0x180010db8  cmp     dword ptr [rbp+57h+var_90], 2
0x180010dbc  jbe     loc_180010FDC
0x180010dc2  cmp     dword ptr [rbp+57h+var_B0], 2
0x180010dc6  jbe     loc_180010FDC
0x180010dcc  mov     edi, 88h
0x180010dd1  mov     r8d, 674D6556h
0x180010dd7  mov     edx, edi
0x180010dd9  lea     ecx, [rdi+78h]
0x180010ddc  call    cs:__imp_ExAllocatePool2
0x180010de3  nop     dword ptr [rax+rax+00h]
0x180010de8  mov     rbx, rax
0x180010deb  test    rax, rax
0x180010dee  jz      short loc_180010E07
0x180010df0  mov     r8d, edi; Size
0x180010df3  xor     edx, edx; Val
0x180010df5  mov     rcx, rax; void *
0x180010df8  call    memset
0x180010dfd  mov     rcx, rbx
0x180010e00  call    ??0?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x180010e05  jmp     short loc_180010E0A
0x180010e07  mov     rax, r13
0x180010e0a  mov     rdx, rax
0x180010e0d  lea     rcx, [rbp+57h+var_C0]
0x180010e11  call    ??$?0V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x180010e16  mov     rcx, [r15]
0x180010e19  or      ebx, 0FFFFFFFFh
0x180010e1c  mov     rdx, [rax]
0x180010e1f  mov     [rax], rcx
0x180010e22  mov     [r15], rdx
0x180010e25  mov     rcx, [rax+8]
0x180010e29  mov     rdx, [r15+8]
0x180010e2d  mov     [r15+8], rcx
0x180010e31  mov     [rax+8], rdx
0x180010e35  mov     rdi, [rbp+57h+var_B8]
0x180010e39  test    rdi, rdi
0x180010e3c  jz      short loc_180010E72
0x180010e3e  mov     eax, ebx
0x180010e40  lock xadd [rdi+8], eax
0x180010e45  add     eax, ebx
0x180010e47  jnz     short loc_180010E72
0x180010e49  mov     rax, [rdi]
0x180010e4c  mov     rcx, rdi
0x180010e4f  mov     rax, [rax+8]
0x180010e53  call    _guard_dispatch_icall
0x180010e58  mov     eax, ebx
0x180010e5a  lock xadd [rdi+0Ch], eax
0x180010e5f  add     eax, ebx
0x180010e61  jnz     short loc_180010E72
0x180010e63  mov     rax, [rdi]
0x180010e66  mov     rcx, rdi
0x180010e69  mov     rax, [rax+10h]
0x180010e6d  call    _guard_dispatch_icall
0x180010e72  cmp     [r15], r13
0x180010e75  jz      loc_180010F5E
0x180010e7b  mov     rax, [r15+8]
0x180010e7f  test    rax, rax
0x180010e82  jz      loc_180010F5E
0x180010e88  mov     eax, [rax+8]
0x180010e8b  test    eax, eax
0x180010e8d  jz      loc_180010F5E
0x180010e93  mov     eax, dword ptr [rbp+57h+var_B0]
0x180010e96  and     r12d, 1
0x180010e9a  mov     rcx, [r15]
0x180010e9d  mov     edx, 0FFFFh
0x180010ea2  shr     eax, 1
0x180010ea4  cmp     eax, edx
0x180010ea6  ja      short loc_180010EB1
0x180010ea8  mov     r8, [rbp+57h+P]
0x180010eac  test    ax, ax
0x180010eaf  jnz     short loc_180010EB4
0x180010eb1  mov     r8, r13
0x180010eb4  mov     eax, dword ptr [rbp+57h+var_90]
0x180010eb7  shr     eax, 1
0x180010eb9  cmp     eax, edx
0x180010ebb  ja      short loc_180010EC6
0x180010ebd  mov     rdx, [rbp+57h+var_88]
0x180010ec1  test    ax, ax
0x180010ec4  jnz     short loc_180010EC9
0x180010ec6  mov     rdx, r13
0x180010ec9  lea     rax, [rbp+57h+var_70]
0x180010ecd  mov     r9b, r12b
0x180010ed0  mov     [rsp+0F0h+var_C8], rax
0x180010ed5  mov     [rsp+0F0h+var_D0], r14b
0x180010eda  call    ?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_W0_N1AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,wchar_t const *,bool,bool,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x180010edf  lea     rcx, [rbp+57h+var_70]
0x180010ee3  test    al, al
0x180010ee5  jz      short loc_180010F62
0x180010ee7  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180010eec  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x180010ef0  test    rdi, rdi
0x180010ef3  jz      short loc_180010F29
0x180010ef5  mov     eax, ebx
0x180010ef7  lock xadd [rdi+8], eax
0x180010efc  add     eax, ebx
0x180010efe  jnz     short loc_180010F29
0x180010f00  mov     rax, [rdi]
0x180010f03  mov     rcx, rdi
0x180010f06  mov     rax, [rax+8]
0x180010f0a  call    _guard_dispatch_icall
0x180010f0f  mov     eax, ebx
0x180010f11  lock xadd [rdi+0Ch], eax
0x180010f16  add     eax, ebx
0x180010f18  jnz     short loc_180010F29
0x180010f1a  mov     rax, [rdi]
0x180010f1d  mov     rcx, rdi
0x180010f20  mov     rax, [rax+10h]
0x180010f24  call    _guard_dispatch_icall
0x180010f29  mov     rcx, [rbp+57h+P]; P
0x180010f2d  test    rcx, rcx
0x180010f30  jz      short loc_180010F40
0x180010f32  xor     edx, edx; Tag
0x180010f34  call    cs:__imp_ExFreePoolWithTag
0x180010f3b  nop     dword ptr [rax+rax+00h]
0x180010f40  mov     rcx, [rbp+57h+var_88]; P
0x180010f44  test    rcx, rcx
0x180010f47  jz      short loc_180010F57
0x180010f49  xor     edx, edx; Tag
0x180010f4b  call    cs:__imp_ExFreePoolWithTag
0x180010f52  nop     dword ptr [rax+rax+00h]
0x180010f57  xor     eax, eax
0x180010f59  jmp     loc_180010D08
0x180010f5e  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
