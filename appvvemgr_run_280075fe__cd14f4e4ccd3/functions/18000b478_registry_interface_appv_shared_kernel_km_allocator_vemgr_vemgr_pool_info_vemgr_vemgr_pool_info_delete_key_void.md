# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)

- ea: `0x18000b478`
- end: `0x18000ba50`
- name: `?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z`
- size: `1496`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000fa58`
- `0x180013e14`
- `0x1800141d0`
- `0x180014338`
- `0x180014470`
- `0x180014d1c`
- `0x180019b1c`
- `0x180019cfc`

## callees

- `0x180001448`
- `0x180005178`
- `0x18000a958`
- `0x18000a9e4`
- `0x18000b478`
- `0x18000ba58`
- `0x18000c290`
- `0x18000c5f4`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000b4cb`
- `ntoskrnl!ExAllocatePool2` at `0x18000b615`
- `ntoskrnl!ExAllocatePool2` at `0x18000b72b`
- `ntoskrnl!ExAllocatePool2` at `0x18000b4cb`
- `ntoskrnl!ExAllocatePool2` at `0x18000b615`
- `ntoskrnl!ExAllocatePool2` at `0x18000b72b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b4ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b63a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b4ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b63a`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
        void *a1,
        __int64 a2)
{
  void *v3; // r15
  __int64 Pool2; // rax
  __int64 v5; // rbx
  volatile signed __int32 *v6; // rsi
  __int64 v7; // r8
  NTSTATUS v8; // r12d
  volatile signed __int32 *v9; // r14
  __int128 *v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int128 *i; // rbx
  __int64 v14; // rax
  __int64 v15; // r15
  __int128 v16; // kr00_16
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int128 *v23; // rcx
  __int128 *v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  int v28; // [rsp+20h] [rbp-49h] BYREF
  __int128 v29; // [rsp+28h] [rbp-41h] BYREF
  __int128 *v30; // [rsp+38h] [rbp-31h]
  __int128 *v31; // [rsp+40h] [rbp-29h]
  int v32; // [rsp+48h] [rbp-21h] BYREF
  __int128 v33; // [rsp+50h] [rbp-19h] BYREF
  __int128 *v34; // [rsp+60h] [rbp-9h]
  __int128 *v35; // [rsp+68h] [rbp-1h]
  __int64 v36; // [rsp+70h] [rbp+7h] BYREF
  volatile signed __int32 *v37; // [rsp+78h] [rbp+Fh]
  __int128 v38; // [rsp+80h] [rbp+17h] BYREF
  __int128 *v40; // [rsp+E8h] [rbp+7Fh] BYREF

  v31 = &v29;
  v3 = a1;
  v28 = 0;
  v30 = &v29;
  v29 = 0;
  Pool2 = ExAllocatePool2(64, 32, 1715758931);
  v5 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v5 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    &v36,
    v5);
  v6 = v37;
  if ( !v36 )
    goto LABEL_103;
  if ( !v37 )
  {
LABEL_100:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v28);
    return 3221225626LL;
  }
  if ( !*((_DWORD *)v37 + 2) )
  {
LABEL_103:
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    goto LABEL_100;
  }
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a2 + 2 * v7) );
  }
  else
  {
    v7 = 0;
  }
  v8 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
         v36,
         a2,
         v7);
  if ( v8 < 0 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) != 1 )
      goto LABEL_82;
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    goto LABEL_80;
  }
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
    &v28,
    &v36);
  while ( 1 )
  {
    if ( !v28 )
      goto LABEL_77;
    v9 = (volatile signed __int32 *)*((_QWORD *)v31 + 1);
    v10 = *(__int128 **)v31;
    v40 = *(__int128 **)v31;
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
    v32 = 0;
    v35 = &v33;
    v34 = &v33;
    v33 = 0;
    v11 = *(_DWORD *)v10 >> 1;
    if ( v11 <= 0xFFFF && (_WORD)v11 )
      v12 = *((_QWORD *)v10 + 1);
    else
      v12 = 0;
    if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
                v3,
                v12,
                &v32) >= 0
      && v32 )
    {
      break;
    }
    v25 = *(_DWORD *)v10 >> 1;
    if ( v25 <= 0xFFFF && (_WORD)v25 )
      v26 = *((_QWORD *)v10 + 1);
    else
      v26 = 0;
    v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_subkey_internal(
           v3,
           v26);
    if ( v8 < 0 )
    {
LABEL_73:
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v32);
      if ( v9 )
      {
        if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
          if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
LABEL_77:
      if ( !v6 || _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) != 1 )
        goto LABEL_82;
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
LABEL_80:
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      goto LABEL_82;
    }
    v40 = v31;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
      &v28,
      &v36,
      &v40);
LABEL_65:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v32);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  for ( i = v35; ; i = (__int128 *)*((_QWORD *)i + 3) )
  {
    if ( i == &v33 )
    {
      v3 = a1;
      goto LABEL_65;
    }
    v14 = ExAllocatePool2(64, 32, 1715758931);
    v15 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = 0;
      *(_QWORD *)(v14 + 8) = 0;
      RtlInitUnicodeString((PUNICODE_STRING)(v14 + 16), 0);
    }
    else
    {
      v15 = 0;
    }
    kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
      &v38,
      v15);
    v16 = v38;
    if ( !(_QWORD)v38 )
      break;
    if ( !*((_QWORD *)&v38 + 1) )
      goto LABEL_87;
    if ( !*(_DWORD *)(*((_QWORD *)&v38 + 1) + 8LL) )
      break;
    v17 = *(_DWORD *)v40 >> 1;
    if ( v17 <= 0xFFFF && (_WORD)v17 )
    {
      v18 = *((_QWORD *)v40 + 1);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(v18 + 2 * v19) );
        goto LABEL_40;
      }
    }
    else
    {
      v18 = 0;
    }
    v19 = 0;
LABEL_40:
    v8 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
           v38,
           v18,
           v19);
    if ( v8 < 0
      || *(_DWORD *)v16 > 2u
      && (v8 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                 v16,
                 L"\\"),
          v8 < 0)
      || ((v20 = **(_DWORD **)i >> 1, v20 > 0xFFFF) || !(_WORD)v20 ? (v21 = 0) : (v21 = *(_QWORD *)(*(_QWORD *)i + 8LL)),
          v8 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                 v16,
                 v21),
          v8 < 0) )
    {
      if ( *((_QWORD *)&v16 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 8LL))(*((_QWORD *)&v16 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 12LL), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 16LL))(*((_QWORD *)&v16 + 1));
        }
      }
      goto LABEL_73;
    }
    v22 = ExAllocatePool2(256, 32, 1733125462);
    v23 = (__int128 *)v22;
    if ( v22 )
    {
      *(_OWORD *)v22 = v38;
      if ( *((_QWORD *)&v16 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL));
      *(_QWORD *)(v22 + 24) = v22;
      *(_QWORD *)(v22 + 16) = v22;
      ++v28;
      v24 = v31;
      *((_QWORD *)v23 + 3) = v31;
      *((_QWORD *)v23 + 2) = &v29;
      *((_QWORD *)v24 + 2) = v23;
      v31 = v23;
    }
    if ( *((_QWORD *)&v16 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 8LL))(*((_QWORD *)&v16 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 16LL))(*((_QWORD *)&v16 + 1));
      }
    }
  }
  if ( *((_QWORD *)&v38 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 8LL))(*((_QWORD *)&v16 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 16LL))(*((_QWORD *)&v16 + 1));
    }
  }
LABEL_87:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v32);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v8 = -1073741670;
LABEL_82:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b478  mov     [rsp-8+arg_8], rbx
0x18000b47d  mov     [rsp-8+arg_0], rcx
0x18000b482  push    rbp
0x18000b483  push    rsi
0x18000b484  push    rdi
0x18000b485  push    r12
0x18000b487  push    r13
0x18000b489  push    r14
0x18000b48b  push    r15
0x18000b48d  lea     rbp, [rsp-27h]
0x18000b492  sub     rsp, 90h
0x18000b499  xor     r13d, r13d
0x18000b49c  lea     rax, [rbp+57h+var_98]
0x18000b4a0  mov     r14, rdx
0x18000b4a3  mov     [rbp+57h+var_80], rax
0x18000b4a7  mov     r15, rcx
0x18000b4aa  mov     [rbp+57h+var_A0], r13d
0x18000b4ae  xorps   xmm0, xmm0
0x18000b4b1  lea     rax, [rbp+57h+var_98]
0x18000b4b5  lea     edx, [r13+20h]
0x18000b4b9  mov     [rbp+57h+var_88], rax
0x18000b4bd  lea     ecx, [rdx+20h]
0x18000b4c0  mov     r8d, 66446753h
0x18000b4c6  movdqu  [rbp+57h+var_98], xmm0
0x18000b4cb  call    cs:__imp_ExAllocatePool2
0x18000b4d2  nop     dword ptr [rax+rax+00h]
0x18000b4d7  mov     rbx, rax
0x18000b4da  test    rax, rax
0x18000b4dd  jz      short loc_18000B4FA
0x18000b4df  lea     rcx, [rax+10h]; DestinationString
0x18000b4e3  mov     [rax], r13
0x18000b4e6  xor     edx, edx; SourceString
0x18000b4e8  mov     [rax+8], r13
0x18000b4ec  call    cs:__imp_RtlInitUnicodeString
0x18000b4f3  nop     dword ptr [rax+rax+00h]
0x18000b4f8  jmp     short loc_18000B4FD
0x18000b4fa  mov     rbx, r13
0x18000b4fd  mov     rdx, rbx
0x18000b500  lea     rcx, [rbp+57h+var_50]
0x18000b504  call    ??$?0V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAA@PEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000b509  mov     rcx, [rbp+57h+var_50]
0x18000b50d  mov     rsi, [rbp+57h+var_48]
0x18000b511  test    rcx, rcx
0x18000b514  jz      loc_18000B9E9
0x18000b51a  test    rsi, rsi
0x18000b51d  jz      loc_18000BA26
0x18000b523  mov     eax, [rsi+8]
0x18000b526  test    eax, eax
0x18000b528  jz      loc_18000B9E9
0x18000b52e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b532  test    r14, r14
0x18000b535  jnz     short loc_18000B53C
0x18000b537  mov     r8, r13
0x18000b53a  jmp     short loc_18000B549
0x18000b53c  mov     r8, rdi
0x18000b53f  inc     r8
0x18000b542  cmp     [r14+r8*2], r13w
0x18000b547  jnz     short loc_18000B53F
0x18000b549  mov     rdx, r14
0x18000b54c  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000b551  mov     r12d, eax
0x18000b554  test    eax, eax
0x18000b556  jns     short loc_18000B573
0x18000b558  mov     ecx, edi
0x18000b55a  lock xadd [rsi+8], ecx
0x18000b55f  add     ecx, edi
0x18000b561  jnz     loc_18000B915
0x18000b567  mov     rdx, [rsi]
0x18000b56a  mov     rax, [rdx+8]
0x18000b56e  jmp     loc_18000B8F3
0x18000b573  lea     rdx, [rbp+57h+var_50]
0x18000b577  lea     rcx, [rbp+57h+var_A0]
0x18000b57b  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000b580  cmp     [rbp+57h+var_A0], r13d
0x18000b584  jz      loc_18000B8DC
0x18000b58a  mov     rax, [rbp+57h+var_80]
0x18000b58e  mov     r14, [rax+8]
0x18000b592  mov     rbx, [rax]
0x18000b595  mov     [rbp+57h+arg_18], rbx
0x18000b599  test    r14, r14
0x18000b59c  jz      short loc_18000B5A3
0x18000b59e  lock inc dword ptr [r14+8]
0x18000b5a3  lea     rax, [rbp+57h+var_70]
0x18000b5a7  mov     [rbp+57h+var_78], r13d
0x18000b5ab  mov     [rbp+57h+var_58], rax
0x18000b5af  xorps   xmm0, xmm0
0x18000b5b2  lea     rax, [rbp+57h+var_70]
0x18000b5b6  mov     [rbp+57h+var_60], rax
0x18000b5ba  movdqu  [rbp+57h+var_70], xmm0
0x18000b5bf  mov     eax, [rbx]
0x18000b5c1  shr     eax, 1
0x18000b5c3  cmp     eax, 0FFFFh
0x18000b5c8  ja      short loc_18000B5D5
0x18000b5ca  test    ax, ax
0x18000b5cd  jz      short loc_18000B5D5
0x18000b5cf  mov     rdx, [rbx+8]
0x18000b5d3  jmp     short loc_18000B5D8
0x18000b5d5  mov     rdx, r13
0x18000b5d8  lea     r8, [rbp+57h+var_78]
0x18000b5dc  mov     rcx, r15
0x18000b5df  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000b5e4  test    eax, eax
0x18000b5e6  js      loc_18000B7BD
0x18000b5ec  cmp     [rbp+57h+var_78], r13d
0x18000b5f0  jz      loc_18000B7BD
0x18000b5f6  mov     rbx, [rbp+57h+var_58]
0x18000b5fa  lea     rax, [rbp+57h+var_70]
0x18000b5fe  cmp     rbx, rax
0x18000b601  jz      loc_18000B804
0x18000b607  mov     edx, 20h ; ' '
0x18000b60c  mov     r8d, 66446753h
0x18000b612  lea     ecx, [rdx+20h]
0x18000b615  call    cs:__imp_ExAllocatePool2
0x18000b61c  nop     dword ptr [rax+rax+00h]
0x18000b621  mov     r15, rax
0x18000b624  test    rax, rax
0x18000b627  jz      short loc_18000B648
0x18000b629  lea     rcx, [rax+10h]; DestinationString
0x18000b62d  mov     qword ptr [rax], 0
0x18000b634  xor     edx, edx; SourceString
0x18000b636  mov     [rax+8], r13
0x18000b63a  call    cs:__imp_RtlInitUnicodeString
0x18000b641  nop     dword ptr [rax+rax+00h]
0x18000b646  jmp     short loc_18000B64B
0x18000b648  mov     r15, r13
0x18000b64b  mov     rdx, r15
0x18000b64e  lea     rcx, [rbp+57h+var_40]
0x18000b652  call    ??$?0V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAA@PEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000b657  mov     r13, qword ptr [rbp+57h+var_40]
0x18000b65b  xor     r12d, r12d
0x18000b65e  mov     r15, qword ptr [rbp+57h+var_40+8]
0x18000b662  test    r13, r13
0x18000b665  jz      loc_18000B926
0x18000b66b  test    r15, r15
0x18000b66e  jz      loc_18000B961
0x18000b674  mov     eax, [r15+8]
0x18000b678  test    eax, eax
0x18000b67a  jz      loc_18000B926
0x18000b680  mov     rcx, [rbp+57h+arg_18]
0x18000b684  mov     eax, [rcx]
0x18000b686  shr     eax, 1
0x18000b688  cmp     eax, 0FFFFh
0x18000b68d  ja      short loc_18000B6AC
0x18000b68f  test    ax, ax
0x18000b692  jz      short loc_18000B6AC
0x18000b694  mov     rdx, [rcx+8]
0x18000b698  test    rdx, rdx
0x18000b69b  jz      short loc_18000B6AF
0x18000b69d  mov     r8, rdi
0x18000b6a0  inc     r8
0x18000b6a3  cmp     [rdx+r8*2], r12w
0x18000b6a8  jnz     short loc_18000B6A0
0x18000b6aa  jmp     short loc_18000B6B2
0x18000b6ac  mov     rdx, r12
0x18000b6af  mov     r8, r12
0x18000b6b2  mov     rcx, r13
0x18000b6b5  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000b6ba  xor     ecx, ecx
0x18000b6bc  mov     r12d, eax
0x18000b6bf  test    eax, eax
0x18000b6c1  js      loc_18000B85D
0x18000b6c7  cmp     dword ptr [r13+0], 2
0x18000b6cc  jbe     short loc_18000B6EA
0x18000b6ce  lea     rdx, asc_18002108C; "\\"
0x18000b6d5  mov     rcx, r13
0x18000b6d8  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18000b6dd  xor     ecx, ecx
0x18000b6df  mov     r12d, eax
0x18000b6e2  test    eax, eax
0x18000b6e4  js      loc_18000B85D
0x18000b6ea  mov     rdx, [rbx]
0x18000b6ed  mov     eax, [rdx]
0x18000b6ef  shr     eax, 1
0x18000b6f1  cmp     eax, 0FFFFh
0x18000b6f6  ja      short loc_18000B703
0x18000b6f8  test    ax, ax
0x18000b6fb  jz      short loc_18000B703
0x18000b6fd  mov     rdx, [rdx+8]
0x18000b701  jmp     short loc_18000B706
0x18000b703  mov     rdx, rcx
0x18000b706  mov     rcx, r13
0x18000b709  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18000b70e  xor     r13d, r13d
0x18000b711  mov     r12d, eax
0x18000b714  test    eax, eax
0x18000b716  js      loc_18000B85D
0x18000b71c  lea     edx, [r13+20h]
0x18000b720  mov     ecx, 100h
0x18000b725  mov     r8d, 674D6556h
0x18000b72b  call    cs:__imp_ExAllocatePool2
0x18000b732  nop     dword ptr [rax+rax+00h]
0x18000b737  mov     rcx, rax
0x18000b73a  test    rax, rax
0x18000b73d  jz      short loc_18000B779
0x18000b73f  movups  xmm0, [rbp+57h+var_40]
0x18000b743  movdqu  xmmword ptr [rax], xmm0
0x18000b747  test    r15, r15
0x18000b74a  jz      short loc_18000B751
0x18000b74c  lock inc dword ptr [r15+8]
0x18000b751  mov     [rax+18h], rcx
0x18000b755  mov     [rax+10h], rcx
0x18000b759  inc     [rbp+57h+var_A0]
0x18000b75c  test    rcx, rcx
0x18000b75f  jz      short loc_18000B779
0x18000b761  mov     rax, [rbp+57h+var_80]
0x18000b765  lea     rdx, [rbp+57h+var_98]
0x18000b769  mov     [rcx+18h], rax
0x18000b76d  mov     [rcx+10h], rdx
0x18000b771  mov     [rax+10h], rcx
0x18000b775  mov     [rbp+57h+var_80], rcx
0x18000b779  test    r15, r15
0x18000b77c  jz      short loc_18000B7B4
0x18000b77e  mov     eax, edi
0x18000b780  lock xadd [r15+8], eax
0x18000b786  add     eax, edi
0x18000b788  jnz     short loc_18000B7B4
0x18000b78a  mov     rax, [r15]
0x18000b78d  mov     rcx, r15
0x18000b790  mov     rax, [rax+8]
0x18000b794  call    _guard_dispatch_icall
0x18000b799  mov     eax, edi
0x18000b79b  lock xadd [r15+0Ch], eax
0x18000b7a1  add     eax, edi
0x18000b7a3  jnz     short loc_18000B7B4
0x18000b7a5  mov     rax, [r15]
0x18000b7a8  mov     rcx, r15
0x18000b7ab  mov     rax, [rax+10h]
0x18000b7af  call    _guard_dispatch_icall
0x18000b7b4  mov     rbx, [rbx+18h]
0x18000b7b8  jmp     loc_18000B5FA
0x18000b7bd  mov     eax, [rbx]
0x18000b7bf  shr     eax, 1
0x18000b7c1  cmp     eax, 0FFFFh
0x18000b7c6  ja      short loc_18000B7D3
0x18000b7c8  test    ax, ax
0x18000b7cb  jz      short loc_18000B7D3
0x18000b7cd  mov     rdx, [rbx+8]
0x18000b7d1  jmp     short loc_18000B7D6
0x18000b7d3  mov     rdx, r13
0x18000b7d6  mov     rcx, r15
0x18000b7d9  call    ?delete_subkey_internal@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_W@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_subkey_internal(void *,wchar_t const *)
0x18000b7de  mov     r12d, eax
0x18000b7e1  test    eax, eax
0x18000b7e3  js      loc_18000B898
0x18000b7e9  mov     rax, [rbp+57h+var_80]
0x18000b7ed  lea     r8, [rbp+57h+arg_18]
0x18000b7f1  lea     rdx, [rbp+57h+var_50]
0x18000b7f5  mov     [rbp+57h+arg_18], rax
0x18000b7f9  lea     rcx, [rbp+57h+var_A0]
0x18000b7fd  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18000b802  jmp     short loc_18000B808
0x18000b804  mov     r15, [rbp+57h+arg_0]
0x18000b808  lea     rcx, [rbp+57h+var_78]
0x18000b80c  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000b811  test    r14, r14
0x18000b814  jz      loc_18000B580
0x18000b81a  mov     eax, edi
0x18000b81c  lock xadd [r14+8], eax
0x18000b822  add     eax, edi
0x18000b824  jnz     loc_18000B580
0x18000b82a  mov     rax, [r14]
0x18000b82d  mov     rcx, r14
0x18000b830  mov     rax, [rax+8]
0x18000b834  call    _guard_dispatch_icall
0x18000b839  mov     eax, edi
0x18000b83b  lock xadd [r14+0Ch], eax
0x18000b841  add     eax, edi
0x18000b843  jnz     loc_18000B580
0x18000b849  mov     rax, [r14]
0x18000b84c  mov     rcx, r14
0x18000b84f  mov     rax, [rax+10h]
0x18000b853  call    _guard_dispatch_icall
0x18000b858  jmp     loc_18000B580
0x18000b85d  test    r15, r15
0x18000b860  jz      short loc_18000B898
0x18000b862  mov     eax, edi
0x18000b864  lock xadd [r15+8], eax
0x18000b86a  add     eax, edi
0x18000b86c  jnz     short loc_18000B898
0x18000b86e  mov     rax, [r15]
0x18000b871  mov     rcx, r15
0x18000b874  mov     rax, [rax+8]
0x18000b878  call    _guard_dispatch_icall
0x18000b87d  mov     eax, edi
0x18000b87f  lock xadd [r15+0Ch], eax
0x18000b885  add     eax, edi
0x18000b887  jnz     short loc_18000B898
0x18000b889  mov     rax, [r15]
0x18000b88c  mov     rcx, r15
0x18000b88f  mov     rax, [rax+10h]
0x18000b893  call    _guard_dispatch_icall
0x18000b898  lea     rcx, [rbp+57h+var_78]
0x18000b89c  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000b8a1  test    r14, r14
0x18000b8a4  jz      short loc_18000B8DC
0x18000b8a6  mov     eax, edi
0x18000b8a8  lock xadd [r14+8], eax
0x18000b8ae  add     eax, edi
0x18000b8b0  jnz     short loc_18000B8DC
0x18000b8b2  mov     rax, [r14]
  ... truncated ...
```
