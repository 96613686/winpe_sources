# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x18000ef74`
- end: `0x18000f2f8`
- name: `?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_WAEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `900`
- prototype: `__int64 __fastcall(_WORD *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800021d0`
- `0x18001a024`

## callees

- `0x18000129c`
- `0x180003f50`
- `0x180005430`
- `0x18000a9e4`
- `0x18000bfb8`
- `0x18000ce10`
- `0x18000e23c`
- `0x18000ef74`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000efb5`
- `ntoskrnl!ExAllocatePool2` at `0x18000f029`
- `ntoskrnl!ExAllocatePool2` at `0x18000efb5`
- `ntoskrnl!ExAllocatePool2` at `0x18000f029`
- `ntoskrnl!ZwClose` at `0x18000f112`
- `ntoskrnl!ZwClose` at `0x18000f178`
- `ntoskrnl!ZwClose` at `0x18000f18c`
- `ntoskrnl!ZwClose` at `0x18000f206`
- `ntoskrnl!ZwClose` at `0x18000f21a`
- `ntoskrnl!ZwClose` at `0x18000f112`
- `ntoskrnl!ZwClose` at `0x18000f178`
- `ntoskrnl!ZwClose` at `0x18000f18c`
- `ntoskrnl!ZwClose` at `0x18000f206`
- `ntoskrnl!ZwClose` at `0x18000f21a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000f04a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000f04a`

## string_xrefs

- `0x18000f0f5`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Groups`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
        _WORD *a1,
        __int64 a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rax
  __int64 *v8; // r15
  volatile signed __int32 *v9; // rsi
  __int64 v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // ebx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rdx
  HANDLE v19; // rbx
  NTSTATUS v20; // edi
  HANDLE v21; // rdi
  __int64 v22; // r8
  __int64 v23; // r9
  int value; // r12d
  __int64 *v25; // [rsp+20h] [rbp-10h] BYREF
  volatile signed __int32 *v26; // [rsp+28h] [rbp-8h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+40h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+50h] BYREF

  if ( !a1 )
    return 3221225485LL;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1715758931);
  v6 = Pool2;
  if ( Pool2 )
  {
    Pool2[2] = 0;
    Pool2[7] = 0;
    *Pool2 = 0;
    Pool2[1] = 0;
    v7 = Pool2 + 3;
    *v7 = 0;
    v7[1] = 0;
    v7[3] = v7;
    v7[2] = v7;
  }
  else
  {
    v6 = 0;
  }
  kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
    &v25,
    v6);
  v8 = v25;
  v9 = v26;
  if ( !v25 )
    goto LABEL_62;
  if ( !v26 )
    return 3221225626LL;
  if ( !*((_DWORD *)v26 + 2) )
    goto LABEL_62;
  v10 = ExAllocatePool2(64, 32, 1715758931);
  v11 = (_QWORD *)v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = 0;
    *(_QWORD *)(v10 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(v10 + 16), 0);
  }
  else
  {
    v11 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    v8,
    v11);
  if ( !*v8 || (v13 = v8[1]) == 0 || !*(_DWORD *)(v13 + 8) )
  {
LABEL_62:
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return 3221225626LL;
  }
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
          *v8,
          a1,
          v14,
          v12);
  if ( v15 < 0 )
  {
    if ( !v9 || _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) != 1 )
      return (unsigned int)v15;
    goto LABEL_20;
  }
  Handle = 0;
  v15 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          0,
          (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Groups",
          &Handle);
  if ( v15 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    if ( !v9 || _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) != 1 )
      return (unsigned int)v15;
LABEL_20:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)v15;
  }
  v16 = *v8;
  KeyHandle = 0;
  v17 = *(_DWORD *)v16 >> 1;
  if ( v17 <= 0xFFFF && (_WORD)v17 )
    v18 = *(_QWORD *)(v16 + 8);
  else
    v18 = 0;
  v19 = Handle;
  v20 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          Handle,
          v18,
          &KeyHandle);
  if ( v20 >= 0 )
  {
    v21 = KeyHandle;
    LODWORD(Handle) = 0;
    value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
              KeyHandle,
              (__int64)L"Priority",
              &Handle);
    if ( value >= 0 )
    {
      *((_DWORD *)v8 + 14) = (_DWORD)Handle;
      value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
                v21,
                (__int64)(v8 + 2),
                v22,
                v23);
      if ( value >= 0 )
      {
        *(_QWORD *)a2 = v8;
        kernel_std::detail::shared_count::operator=((volatile signed __int32 **)(a2 + 8), &v26);
      }
    }
    if ( v21 )
      ZwClose(v21);
    if ( v19 )
      ZwClose(v19);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return (unsigned int)value;
  }
  else
  {
    if ( KeyHandle )
      ZwClose(KeyHandle);
    if ( v19 )
      ZwClose(v19);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x18000ef74  mov     [rsp-38h+arg_8], rbx
0x18000ef79  push    rbp
0x18000ef7a  push    rsi
0x18000ef7b  push    rdi
0x18000ef7c  push    r12
0x18000ef7e  push    r13
0x18000ef80  push    r14
0x18000ef82  push    r15
0x18000ef84  mov     rbp, rsp
0x18000ef87  sub     rsp, 30h
0x18000ef8b  xor     r12d, r12d
0x18000ef8e  mov     r13, rdx
0x18000ef91  mov     rdi, rcx
0x18000ef94  test    rcx, rcx
0x18000ef97  jnz     short loc_18000EFA3
0x18000ef99  mov     eax, 0C000000Dh
0x18000ef9e  jmp     loc_18000F2E2
0x18000efa3  mov     ebx, 40h ; '@'
0x18000efa8  mov     r14d, 66446753h
0x18000efae  mov     r8d, r14d
0x18000efb1  mov     edx, ebx
0x18000efb3  mov     ecx, ebx
0x18000efb5  call    cs:__imp_ExAllocatePool2
0x18000efbc  nop     dword ptr [rax+rax+00h]
0x18000efc1  mov     rdx, rax
0x18000efc4  test    rax, rax
0x18000efc7  jz      short loc_18000EFED
0x18000efc9  mov     [rax+10h], r12
0x18000efcd  mov     [rax+38h], r12
0x18000efd1  mov     [rax], r12
0x18000efd4  mov     [rax+8], r12
0x18000efd8  add     rax, 18h
0x18000efdc  mov     [rax], r12
0x18000efdf  mov     [rax+8], r12
0x18000efe3  mov     [rax+18h], rax
0x18000efe7  mov     [rax+10h], rax
0x18000efeb  jmp     short loc_18000EFF0
0x18000efed  mov     rdx, r12
0x18000eff0  lea     rcx, [rbp+var_10]
0x18000eff4  call    ??$?0V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x18000eff9  mov     r15, [rbp+var_10]
0x18000effd  mov     rsi, [rbp+var_8]
0x18000f001  test    r15, r15
0x18000f004  jz      loc_18000F29C
0x18000f00a  test    rsi, rsi
0x18000f00d  jz      loc_18000F2DD
0x18000f013  mov     eax, [rsi+8]
0x18000f016  test    eax, eax
0x18000f018  jz      loc_18000F29C
0x18000f01e  mov     r8d, r14d
0x18000f021  mov     edx, 20h ; ' '
0x18000f026  mov     rcx, rbx
0x18000f029  call    cs:__imp_ExAllocatePool2
0x18000f030  nop     dword ptr [rax+rax+00h]
0x18000f035  mov     rbx, rax
0x18000f038  test    rax, rax
0x18000f03b  jz      short loc_18000F058
0x18000f03d  lea     rcx, [rax+10h]; DestinationString
0x18000f041  mov     [rax], r12
0x18000f044  xor     edx, edx; SourceString
0x18000f046  mov     [rax+8], r12
0x18000f04a  call    cs:__imp_RtlInitUnicodeString
0x18000f051  nop     dword ptr [rax+rax+00h]
0x18000f056  jmp     short loc_18000F05B
0x18000f058  mov     rbx, r12
0x18000f05b  mov     rdx, rbx
0x18000f05e  mov     rcx, r15
0x18000f061  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000f066  cmp     [r15], r12
0x18000f069  jz      loc_18000F29C
0x18000f06f  mov     rax, [r15+8]
0x18000f073  test    rax, rax
0x18000f076  jz      loc_18000F29C
0x18000f07c  mov     eax, [rax+8]
0x18000f07f  test    eax, eax
0x18000f081  jz      loc_18000F29C
0x18000f087  mov     rcx, [r15]
0x18000f08a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f08e  mov     r8, r14
0x18000f091  inc     r8
0x18000f094  cmp     [rdi+r8*2], r12w
0x18000f099  jnz     short loc_18000F091
0x18000f09b  mov     rdx, rdi
0x18000f09e  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000f0a3  mov     ebx, eax
0x18000f0a5  test    eax, eax
0x18000f0a7  jns     short loc_18000F0ED
0x18000f0a9  test    rsi, rsi
0x18000f0ac  jz      short loc_18000F0E6
0x18000f0ae  mov     ecx, r14d
0x18000f0b1  lock xadd [rsi+8], ecx
0x18000f0b6  add     ecx, r14d
0x18000f0b9  jnz     short loc_18000F0E6
0x18000f0bb  mov     rdx, [rsi]
0x18000f0be  mov     rax, [rdx+8]
0x18000f0c2  mov     rcx, rsi
0x18000f0c5  call    _guard_dispatch_icall
0x18000f0ca  mov     eax, r14d
0x18000f0cd  lock xadd [rsi+0Ch], eax
0x18000f0d2  add     eax, r14d
0x18000f0d5  jnz     short loc_18000F0E6
0x18000f0d7  mov     rax, [rsi]
0x18000f0da  mov     rcx, rsi
0x18000f0dd  mov     rax, [rax+10h]
0x18000f0e1  call    _guard_dispatch_icall
0x18000f0e6  mov     eax, ebx
0x18000f0e8  jmp     loc_18000F2E2
0x18000f0ed  lea     r8, [rbp+Handle]
0x18000f0f1  mov     [rbp+Handle], r12
0x18000f0f5  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18000f0fc  xor     ecx, ecx
0x18000f0fe  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000f103  mov     ebx, eax
0x18000f105  test    eax, eax
0x18000f107  jns     short loc_18000F139
0x18000f109  mov     rcx, [rbp+Handle]; Handle
0x18000f10d  test    rcx, rcx
0x18000f110  jz      short loc_18000F11E
0x18000f112  call    cs:__imp_ZwClose
0x18000f119  nop     dword ptr [rax+rax+00h]
0x18000f11e  test    rsi, rsi
0x18000f121  jz      short loc_18000F0E6
0x18000f123  mov     eax, r14d
0x18000f126  lock xadd [rsi+8], eax
0x18000f12b  add     eax, r14d
0x18000f12e  jnz     short loc_18000F0E6
0x18000f130  mov     rax, [rsi]
0x18000f133  mov     rax, [rax+8]
0x18000f137  jmp     short loc_18000F0C2
0x18000f139  mov     rcx, [r15]
0x18000f13c  mov     [rbp+KeyHandle], r12
0x18000f140  mov     eax, [rcx]
0x18000f142  shr     eax, 1
0x18000f144  cmp     eax, 0FFFFh
0x18000f149  ja      short loc_18000F156
0x18000f14b  test    ax, ax
0x18000f14e  jz      short loc_18000F156
0x18000f150  mov     rdx, [rcx+8]
0x18000f154  jmp     short loc_18000F159
0x18000f156  mov     rdx, r12
0x18000f159  mov     rbx, [rbp+Handle]
0x18000f15d  lea     r8, [rbp+KeyHandle]
0x18000f161  mov     rcx, rbx
0x18000f164  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000f169  mov     edi, eax
0x18000f16b  test    eax, eax
0x18000f16d  jns     short loc_18000F1DC
0x18000f16f  mov     rcx, [rbp+KeyHandle]; Handle
0x18000f173  test    rcx, rcx
0x18000f176  jz      short loc_18000F184
0x18000f178  call    cs:__imp_ZwClose
0x18000f17f  nop     dword ptr [rax+rax+00h]
0x18000f184  test    rbx, rbx
0x18000f187  jz      short loc_18000F198
0x18000f189  mov     rcx, rbx; Handle
0x18000f18c  call    cs:__imp_ZwClose
0x18000f193  nop     dword ptr [rax+rax+00h]
0x18000f198  test    rsi, rsi
0x18000f19b  jz      short loc_18000F1D5
0x18000f19d  mov     eax, r14d
0x18000f1a0  lock xadd [rsi+8], eax
0x18000f1a5  add     eax, r14d
0x18000f1a8  jnz     short loc_18000F1D5
0x18000f1aa  mov     rax, [rsi]
0x18000f1ad  mov     rcx, rsi
0x18000f1b0  mov     rax, [rax+8]
0x18000f1b4  call    _guard_dispatch_icall
0x18000f1b9  mov     eax, r14d
0x18000f1bc  lock xadd [rsi+0Ch], eax
0x18000f1c1  add     eax, r14d
0x18000f1c4  jnz     short loc_18000F1D5
0x18000f1c6  mov     rax, [rsi]
0x18000f1c9  mov     rcx, rsi
0x18000f1cc  mov     rax, [rax+10h]
0x18000f1d0  call    _guard_dispatch_icall
0x18000f1d5  mov     eax, edi
0x18000f1d7  jmp     loc_18000F2E2
0x18000f1dc  mov     rdi, [rbp+KeyHandle]
0x18000f1e0  lea     r8, [rbp+Handle]
0x18000f1e4  mov     rcx, rdi
0x18000f1e7  mov     dword ptr [rbp+Handle], r12d
0x18000f1eb  lea     rdx, aPriority; "Priority"
0x18000f1f2  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x18000f1f7  mov     r12d, eax
0x18000f1fa  test    eax, eax
0x18000f1fc  jns     short loc_18000F268
0x18000f1fe  test    rdi, rdi
0x18000f201  jz      short loc_18000F212
0x18000f203  mov     rcx, rdi; Handle
0x18000f206  call    cs:__imp_ZwClose
0x18000f20d  nop     dword ptr [rax+rax+00h]
0x18000f212  test    rbx, rbx
0x18000f215  jz      short loc_18000F226
0x18000f217  mov     rcx, rbx; Handle
0x18000f21a  call    cs:__imp_ZwClose
0x18000f221  nop     dword ptr [rax+rax+00h]
0x18000f226  test    rsi, rsi
0x18000f229  jz      short loc_18000F263
0x18000f22b  mov     eax, r14d
0x18000f22e  lock xadd [rsi+8], eax
0x18000f233  add     eax, r14d
0x18000f236  jnz     short loc_18000F263
0x18000f238  mov     rax, [rsi]
0x18000f23b  mov     rcx, rsi
0x18000f23e  mov     rax, [rax+8]
0x18000f242  call    _guard_dispatch_icall
0x18000f247  mov     eax, r14d
0x18000f24a  lock xadd [rsi+0Ch], eax
0x18000f24f  add     eax, r14d
0x18000f252  jnz     short loc_18000F263
0x18000f254  mov     rax, [rsi]
0x18000f257  mov     rcx, rsi
0x18000f25a  mov     rax, [rax+10h]
0x18000f25e  call    _guard_dispatch_icall
0x18000f263  mov     eax, r12d
0x18000f266  jmp     short loc_18000F2E2
0x18000f268  mov     eax, dword ptr [rbp+Handle]
0x18000f26b  lea     rdx, [r15+10h]
0x18000f26f  mov     rcx, rdi; KeyHandle
0x18000f272  mov     [r15+38h], eax
0x18000f276  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000f27b  mov     r12d, eax
0x18000f27e  test    eax, eax
0x18000f280  js      loc_18000F1FE
0x18000f286  lea     rcx, [r13+8]
0x18000f28a  mov     [r13+0], r15
0x18000f28e  lea     rdx, [rbp+var_8]
0x18000f292  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000f297  jmp     loc_18000F1FE
0x18000f29c  test    rsi, rsi
0x18000f29f  jz      short loc_18000F2DD
0x18000f2a1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f2a5  mov     eax, r14d
0x18000f2a8  lock xadd [rsi+8], eax
0x18000f2ad  add     eax, r14d
0x18000f2b0  jnz     short loc_18000F2DD
0x18000f2b2  mov     rax, [rsi]
0x18000f2b5  mov     rcx, rsi
0x18000f2b8  mov     rax, [rax+8]
0x18000f2bc  call    _guard_dispatch_icall
0x18000f2c1  mov     eax, r14d
0x18000f2c4  lock xadd [rsi+0Ch], eax
0x18000f2c9  add     eax, r14d
0x18000f2cc  jnz     short loc_18000F2DD
0x18000f2ce  mov     rax, [rsi]
0x18000f2d1  mov     rcx, rsi
0x18000f2d4  mov     rax, [rax+10h]
0x18000f2d8  call    _guard_dispatch_icall
0x18000f2dd  mov     eax, 0C000009Ah
0x18000f2e2  mov     rbx, [rsp+30h+arg_8]
0x18000f2e7  add     rsp, 30h
0x18000f2eb  pop     r15
0x18000f2ed  pop     r14
0x18000f2ef  pop     r13
0x18000f2f1  pop     r12
0x18000f2f3  pop     rdi
0x18000f2f4  pop     rsi
0x18000f2f5  pop     rbp
0x18000f2f6  retn
```
