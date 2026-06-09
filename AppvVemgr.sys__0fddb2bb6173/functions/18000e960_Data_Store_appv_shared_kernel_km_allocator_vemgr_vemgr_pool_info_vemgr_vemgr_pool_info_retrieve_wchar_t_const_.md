# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x18000e960`
- end: `0x18000ef6c`
- name: `?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `1548`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007d54`
- `0x1800105f4`

## callees

- `0x180001398`
- `0x180003f50`
- `0x180004764`
- `0x180005430`
- `0x18000a9e4`
- `0x18000ab2c`
- `0x18000ce10`
- `0x18000ce9c`
- `0x18000e23c`
- `0x18000e354`
- `0x18000e960`
- `0x18000f300`
- `0x18000f718`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000e9ae`
- `ntoskrnl!ExAllocatePool2` at `0x18000ea84`
- `ntoskrnl!ExAllocatePool2` at `0x18000e9ae`
- `ntoskrnl!ExAllocatePool2` at `0x18000ea84`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ed22`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000edda`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ed22`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000edda`
- `ntoskrnl!ZwClose` at `0x18000eb72`
- `ntoskrnl!ZwClose` at `0x18000ebd2`
- `ntoskrnl!ZwClose` at `0x18000ebe6`
- `ntoskrnl!ZwClose` at `0x18000ec7a`
- `ntoskrnl!ZwClose` at `0x18000ec8e`
- `ntoskrnl!ZwClose` at `0x18000eca2`
- `ntoskrnl!ZwClose` at `0x18000ed36`
- `ntoskrnl!ZwClose` at `0x18000ed4a`
- `ntoskrnl!ZwClose` at `0x18000ed5e`
- `ntoskrnl!ZwClose` at `0x18000edee`
- `ntoskrnl!ZwClose` at `0x18000ee02`
- `ntoskrnl!ZwClose` at `0x18000ee16`
- `ntoskrnl!ZwClose` at `0x18000eb72`
- `ntoskrnl!ZwClose` at `0x18000ebd2`
- `ntoskrnl!ZwClose` at `0x18000ebe6`
- `ntoskrnl!ZwClose` at `0x18000ec7a`
- `ntoskrnl!ZwClose` at `0x18000ec8e`
- `ntoskrnl!ZwClose` at `0x18000eca2`
- `ntoskrnl!ZwClose` at `0x18000ed36`
- `ntoskrnl!ZwClose` at `0x18000ed4a`
- `ntoskrnl!ZwClose` at `0x18000ed5e`
- `ntoskrnl!ZwClose` at `0x18000edee`
- `ntoskrnl!ZwClose` at `0x18000ee02`
- `ntoskrnl!ZwClose` at `0x18000ee16`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000eaa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000eaa5`

## string_xrefs

- `0x18000ebb4`: `UserConfigEx`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
        _WORD *a1,
        _WORD *a2,
        _WORD *a3,
        _QWORD *a4)
{
  void *Pool2; // rax
  __int64 v8; // rbx
  void *v9; // rax
  __int64 v10; // r9
  __int64 v11; // r13
  volatile signed __int32 *v12; // r15
  __int64 v13; // r8
  int v14; // ebx
  __int64 v16; // rax
  _QWORD *v17; // rbx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  HANDLE v23; // rbx
  NTSTATUS v24; // edi
  unsigned int v25; // eax
  __int64 v26; // rdx
  HANDLE v27; // rdi
  __int64 v28; // rdx
  NTSTATUS v29; // esi
  HANDLE v30; // rsi
  int value; // r14d
  PVOID v32; // r14
  PVOID v33; // rcx
  bool v34; // zf
  __int64 v35; // rdx
  __int64 v36; // rdx
  volatile signed __int32 **v37; // rcx
  HANDLE v38; // [rsp+20h] [rbp-30h] BYREF
  HANDLE v39; // [rsp+28h] [rbp-28h] BYREF
  __int64 v40; // [rsp+30h] [rbp-20h] BYREF
  PVOID P; // [rsp+38h] [rbp-18h]
  __int64 v42; // [rsp+40h] [rbp-10h] BYREF
  volatile signed __int32 *v43; // [rsp+48h] [rbp-8h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v45; // [rsp+A8h] [rbp+58h]

  v45 = a4;
  if ( !a1 || !a3 )
    return 3221225485LL;
  Pool2 = (void *)ExAllocatePool2(64, 192, 1715758931);
  v8 = (__int64)Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0xC0u);
    v9 = (void *)Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v8);
  }
  else
  {
    v9 = 0;
  }
  kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
    &v42,
    v9);
  v11 = v42;
  v12 = v43;
  if ( !v42 )
    goto LABEL_97;
  if ( !v43 )
    return 3221225626LL;
  if ( !*((_DWORD *)v43 + 2) )
  {
LABEL_97:
    if ( v43 )
    {
LABEL_98:
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return 3221225626LL;
  }
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  v14 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          v42 + 48,
          a3,
          v13,
          v10);
  if ( v14 < 0 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) != 1 )
      return (unsigned int)v14;
LABEL_13:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v14;
  }
  v16 = ExAllocatePool2(64, 32, 1715758931);
  v17 = (_QWORD *)v16;
  if ( v16 )
  {
    *(_QWORD *)v16 = 0;
    *(_QWORD *)(v16 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(v16 + 16), 0);
  }
  else
  {
    v17 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    (_QWORD *)v11,
    v17);
  if ( !*(_QWORD *)v11 || (v19 = *(_QWORD *)(v11 + 8)) == 0 || !*(_DWORD *)(v19 + 8) )
  {
    if ( v12 )
      goto LABEL_98;
    return 3221225626LL;
  }
  v20 = -1;
  do
    ++v20;
  while ( a1[v20] );
  v14 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          *(_QWORD *)v11,
          a1,
          v20,
          v18);
  if ( v14 < 0 )
    goto LABEL_26;
  if ( a2 )
  {
    v22 = -1;
    do
      ++v22;
    while ( a2[v22] );
    v14 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
            v11 + 16,
            a2,
            v22,
            v21);
    if ( v14 < 0 )
    {
LABEL_26:
      if ( !v12 || _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) != 1 )
        return (unsigned int)v14;
      goto LABEL_13;
    }
  }
  Handle = 0;
  v14 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
          &Handle,
          (__int64)a1,
          (__int64)a2,
          0);
  if ( v14 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    if ( !v12 || _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) != 1 )
      return (unsigned int)v14;
    goto LABEL_13;
  }
  v23 = Handle;
  v38 = 0;
  v24 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          Handle,
          (__int64)L"UserConfigEx",
          &v38);
  if ( v24 < 0 )
  {
    if ( v38 )
      ZwClose(v38);
    if ( v23 )
      ZwClose(v23);
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return (unsigned int)v24;
  }
  v25 = *(_DWORD *)(v11 + 48) >> 1;
  v39 = 0;
  if ( v25 <= 0xFFFF && (_WORD)v25 )
    v26 = *(_QWORD *)(v11 + 56);
  else
    v26 = 0;
  v27 = v38;
  v29 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          v38,
          v26,
          &v39);
  if ( v29 < 0 )
  {
    if ( v39 )
      ZwClose(v39);
    if ( v27 )
      ZwClose(v27);
    if ( v23 )
      ZwClose(v23);
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return (unsigned int)v29;
  }
  v30 = v39;
  v40 = 0;
  P = 0;
  value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
            v39,
            v28,
            (__int64)&v40);
  if ( value < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v30 )
      ZwClose(v30);
    if ( v27 )
      ZwClose(v27);
    if ( v23 )
      ZwClose(v23);
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return (unsigned int)value;
  }
  v32 = P;
  LODWORD(v38) = appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                   v11 + 80,
                   P,
                   v40);
  if ( (int)v38 >= 0 )
  {
    LODWORD(Handle) = 0;
    registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
      v30,
      (__int64)L"Global",
      &Handle);
    v34 = (_DWORD)Handle == 0;
    LODWORD(Handle) = 0;
    *(_BYTE *)(v11 + 184) = !v34;
    registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
      v30,
      (__int64)L"OnDemand",
      &Handle);
    *(_BYTE *)(v11 + 185) = (_DWORD)Handle != 0;
    Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_mappings(
      &v39,
      v35,
      v11 + 104);
    Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_vfs_volumes_list(
      &v39,
      v36,
      v11 + 104,
      v11 + 144);
    v37 = (volatile signed __int32 **)(v45 + 1);
    *v45 = v11;
    kernel_std::detail::shared_count::operator=(v37, &v43);
    v33 = P;
    if ( !P )
      goto LABEL_82;
    goto LABEL_81;
  }
  if ( v32 )
  {
    v33 = v32;
LABEL_81:
    ExFreePoolWithTag(v33, 0);
  }
LABEL_82:
  if ( v30 )
    ZwClose(v30);
  if ( v27 )
    ZwClose(v27);
  if ( v23 )
    ZwClose(v23);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x18000e960  mov     [rsp-38h+arg_8], rbx
0x18000e965  mov     [rsp-38h+arg_18], r9
0x18000e96a  push    rbp
0x18000e96b  push    rsi
0x18000e96c  push    rdi
0x18000e96d  push    r12
0x18000e96f  push    r13
0x18000e971  push    r14
0x18000e973  push    r15
0x18000e975  mov     rbp, rsp
0x18000e978  sub     rsp, 50h
0x18000e97c  xor     r12d, r12d
0x18000e97f  mov     rdi, r8
0x18000e982  mov     rsi, rdx
0x18000e985  mov     r14, rcx
0x18000e988  test    rcx, rcx
0x18000e98b  jz      loc_18000EF4E
0x18000e991  test    r8, r8
0x18000e994  jz      loc_18000EF4E
0x18000e99a  mov     r15d, 0C0h
0x18000e9a0  lea     ecx, [r12+40h]
0x18000e9a5  mov     edx, r15d
0x18000e9a8  mov     r8d, 66446753h
0x18000e9ae  call    cs:__imp_ExAllocatePool2
0x18000e9b5  nop     dword ptr [rax+rax+00h]
0x18000e9ba  mov     rbx, rax
0x18000e9bd  test    rax, rax
0x18000e9c0  jz      short loc_18000E9D9
0x18000e9c2  mov     r8d, r15d; Size
0x18000e9c5  xor     edx, edx; Val
0x18000e9c7  mov     rcx, rax; void *
0x18000e9ca  call    memset
0x18000e9cf  mov     rcx, rbx
0x18000e9d2  call    ??0?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x18000e9d7  jmp     short loc_18000E9DC
0x18000e9d9  mov     rax, r12
0x18000e9dc  mov     rdx, rax
0x18000e9df  lea     rcx, [rbp+var_10]
0x18000e9e3  call    ??$?0V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x18000e9e8  mov     r13, [rbp+var_10]
0x18000e9ec  mov     r15, [rbp+var_8]
0x18000e9f0  test    r13, r13
0x18000e9f3  jz      loc_18000EF04
0x18000e9f9  test    r15, r15
0x18000e9fc  jz      loc_18000EF47
0x18000ea02  mov     eax, [r15+8]
0x18000ea06  test    eax, eax
0x18000ea08  jz      loc_18000EF04
0x18000ea0e  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ea12  mov     r8, r12
0x18000ea15  xor     ecx, ecx
0x18000ea17  inc     r8
0x18000ea1a  cmp     [rdi+r8*2], cx
0x18000ea1f  jnz     short loc_18000EA17
0x18000ea21  mov     rdx, rdi
0x18000ea24  lea     rcx, [r13+30h]
0x18000ea28  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000ea2d  xor     edi, edi
0x18000ea2f  mov     ebx, eax
0x18000ea31  test    eax, eax
0x18000ea33  jns     short loc_18000EA76
0x18000ea35  mov     ecx, r12d
0x18000ea38  lock xadd [r15+8], ecx
0x18000ea3e  add     ecx, r12d
0x18000ea41  jnz     short loc_18000EA6F
0x18000ea43  mov     rdx, [r15]
0x18000ea46  mov     rax, [rdx+8]
0x18000ea4a  mov     rcx, r15
0x18000ea4d  call    _guard_dispatch_icall
0x18000ea52  mov     eax, r12d
0x18000ea55  lock xadd [r15+0Ch], eax
0x18000ea5b  add     eax, r12d
0x18000ea5e  jnz     short loc_18000EA6F
0x18000ea60  mov     rax, [r15]
0x18000ea63  mov     rcx, r15
0x18000ea66  mov     rax, [rax+10h]
0x18000ea6a  call    _guard_dispatch_icall
0x18000ea6f  mov     eax, ebx
0x18000ea71  jmp     loc_18000EF53
0x18000ea76  mov     edx, 20h ; ' '
0x18000ea7b  mov     r8d, 66446753h
0x18000ea81  lea     ecx, [rdx+20h]
0x18000ea84  call    cs:__imp_ExAllocatePool2
0x18000ea8b  nop     dword ptr [rax+rax+00h]
0x18000ea90  mov     rbx, rax
0x18000ea93  test    rax, rax
0x18000ea96  jz      short loc_18000EAB3
0x18000ea98  lea     rcx, [rax+10h]; DestinationString
0x18000ea9c  mov     [rax], rdi
0x18000ea9f  xor     edx, edx; SourceString
0x18000eaa1  mov     [rax+8], rdi
0x18000eaa5  call    cs:__imp_RtlInitUnicodeString
0x18000eaac  nop     dword ptr [rax+rax+00h]
0x18000eab1  jmp     short loc_18000EAB6
0x18000eab3  mov     rbx, rdi
0x18000eab6  mov     rdx, rbx
0x18000eab9  mov     rcx, r13
0x18000eabc  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000eac1  cmp     [r13+0], rdi
0x18000eac5  jz      loc_18000EEFD
0x18000eacb  mov     rax, [r13+8]
0x18000eacf  test    rax, rax
0x18000ead2  jz      loc_18000EEFD
0x18000ead8  mov     eax, [rax+8]
0x18000eadb  test    eax, eax
0x18000eadd  jz      loc_18000EEFD
0x18000eae3  mov     rcx, [r13+0]
0x18000eae7  mov     r8, r12
0x18000eaea  inc     r8
0x18000eaed  cmp     [r14+r8*2], di
0x18000eaf2  jnz     short loc_18000EAEA
0x18000eaf4  mov     rdx, r14
0x18000eaf7  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000eafc  mov     ebx, eax
0x18000eafe  test    eax, eax
0x18000eb00  jns     short loc_18000EB29
0x18000eb02  test    r15, r15
0x18000eb05  jz      loc_18000EA6F
0x18000eb0b  mov     ecx, r12d
0x18000eb0e  lock xadd [r15+8], ecx
0x18000eb14  add     ecx, r12d
0x18000eb17  jnz     loc_18000EA6F
0x18000eb1d  mov     rcx, [r15]
0x18000eb20  mov     rax, [rcx+8]
0x18000eb24  jmp     loc_18000EA4A
0x18000eb29  test    rsi, rsi
0x18000eb2c  jz      short loc_18000EB4D
0x18000eb2e  lea     rcx, [r13+10h]
0x18000eb32  mov     r8, r12
0x18000eb35  inc     r8
0x18000eb38  cmp     [rsi+r8*2], di
0x18000eb3d  jnz     short loc_18000EB35
0x18000eb3f  mov     rdx, rsi
0x18000eb42  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000eb47  mov     ebx, eax
0x18000eb49  test    eax, eax
0x18000eb4b  js      short loc_18000EB02
0x18000eb4d  xor     r9d, r9d
0x18000eb50  mov     [rbp+Handle], rdi
0x18000eb54  mov     r8, rsi
0x18000eb57  lea     rcx, [rbp+Handle]
0x18000eb5b  mov     rdx, r14
0x18000eb5e  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x18000eb63  mov     ebx, eax
0x18000eb65  test    eax, eax
0x18000eb67  jns     short loc_18000EBA5
0x18000eb69  mov     rcx, [rbp+Handle]; Handle
0x18000eb6d  test    rcx, rcx
0x18000eb70  jz      short loc_18000EB7E
0x18000eb72  call    cs:__imp_ZwClose
0x18000eb79  nop     dword ptr [rax+rax+00h]
0x18000eb7e  test    r15, r15
0x18000eb81  jz      loc_18000EA6F
0x18000eb87  mov     eax, r12d
0x18000eb8a  lock xadd [r15+8], eax
0x18000eb90  add     eax, r12d
0x18000eb93  jnz     loc_18000EA6F
0x18000eb99  mov     rax, [r15]
0x18000eb9c  mov     rax, [rax+8]
0x18000eba0  jmp     loc_18000EA4A
0x18000eba5  mov     rbx, [rbp+Handle]
0x18000eba9  lea     r8, [rbp+var_30]
0x18000ebad  mov     rcx, rbx
0x18000ebb0  mov     [rbp+var_30], rdi
0x18000ebb4  lea     rdx, aUserconfigex; "UserConfigEx"
0x18000ebbb  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000ebc0  xor     r14d, r14d
0x18000ebc3  mov     edi, eax
0x18000ebc5  test    eax, eax
0x18000ebc7  jns     short loc_18000EC38
0x18000ebc9  mov     rcx, [rbp+var_30]; Handle
0x18000ebcd  test    rcx, rcx
0x18000ebd0  jz      short loc_18000EBDE
0x18000ebd2  call    cs:__imp_ZwClose
0x18000ebd9  nop     dword ptr [rax+rax+00h]
0x18000ebde  test    rbx, rbx
0x18000ebe1  jz      short loc_18000EBF2
0x18000ebe3  mov     rcx, rbx; Handle
0x18000ebe6  call    cs:__imp_ZwClose
0x18000ebed  nop     dword ptr [rax+rax+00h]
0x18000ebf2  test    r15, r15
0x18000ebf5  jz      short loc_18000EC31
0x18000ebf7  mov     eax, r12d
0x18000ebfa  lock xadd [r15+8], eax
0x18000ec00  add     eax, r12d
0x18000ec03  jnz     short loc_18000EC31
0x18000ec05  mov     rax, [r15]
0x18000ec08  mov     rcx, r15
0x18000ec0b  mov     rax, [rax+8]
0x18000ec0f  call    _guard_dispatch_icall
0x18000ec14  mov     eax, r12d
0x18000ec17  lock xadd [r15+0Ch], eax
0x18000ec1d  add     eax, r12d
0x18000ec20  jnz     short loc_18000EC31
0x18000ec22  mov     rax, [r15]
0x18000ec25  mov     rcx, r15
0x18000ec28  mov     rax, [rax+10h]
0x18000ec2c  call    _guard_dispatch_icall
0x18000ec31  mov     eax, edi
0x18000ec33  jmp     loc_18000EF53
0x18000ec38  mov     eax, [r13+30h]
0x18000ec3c  shr     eax, 1
0x18000ec3e  mov     [rbp+var_28], r14
0x18000ec42  cmp     eax, 0FFFFh
0x18000ec47  ja      short loc_18000EC54
0x18000ec49  test    ax, ax
0x18000ec4c  jz      short loc_18000EC54
0x18000ec4e  mov     rdx, [r13+38h]
0x18000ec52  jmp     short loc_18000EC57
0x18000ec54  mov     rdx, r14
0x18000ec57  mov     rdi, [rbp+var_30]
0x18000ec5b  lea     r8, [rbp+var_28]
0x18000ec5f  mov     rcx, rdi
0x18000ec62  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000ec67  mov     esi, eax
0x18000ec69  test    eax, eax
0x18000ec6b  jns     loc_18000ECF4
0x18000ec71  mov     rcx, [rbp+var_28]; Handle
0x18000ec75  test    rcx, rcx
0x18000ec78  jz      short loc_18000EC86
0x18000ec7a  call    cs:__imp_ZwClose
0x18000ec81  nop     dword ptr [rax+rax+00h]
0x18000ec86  test    rdi, rdi
0x18000ec89  jz      short loc_18000EC9A
0x18000ec8b  mov     rcx, rdi; Handle
0x18000ec8e  call    cs:__imp_ZwClose
0x18000ec95  nop     dword ptr [rax+rax+00h]
0x18000ec9a  test    rbx, rbx
0x18000ec9d  jz      short loc_18000ECAE
0x18000ec9f  mov     rcx, rbx; Handle
0x18000eca2  call    cs:__imp_ZwClose
0x18000eca9  nop     dword ptr [rax+rax+00h]
0x18000ecae  test    r15, r15
0x18000ecb1  jz      short loc_18000ECED
0x18000ecb3  mov     eax, r12d
0x18000ecb6  lock xadd [r15+8], eax
0x18000ecbc  add     eax, r12d
0x18000ecbf  jnz     short loc_18000ECED
0x18000ecc1  mov     rax, [r15]
0x18000ecc4  mov     rcx, r15
0x18000ecc7  mov     rax, [rax+8]
0x18000eccb  call    _guard_dispatch_icall
0x18000ecd0  mov     eax, r12d
0x18000ecd3  lock xadd [r15+0Ch], eax
0x18000ecd9  add     eax, r12d
0x18000ecdc  jnz     short loc_18000ECED
0x18000ecde  mov     rax, [r15]
0x18000ece1  mov     rcx, r15
0x18000ece4  mov     rax, [rax+10h]
0x18000ece8  call    _guard_dispatch_icall
0x18000eced  mov     eax, esi
0x18000ecef  jmp     loc_18000EF53
0x18000ecf4  mov     rsi, [rbp+var_28]
0x18000ecf8  lea     r8, [rbp+var_20]
0x18000ecfc  mov     rcx, rsi
0x18000ecff  mov     [rbp+var_20], r14
0x18000ed03  mov     [rbp+P], r14
0x18000ed07  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000ed0c  mov     r14d, eax
0x18000ed0f  test    eax, eax
0x18000ed11  jns     loc_18000EDB1
0x18000ed17  mov     rcx, [rbp+P]; P
0x18000ed1b  test    rcx, rcx
0x18000ed1e  jz      short loc_18000ED2E
0x18000ed20  xor     edx, edx; Tag
0x18000ed22  call    cs:__imp_ExFreePoolWithTag
0x18000ed29  nop     dword ptr [rax+rax+00h]
0x18000ed2e  test    rsi, rsi
0x18000ed31  jz      short loc_18000ED42
0x18000ed33  mov     rcx, rsi; Handle
0x18000ed36  call    cs:__imp_ZwClose
0x18000ed3d  nop     dword ptr [rax+rax+00h]
0x18000ed42  test    rdi, rdi
0x18000ed45  jz      short loc_18000ED56
0x18000ed47  mov     rcx, rdi; Handle
0x18000ed4a  call    cs:__imp_ZwClose
0x18000ed51  nop     dword ptr [rax+rax+00h]
0x18000ed56  test    rbx, rbx
0x18000ed59  jz      short loc_18000ED6A
0x18000ed5b  mov     rcx, rbx; Handle
0x18000ed5e  call    cs:__imp_ZwClose
0x18000ed65  nop     dword ptr [rax+rax+00h]
0x18000ed6a  test    r15, r15
0x18000ed6d  jz      short loc_18000EDA9
0x18000ed6f  mov     eax, r12d
0x18000ed72  lock xadd [r15+8], eax
0x18000ed78  add     eax, r12d
0x18000ed7b  jnz     short loc_18000EDA9
0x18000ed7d  mov     rax, [r15]
0x18000ed80  mov     rcx, r15
0x18000ed83  mov     rax, [rax+8]
0x18000ed87  call    _guard_dispatch_icall
0x18000ed8c  mov     eax, r12d
0x18000ed8f  lock xadd [r15+0Ch], eax
0x18000ed95  add     eax, r12d
0x18000ed98  jnz     short loc_18000EDA9
0x18000ed9a  mov     rax, [r15]
0x18000ed9d  mov     rcx, r15
0x18000eda0  mov     rax, [rax+10h]
0x18000eda4  call    _guard_dispatch_icall
  ... truncated ...
```
