# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParseRunVirtualRegistry(ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,bool &)

- ea: `0x180018b9c`
- end: `0x180018e93`
- name: `?ParseRunVirtualRegistry@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NKAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEBV2345@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEA_N@Z`
- size: `759`
- prototype: `bool __fastcall(__int64, unsigned int, __int64, __int64, __int64 **, _BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018484`

## callees

- `0x180001598`
- `0x180001f78`
- `0x180002b48`
- `0x180002cb4`
- `0x180017c7c`
- `0x180018b9c`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180018df2`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018df2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018da3`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018da3`

## string_xrefs

- `0x180018be6`: `VirtualEnvironmentManager::ParseRunVirtualRegistry() - Failed to get sid from pid: %d. Error: %d`
- `0x180018c7c`: `VirtualEnvironmentManager::ParseRunVirtualRegistry() - Failed to find package, %s. Error: %d`
- `0x180018cf4`: `VirtualEnvironmentManager::ParseRunVirtualRegistry() - Package %s is not published`

## pseudocode

```c
bool __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParseRunVirtualRegistry(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        _BYTE *a6)
{
  int v10; // eax
  volatile signed __int32 *v12; // rdi
  __int64 *v13; // rbx
  __int64 v14; // rcx
  int v15; // r10d
  unsigned int v16; // edx
  __int16 v17; // r8
  __int16 v18; // ax
  __int64 v19; // r9
  _BYTE *v20; // r14
  __int64 **v21; // rdi
  unsigned int v22; // edx
  __int16 v23; // r8
  __int16 v24; // ax
  __int64 v25; // r9
  volatile signed __int32 *v26; // rdi
  __int64 *v27; // r8
  bool v28; // si
  volatile signed __int32 *v29; // rdi
  volatile signed __int32 *v30; // rdi
  bool v31; // [rsp+40h] [rbp-49h] BYREF
  __int128 v32; // [rsp+48h] [rbp-41h] BYREF
  __int128 v33; // [rsp+58h] [rbp-31h] BYREF
  __int64 v34; // [rsp+68h] [rbp-21h] BYREF
  PVOID P; // [rsp+70h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-11h] BYREF
  char v37; // [rsp+E8h] [rbp+5Fh] BYREF

  v32 = 0;
  v10 = appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(a2, a3, 0);
  if ( v10 < 0 )
  {
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::ParseRunVirtualRegistry() - Failed to get sid from pid: %d. Error: %d",
      a2,
      v10);
    return 0;
  }
  v37 = 0;
  if ( !RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetRegistryInfo(
          a4,
          (__int64)&v32,
          a3,
          &v37) )
  {
    v12 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( !*((_QWORD *)&v32 + 1) )
      return 0;
LABEL_31:
    if ( !_InterlockedDecrement(v12 + 2) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 0;
  }
  v13 = (__int64 *)v32;
  v14 = *(_QWORD *)(a1 + 56);
  v33 = 0;
  v15 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          v14,
          (const UNICODE_STRING *)v32,
          (__int64 *)&v33);
  if ( v15 < 0 )
  {
    v16 = *(_DWORD *)v13 >> 1;
    if ( v16 > 0xFFFF )
      v17 = -1;
    else
      v17 = *(_DWORD *)v13 >> 1;
    v18 = 0;
    v19 = 0;
    if ( v16 <= 0xFFFF )
      v18 = v17;
    if ( v18 )
      v19 = v13[1];
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::ParseRunVirtualRegistry() - Failed to find package, %s. Error: %d",
      v19,
      v15);
    goto LABEL_26;
  }
  v20 = a6;
  v21 = a5;
  if ( !ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          *(_QWORD *)(a1 + 56),
          (_QWORD **)&v33,
          a3,
          a2,
          a4,
          a5,
          a6) )
  {
    v22 = *(_DWORD *)*v21 >> 1;
    if ( v22 > 0xFFFF )
      v23 = -1;
    else
      v23 = *(_DWORD *)*v21 >> 1;
    v24 = 0;
    if ( v22 <= 0xFFFF )
      v24 = v23;
    if ( v24 )
      v25 = (*v21)[1];
    else
      v25 = 0;
    LogWrite(1, 0, L"VirtualEnvironmentManager::ParseRunVirtualRegistry() - Package %s is not published", v25);
LABEL_26:
    v26 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL)) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        if ( !_InterlockedDecrement(v26 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 16LL))(v26);
      }
    }
    v12 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( !*((_QWORD *)&v32 + 1) )
      return 0;
    goto LABEL_31;
  }
  v31 = 0;
  v34 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( *v20 )
  {
    v27 = &v34;
  }
  else
  {
    v27 = *v21;
    v13 = &v34;
  }
  v28 = (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
               *(_QWORD *)(a1 + 56),
               (__int64)v13,
               (__int64)v27,
               &v31) >= 0
     && v31 == v37;
  if ( P )
    ExFreePoolWithTag(P, 0);
  v29 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      if ( !_InterlockedDecrement(v29 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
    }
  }
  v30 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      if ( !_InterlockedDecrement(v30 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  return v28;
}

```

## disassembly

```asm
0x180018b9c  push    rbp
0x180018b9e  push    rbx
0x180018b9f  push    rsi
0x180018ba0  push    rdi
0x180018ba1  push    r12
0x180018ba3  push    r13
0x180018ba5  push    r14
0x180018ba7  push    r15
0x180018ba9  lea     rbp, [rsp-0Fh]
0x180018bae  sub     rsp, 98h
0x180018bb5  mov     r12, r8
0x180018bb8  mov     r15d, edx
0x180018bbb  mov     rsi, rcx
0x180018bbe  xorps   xmm0, xmm0
0x180018bc1  mov     ecx, edx
0x180018bc3  xor     r8d, r8d
0x180018bc6  mov     rdx, r12
0x180018bc9  mov     r13, r9
0x180018bcc  movdqu  [rbp+47h+var_88], xmm0
0x180018bd1  call    ??$SidFromPid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)
0x180018bd6  xor     r14d, r14d
0x180018bd9  test    eax, eax
0x180018bdb  jns     short loc_180018BFC
0x180018bdd  xor     edx, edx
0x180018bdf  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180018be3  mov     r9d, r15d
0x180018be6  lea     r8, aVirtualenviron_27; "VirtualEnvironmentManager::ParseRunVirt"...
0x180018bed  lea     ecx, [rdx+1]
0x180018bf0  call    LogWrite
0x180018bf5  xor     al, al
0x180018bf7  jmp     loc_180018E7E
0x180018bfc  lea     r9, [rbp+47h+arg_8]
0x180018c00  mov     [rbp+47h+arg_8], r14b
0x180018c04  mov     r8, r12
0x180018c07  lea     rdx, [rbp+47h+var_88]
0x180018c0b  mov     rcx, r13
0x180018c0e  call    ?GetRegistryInfo@?$RunVirtualInfoStore@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEA_N@Z; RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetRegistryInfo(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)
0x180018c13  test    al, al
0x180018c15  jnz     short loc_180018C28
0x180018c17  mov     rdi, qword ptr [rbp+47h+var_88+8]
0x180018c1b  test    rdi, rdi
0x180018c1e  jz      short loc_180018BF5
0x180018c20  or      ebx, 0FFFFFFFFh
0x180018c23  jmp     loc_180018D50
0x180018c28  mov     rbx, qword ptr [rbp+47h+var_88]
0x180018c2c  lea     r8, [rbp+47h+var_78]
0x180018c30  mov     rcx, [rsi+38h]
0x180018c34  xorps   xmm0, xmm0
0x180018c37  mov     rdx, rbx
0x180018c3a  movdqu  [rbp+47h+var_78], xmm0
0x180018c3f  call    ??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180018c44  mov     r10d, eax
0x180018c47  test    eax, eax
0x180018c49  jns     short loc_180018C8D
0x180018c4b  mov     edx, [rbx]
0x180018c4d  mov     ecx, 0FFFFh
0x180018c52  shr     edx, 1
0x180018c54  cmp     edx, ecx
0x180018c56  ja      short loc_180018C5E
0x180018c58  movzx   r8d, dx
0x180018c5c  jmp     short loc_180018C61
0x180018c5e  mov     r8d, ecx
0x180018c61  mov     eax, r14d
0x180018c64  mov     r9, r14
0x180018c67  cmovbe  ax, r8w
0x180018c6c  test    ax, ax
0x180018c6f  jz      short loc_180018C75
0x180018c71  mov     r9, [rbx+8]
0x180018c75  xor     edx, edx
0x180018c77  mov     dword ptr [rsp+0D0h+var_B0], r10d
0x180018c7c  lea     r8, aVirtualenviron_5; "VirtualEnvironmentManager::ParseRunVirt"...
0x180018c83  lea     ecx, [rdx+1]
0x180018c86  call    LogWrite
0x180018c8b  jmp     short loc_180018D03
0x180018c8d  mov     r14, [rbp+47h+arg_28]
0x180018c91  lea     rdx, [rbp+47h+var_78]
0x180018c95  mov     rdi, [rbp+47h+arg_20]
0x180018c99  mov     r9d, r15d
0x180018c9c  mov     rcx, [rsi+38h]
0x180018ca0  mov     r8, r12
0x180018ca3  mov     [rsp+0D0h+var_A0], r14
0x180018ca8  mov     [rsp+0D0h+var_A8], rdi
0x180018cad  mov     [rsp+0D0h+var_B0], r13
0x180018cb2  call    ??$IsPackagePublished@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K1AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@2@AEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,bool &)
0x180018cb7  xor     r15d, r15d
0x180018cba  test    al, al
0x180018cbc  jnz     loc_180018D91
0x180018cc2  mov     r9, [rdi]
0x180018cc5  mov     ecx, 0FFFFh
0x180018cca  mov     edx, [r9]
0x180018ccd  shr     edx, 1
0x180018ccf  cmp     edx, ecx
0x180018cd1  ja      short loc_180018CD9
0x180018cd3  movzx   r8d, dx
0x180018cd7  jmp     short loc_180018CDC
0x180018cd9  mov     r8d, ecx
0x180018cdc  mov     eax, r15d
0x180018cdf  cmovbe  ax, r8w
0x180018ce4  test    ax, ax
0x180018ce7  jnz     short loc_180018CEE
0x180018ce9  mov     r9, r15
0x180018cec  jmp     short loc_180018CF2
0x180018cee  mov     r9, [r9+8]
0x180018cf2  xor     edx, edx
0x180018cf4  lea     r8, aVirtualenviron_15; "VirtualEnvironmentManager::ParseRunVirt"...
0x180018cfb  lea     ecx, [rdx+1]
0x180018cfe  call    LogWrite
0x180018d03  mov     rdi, qword ptr [rbp+47h+var_78+8]
0x180018d07  or      ebx, 0FFFFFFFFh
0x180018d0a  test    rdi, rdi
0x180018d0d  jz      short loc_180018D43
0x180018d0f  mov     eax, ebx
0x180018d11  lock xadd [rdi+8], eax
0x180018d16  add     eax, ebx
0x180018d18  jnz     short loc_180018D43
0x180018d1a  mov     rax, [rdi]
0x180018d1d  mov     rcx, rdi
0x180018d20  mov     rax, [rax+8]
0x180018d24  call    _guard_dispatch_icall
0x180018d29  mov     eax, ebx
0x180018d2b  lock xadd [rdi+0Ch], eax
0x180018d30  add     eax, ebx
0x180018d32  jnz     short loc_180018D43
0x180018d34  mov     rax, [rdi]
0x180018d37  mov     rcx, rdi
0x180018d3a  mov     rax, [rax+10h]
0x180018d3e  call    _guard_dispatch_icall
0x180018d43  mov     rdi, qword ptr [rbp+47h+var_88+8]
0x180018d47  test    rdi, rdi
0x180018d4a  jz      loc_180018BF5
0x180018d50  mov     eax, ebx
0x180018d52  lock xadd [rdi+8], eax
0x180018d57  add     eax, ebx
0x180018d59  jnz     loc_180018BF5
0x180018d5f  mov     rax, [rdi]
0x180018d62  mov     rcx, rdi
0x180018d65  mov     rax, [rax+8]
0x180018d69  call    _guard_dispatch_icall
0x180018d6e  mov     eax, ebx
0x180018d70  lock xadd [rdi+0Ch], eax
0x180018d75  add     eax, ebx
0x180018d77  jnz     loc_180018BF5
0x180018d7d  mov     rax, [rdi]
0x180018d80  mov     rcx, rdi
0x180018d83  mov     rax, [rax+10h]
0x180018d87  call    _guard_dispatch_icall
0x180018d8c  jmp     loc_180018BF5
0x180018d91  xor     edx, edx; SourceString
0x180018d93  mov     [rbp+47h+var_90], r15b
0x180018d97  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180018d9b  mov     [rbp+47h+var_68], r15
0x180018d9f  mov     [rbp+47h+P], r15
0x180018da3  call    cs:__imp_RtlInitUnicodeString
0x180018daa  nop     dword ptr [rax+rax+00h]
0x180018daf  mov     rcx, [rsi+38h]
0x180018db3  cmp     [r14], r15b
0x180018db6  jz      short loc_180018DBE
0x180018db8  lea     r8, [rbp+47h+var_68]
0x180018dbc  jmp     short loc_180018DC5
0x180018dbe  mov     r8, [rdi]
0x180018dc1  lea     rbx, [rbp+47h+var_68]
0x180018dc5  lea     r9, [rbp+47h+var_90]
0x180018dc9  mov     rdx, rbx
0x180018dcc  call    ??$IsPublishedGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)
0x180018dd1  test    eax, eax
0x180018dd3  js      short loc_180018DE4
0x180018dd5  mov     al, [rbp+47h+arg_8]
0x180018dd8  cmp     [rbp+47h+var_90], al
0x180018ddb  jnz     short loc_180018DE4
0x180018ddd  mov     esi, 1
0x180018de2  jmp     short loc_180018DE7
0x180018de4  mov     sil, r15b
0x180018de7  mov     rcx, [rbp+47h+P]; P
0x180018deb  test    rcx, rcx
0x180018dee  jz      short loc_180018DFE
0x180018df0  xor     edx, edx; Tag
0x180018df2  call    cs:__imp_ExFreePoolWithTag
0x180018df9  nop     dword ptr [rax+rax+00h]
0x180018dfe  mov     rdi, qword ptr [rbp+47h+var_78+8]
0x180018e02  or      ebx, 0FFFFFFFFh
0x180018e05  test    rdi, rdi
0x180018e08  jz      short loc_180018E3E
0x180018e0a  mov     eax, ebx
0x180018e0c  lock xadd [rdi+8], eax
0x180018e11  add     eax, ebx
0x180018e13  jnz     short loc_180018E3E
0x180018e15  mov     rax, [rdi]
0x180018e18  mov     rcx, rdi
0x180018e1b  mov     rax, [rax+8]
0x180018e1f  call    _guard_dispatch_icall
0x180018e24  mov     eax, ebx
0x180018e26  lock xadd [rdi+0Ch], eax
0x180018e2b  add     eax, ebx
0x180018e2d  jnz     short loc_180018E3E
0x180018e2f  mov     rax, [rdi]
0x180018e32  mov     rcx, rdi
0x180018e35  mov     rax, [rax+10h]
0x180018e39  call    _guard_dispatch_icall
0x180018e3e  mov     rdi, qword ptr [rbp+47h+var_88+8]
0x180018e42  test    rdi, rdi
0x180018e45  jz      short loc_180018E7B
0x180018e47  mov     eax, ebx
0x180018e49  lock xadd [rdi+8], eax
0x180018e4e  add     eax, ebx
0x180018e50  jnz     short loc_180018E7B
0x180018e52  mov     rax, [rdi]
0x180018e55  mov     rcx, rdi
0x180018e58  mov     rax, [rax+8]
0x180018e5c  call    _guard_dispatch_icall
0x180018e61  mov     eax, ebx
0x180018e63  lock xadd [rdi+0Ch], eax
0x180018e68  add     eax, ebx
0x180018e6a  jnz     short loc_180018E7B
0x180018e6c  mov     rax, [rdi]
0x180018e6f  mov     rcx, rdi
0x180018e72  mov     rax, [rax+10h]
0x180018e76  call    _guard_dispatch_icall
0x180018e7b  mov     al, sil
0x180018e7e  add     rsp, 98h
0x180018e85  pop     r15
0x180018e87  pop     r14
0x180018e89  pop     r13
0x180018e8b  pop     r12
0x180018e8d  pop     rdi
0x180018e8e  pop     rsi
0x180018e8f  pop     rbx
0x180018e90  pop     rbp
0x180018e91  retn
```
