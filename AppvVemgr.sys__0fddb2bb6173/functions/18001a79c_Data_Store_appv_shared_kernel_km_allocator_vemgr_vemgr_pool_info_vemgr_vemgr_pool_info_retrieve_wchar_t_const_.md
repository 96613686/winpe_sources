# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x18001a79c`
- end: `0x18001ab5a`
- name: `?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_WAEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(_WORD *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016474`

## callees

- `0x1800011ec`
- `0x180003f50`
- `0x1800046d4`
- `0x180005430`
- `0x18000a9e4`
- `0x18000ce10`
- `0x18000cf74`
- `0x18000e23c`
- `0x18000f300`
- `0x18001a79c`
- `0x18001bb30`
- `0x18001bf00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001a7de`
- `ntoskrnl!ExAllocatePool2` at `0x18001a848`
- `ntoskrnl!ExAllocatePool2` at `0x18001a7de`
- `ntoskrnl!ExAllocatePool2` at `0x18001a848`
- `ntoskrnl!ZwClose` at `0x18001a931`
- `ntoskrnl!ZwClose` at `0x18001a997`
- `ntoskrnl!ZwClose` at `0x18001a9ab`
- `ntoskrnl!ZwClose` at `0x18001aa21`
- `ntoskrnl!ZwClose` at `0x18001aa35`
- `ntoskrnl!ZwClose` at `0x18001a931`
- `ntoskrnl!ZwClose` at `0x18001a997`
- `ntoskrnl!ZwClose` at `0x18001a9ab`
- `ntoskrnl!ZwClose` at `0x18001aa21`
- `ntoskrnl!ZwClose` at `0x18001aa35`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001a869`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001a869`

## string_xrefs

- `0x18001a914`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Packages`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
        _WORD *a1,
        __int64 a2)
{
  void *Pool2; // rax
  __int64 v6; // rbx
  void *v7; // rax
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
  int value; // r12d
  bool v23; // zf
  __int64 v24; // rdx
  __int64 *v25; // [rsp+20h] [rbp-10h] BYREF
  volatile signed __int32 *v26; // [rsp+28h] [rbp-8h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+40h] BYREF
  HANDLE v28; // [rsp+80h] [rbp+50h] BYREF

  if ( !a1 )
    return 3221225485LL;
  Pool2 = (void *)ExAllocatePool2(64, 136, 1715758931);
  v6 = (__int64)Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x88u);
    v7 = (void *)Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v6);
  }
  else
  {
    v7 = 0;
  }
  kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
    &v25,
    v7);
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
          (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Packages",
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
  v28 = 0;
  v17 = *(_DWORD *)v16 >> 1;
  if ( v17 <= 0xFFFF && (_WORD)v17 )
    v18 = *(_QWORD *)(v16 + 8);
  else
    v18 = 0;
  v19 = Handle;
  v20 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
          Handle,
          v18,
          &v28);
  if ( v20 >= 0 )
  {
    v21 = v28;
    value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
              v28,
              (__int64)L"PackageRoot",
              (__int64)(v8 + 2));
    if ( value >= 0 )
    {
      LODWORD(Handle) = 0;
      value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                v21,
                (__int64)L"Packaged32",
                &Handle);
      if ( value >= 0 )
      {
        v23 = (_DWORD)Handle == 0;
        LODWORD(Handle) = 0;
        *((_BYTE *)v8 + 48) = !v23;
        registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
          v21,
          (__int64)L"JITV",
          &Handle);
        *((_BYTE *)v8 + 49) = (_DWORD)Handle != 0;
        Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_mappings(
          &v28,
          v24,
          v8 + 7);
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
    if ( v28 )
      ZwClose(v28);
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
0x18001a79c  mov     [rsp-38h+arg_8], rbx
0x18001a7a1  push    rbp
0x18001a7a2  push    rsi
0x18001a7a3  push    rdi
0x18001a7a4  push    r12
0x18001a7a6  push    r13
0x18001a7a8  push    r14
0x18001a7aa  push    r15
0x18001a7ac  mov     rbp, rsp
0x18001a7af  sub     rsp, 30h
0x18001a7b3  xor     r12d, r12d
0x18001a7b6  mov     r13, rdx
0x18001a7b9  mov     rdi, rcx
0x18001a7bc  test    rcx, rcx
0x18001a7bf  jnz     short loc_18001A7CB
0x18001a7c1  mov     eax, 0C000000Dh
0x18001a7c6  jmp     loc_18001AB44
0x18001a7cb  mov     esi, 88h
0x18001a7d0  mov     r14d, 66446753h
0x18001a7d6  mov     r8d, r14d
0x18001a7d9  mov     edx, esi
0x18001a7db  lea     ecx, [rsi-48h]
0x18001a7de  call    cs:__imp_ExAllocatePool2
0x18001a7e5  nop     dword ptr [rax+rax+00h]
0x18001a7ea  mov     rbx, rax
0x18001a7ed  test    rax, rax
0x18001a7f0  jz      short loc_18001A809
0x18001a7f2  mov     r8d, esi; Size
0x18001a7f5  xor     edx, edx; Val
0x18001a7f7  mov     rcx, rax; void *
0x18001a7fa  call    memset
0x18001a7ff  mov     rcx, rbx
0x18001a802  call    ??0?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x18001a807  jmp     short loc_18001A80C
0x18001a809  mov     rax, r12
0x18001a80c  mov     rdx, rax
0x18001a80f  lea     rcx, [rbp+var_10]
0x18001a813  call    ??$?0V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x18001a818  mov     r15, [rbp+var_10]
0x18001a81c  mov     rsi, [rbp+var_8]
0x18001a820  test    r15, r15
0x18001a823  jz      loc_18001AAFE
0x18001a829  test    rsi, rsi
0x18001a82c  jz      loc_18001AB3F
0x18001a832  mov     eax, [rsi+8]
0x18001a835  test    eax, eax
0x18001a837  jz      loc_18001AAFE
0x18001a83d  mov     edx, 20h ; ' '
0x18001a842  mov     r8d, r14d
0x18001a845  lea     ecx, [rdx+20h]
0x18001a848  call    cs:__imp_ExAllocatePool2
0x18001a84f  nop     dword ptr [rax+rax+00h]
0x18001a854  mov     rbx, rax
0x18001a857  test    rax, rax
0x18001a85a  jz      short loc_18001A877
0x18001a85c  lea     rcx, [rax+10h]; DestinationString
0x18001a860  mov     [rax], r12
0x18001a863  xor     edx, edx; SourceString
0x18001a865  mov     [rax+8], r12
0x18001a869  call    cs:__imp_RtlInitUnicodeString
0x18001a870  nop     dword ptr [rax+rax+00h]
0x18001a875  jmp     short loc_18001A87A
0x18001a877  mov     rbx, r12
0x18001a87a  mov     rdx, rbx
0x18001a87d  mov     rcx, r15
0x18001a880  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18001a885  cmp     [r15], r12
0x18001a888  jz      loc_18001AAFE
0x18001a88e  mov     rax, [r15+8]
0x18001a892  test    rax, rax
0x18001a895  jz      loc_18001AAFE
0x18001a89b  mov     eax, [rax+8]
0x18001a89e  test    eax, eax
0x18001a8a0  jz      loc_18001AAFE
0x18001a8a6  mov     rcx, [r15]
0x18001a8a9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001a8ad  mov     r8, r14
0x18001a8b0  inc     r8
0x18001a8b3  cmp     [rdi+r8*2], r12w
0x18001a8b8  jnz     short loc_18001A8B0
0x18001a8ba  mov     rdx, rdi
0x18001a8bd  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18001a8c2  mov     ebx, eax
0x18001a8c4  test    eax, eax
0x18001a8c6  jns     short loc_18001A90C
0x18001a8c8  test    rsi, rsi
0x18001a8cb  jz      short loc_18001A905
0x18001a8cd  mov     ecx, r14d
0x18001a8d0  lock xadd [rsi+8], ecx
0x18001a8d5  add     ecx, r14d
0x18001a8d8  jnz     short loc_18001A905
0x18001a8da  mov     rdx, [rsi]
0x18001a8dd  mov     rax, [rdx+8]
0x18001a8e1  mov     rcx, rsi
0x18001a8e4  call    _guard_dispatch_icall
0x18001a8e9  mov     eax, r14d
0x18001a8ec  lock xadd [rsi+0Ch], eax
0x18001a8f1  add     eax, r14d
0x18001a8f4  jnz     short loc_18001A905
0x18001a8f6  mov     rax, [rsi]
0x18001a8f9  mov     rcx, rsi
0x18001a8fc  mov     rax, [rax+10h]
0x18001a900  call    _guard_dispatch_icall
0x18001a905  mov     eax, ebx
0x18001a907  jmp     loc_18001AB44
0x18001a90c  lea     r8, [rbp+Handle]
0x18001a910  mov     [rbp+Handle], r12
0x18001a914  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18001a91b  xor     ecx, ecx
0x18001a91d  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001a922  mov     ebx, eax
0x18001a924  test    eax, eax
0x18001a926  jns     short loc_18001A958
0x18001a928  mov     rcx, [rbp+Handle]; Handle
0x18001a92c  test    rcx, rcx
0x18001a92f  jz      short loc_18001A93D
0x18001a931  call    cs:__imp_ZwClose
0x18001a938  nop     dword ptr [rax+rax+00h]
0x18001a93d  test    rsi, rsi
0x18001a940  jz      short loc_18001A905
0x18001a942  mov     eax, r14d
0x18001a945  lock xadd [rsi+8], eax
0x18001a94a  add     eax, r14d
0x18001a94d  jnz     short loc_18001A905
0x18001a94f  mov     rax, [rsi]
0x18001a952  mov     rax, [rax+8]
0x18001a956  jmp     short loc_18001A8E1
0x18001a958  mov     rcx, [r15]
0x18001a95b  mov     [rbp+arg_10], r12
0x18001a95f  mov     eax, [rcx]
0x18001a961  shr     eax, 1
0x18001a963  cmp     eax, 0FFFFh
0x18001a968  ja      short loc_18001A975
0x18001a96a  test    ax, ax
0x18001a96d  jz      short loc_18001A975
0x18001a96f  mov     rdx, [rcx+8]
0x18001a973  jmp     short loc_18001A978
0x18001a975  mov     rdx, r12
0x18001a978  mov     rbx, [rbp+Handle]
0x18001a97c  lea     r8, [rbp+arg_10]
0x18001a980  mov     rcx, rbx
0x18001a983  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001a988  mov     edi, eax
0x18001a98a  test    eax, eax
0x18001a98c  jns     short loc_18001A9FB
0x18001a98e  mov     rcx, [rbp+arg_10]; Handle
0x18001a992  test    rcx, rcx
0x18001a995  jz      short loc_18001A9A3
0x18001a997  call    cs:__imp_ZwClose
0x18001a99e  nop     dword ptr [rax+rax+00h]
0x18001a9a3  test    rbx, rbx
0x18001a9a6  jz      short loc_18001A9B7
0x18001a9a8  mov     rcx, rbx; Handle
0x18001a9ab  call    cs:__imp_ZwClose
0x18001a9b2  nop     dword ptr [rax+rax+00h]
0x18001a9b7  test    rsi, rsi
0x18001a9ba  jz      short loc_18001A9F4
0x18001a9bc  mov     eax, r14d
0x18001a9bf  lock xadd [rsi+8], eax
0x18001a9c4  add     eax, r14d
0x18001a9c7  jnz     short loc_18001A9F4
0x18001a9c9  mov     rax, [rsi]
0x18001a9cc  mov     rcx, rsi
0x18001a9cf  mov     rax, [rax+8]
0x18001a9d3  call    _guard_dispatch_icall
0x18001a9d8  mov     eax, r14d
0x18001a9db  lock xadd [rsi+0Ch], eax
0x18001a9e0  add     eax, r14d
0x18001a9e3  jnz     short loc_18001A9F4
0x18001a9e5  mov     rax, [rsi]
0x18001a9e8  mov     rcx, rsi
0x18001a9eb  mov     rax, [rax+10h]
0x18001a9ef  call    _guard_dispatch_icall
0x18001a9f4  mov     eax, edi
0x18001a9f6  jmp     loc_18001AB44
0x18001a9fb  mov     rdi, [rbp+arg_10]
0x18001a9ff  lea     r8, [r15+10h]
0x18001aa03  mov     rcx, rdi
0x18001aa06  lea     rdx, aPackageroot; "PackageRoot"
0x18001aa0d  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18001aa12  mov     r12d, eax
0x18001aa15  test    eax, eax
0x18001aa17  jns     short loc_18001AA86
0x18001aa19  test    rdi, rdi
0x18001aa1c  jz      short loc_18001AA2D
0x18001aa1e  mov     rcx, rdi; Handle
0x18001aa21  call    cs:__imp_ZwClose
0x18001aa28  nop     dword ptr [rax+rax+00h]
0x18001aa2d  test    rbx, rbx
0x18001aa30  jz      short loc_18001AA41
0x18001aa32  mov     rcx, rbx; Handle
0x18001aa35  call    cs:__imp_ZwClose
0x18001aa3c  nop     dword ptr [rax+rax+00h]
0x18001aa41  test    rsi, rsi
0x18001aa44  jz      short loc_18001AA7E
0x18001aa46  mov     eax, r14d
0x18001aa49  lock xadd [rsi+8], eax
0x18001aa4e  add     eax, r14d
0x18001aa51  jnz     short loc_18001AA7E
0x18001aa53  mov     rax, [rsi]
0x18001aa56  mov     rcx, rsi
0x18001aa59  mov     rax, [rax+8]
0x18001aa5d  call    _guard_dispatch_icall
0x18001aa62  mov     eax, r14d
0x18001aa65  lock xadd [rsi+0Ch], eax
0x18001aa6a  add     eax, r14d
0x18001aa6d  jnz     short loc_18001AA7E
0x18001aa6f  mov     rax, [rsi]
0x18001aa72  mov     rcx, rsi
0x18001aa75  mov     rax, [rax+10h]
0x18001aa79  call    _guard_dispatch_icall
0x18001aa7e  mov     eax, r12d
0x18001aa81  jmp     loc_18001AB44
0x18001aa86  lea     r8, [rbp+Handle]
0x18001aa8a  mov     dword ptr [rbp+Handle], 0
0x18001aa91  lea     rdx, aPackaged32; "Packaged32"
0x18001aa98  mov     rcx, rdi
0x18001aa9b  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x18001aaa0  mov     r12d, eax
0x18001aaa3  test    eax, eax
0x18001aaa5  js      loc_18001AA19
0x18001aaab  cmp     dword ptr [rbp+Handle], 0
0x18001aaaf  lea     r8, [rbp+Handle]
0x18001aab3  lea     rdx, aJitv; "JITV"
0x18001aaba  mov     dword ptr [rbp+Handle], 0
0x18001aac1  setnz   al
0x18001aac4  mov     rcx, rdi
0x18001aac7  mov     [r15+30h], al
0x18001aacb  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x18001aad0  cmp     dword ptr [rbp+Handle], 0
0x18001aad4  lea     r8, [r15+38h]
0x18001aad8  lea     rcx, [rbp+arg_10]
0x18001aadc  setnz   al
0x18001aadf  mov     [r15+31h], al
0x18001aae3  call    ?retrieve_mappings@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEAV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_mappings(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18001aae8  lea     rcx, [r13+8]
0x18001aaec  mov     [r13+0], r15
0x18001aaf0  lea     rdx, [rbp+var_8]
0x18001aaf4  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18001aaf9  jmp     loc_18001AA19
0x18001aafe  test    rsi, rsi
0x18001ab01  jz      short loc_18001AB3F
0x18001ab03  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001ab07  mov     eax, r14d
0x18001ab0a  lock xadd [rsi+8], eax
0x18001ab0f  add     eax, r14d
0x18001ab12  jnz     short loc_18001AB3F
0x18001ab14  mov     rax, [rsi]
0x18001ab17  mov     rcx, rsi
0x18001ab1a  mov     rax, [rax+8]
0x18001ab1e  call    _guard_dispatch_icall
0x18001ab23  mov     eax, r14d
0x18001ab26  lock xadd [rsi+0Ch], eax
0x18001ab2b  add     eax, r14d
0x18001ab2e  jnz     short loc_18001AB3F
0x18001ab30  mov     rax, [rsi]
0x18001ab33  mov     rcx, rsi
0x18001ab36  mov     rax, [rax+10h]
0x18001ab3a  call    _guard_dispatch_icall
0x18001ab3f  mov     eax, 0C000009Ah
0x18001ab44  mov     rbx, [rsp+30h+arg_8]
0x18001ab49  add     rsp, 30h
0x18001ab4d  pop     r15
0x18001ab4f  pop     r14
0x18001ab51  pop     r13
0x18001ab53  pop     r12
0x18001ab55  pop     rdi
0x18001ab56  pop     rsi
0x18001ab57  pop     rbp
0x18001ab58  retn
```
