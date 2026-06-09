# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ExePathStartsWithPackageRoot(ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool &,bool &,bool &)

- ea: `0x180007840`
- end: `0x180007b7f`
- name: `?ExePathStartsWithPackageRoot@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV2345@AEA_N44@Z`
- size: `831`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000da60`
- `0x180018484`

## callees

- `0x180001788`
- `0x180001f78`
- `0x180002cb4`
- `0x180005430`
- `0x180007840`
- `0x180008048`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800079b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800079b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007ab6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180007911`
- `ntoskrnl!RtlInitUnicodeString` at `0x180007911`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000796c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180007a6a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000796c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180007a6a`

## pseudocode

```c
char __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ExePathStartsWithPackageRoot(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        char a5,
        const UNICODE_STRING **a6,
        __int64 a7,
        _BYTE *a8,
        _BYTE *a9,
        _BYTE *a10)
{
  __int64 v14; // r8
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rdi
  const UNICODE_STRING **v18; // rdi
  const UNICODE_STRING *v19; // rsi
  const UNICODE_STRING **v20; // rcx
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  const UNICODE_STRING ***i; // rbx
  const UNICODE_STRING **v24; // rcx
  __int64 v25; // rdx
  PVOID v26; // rcx
  volatile signed __int32 *v27; // rdi
  char v28; // al
  __int128 v29; // [rsp+40h] [rbp-40h] BYREF
  __int128 v30; // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+60h] [rbp-20h] BYREF
  PVOID P; // [rsp+68h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF

  a5 = 0;
  if ( (int)appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(a2, a7, &a5) < 0
    || a5 == 1 )
  {
    return 0;
  }
  v15 = *(_QWORD *)(a1 + 56);
  v29 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              v15,
              a4,
              v14,
              &v29) < 0 )
  {
    v16 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
    if ( *((_QWORD *)&v29 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( !_InterlockedDecrement(v16 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 0;
  }
  a5 = 0;
  v31 = 0;
  P = 0;
  v30 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v18 = (const UNICODE_STRING **)v29;
  *a10 = *(_BYTE *)(v29 + 49);
  if ( !(unsigned __int8)VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParentProcessIsVirtual(
                           a1,
                           a3,
                           (unsigned int)&v30,
                           (unsigned int)&v31,
                           (__int64)&a5) )
    goto LABEL_38;
  v19 = (const UNICODE_STRING *)v30;
  if ( !a5 || RtlCompareUnicodeString((PCUNICODE_STRING)(v30 + 16), *v18 + 1, 1u) )
  {
    for ( i = (const UNICODE_STRING ***)v18[16];
          i != (const UNICODE_STRING ***)(v18 + 13);
          i = (const UNICODE_STRING ***)i[3] )
    {
      if ( !RtlCompareUnicodeString(v19 + 1, **i + 1, 1u) )
      {
        v24 = a6;
        v25 = (__int64)(*i + 1);
        *a6 = **i;
        kernel_std::detail::shared_count::operator=(v24 + 1, v25);
        v26 = P;
        *a8 = 0;
        *a9 = 1;
        if ( v26 )
          ExFreePoolWithTag(v26, 0);
        v27 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
        if ( *((_QWORD *)&v30 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL)) )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
            if ( !_InterlockedDecrement(v27 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 16LL))(v27);
          }
        }
        v22 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
        if ( !*((_QWORD *)&v29 + 1) )
          return 1;
        if ( _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL)) )
          return 1;
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) != 1 )
          return 1;
        goto LABEL_36;
      }
    }
LABEL_38:
    v28 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            *(_QWORD *)(a1 + 56),
            (unsigned int)&v29,
            a7,
            a2,
            a4,
            (__int64)a6,
            (__int64)a8);
    *a9 = v28;
    goto LABEL_13;
  }
  v20 = a6;
  *a6 = *v18;
  kernel_std::detail::shared_count::operator=(v20 + 1, v18 + 1);
  *a8 = 1;
  *a9 = 1;
LABEL_13:
  if ( P )
    ExFreePoolWithTag(P, 0);
  v21 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( !_InterlockedDecrement(v21 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
LABEL_36:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180007840  push    rbp
0x180007842  push    rbx
0x180007843  push    rsi
0x180007844  push    rdi
0x180007845  push    r12
0x180007847  push    r14
0x180007849  push    r15
0x18000784b  mov     rbp, rsp
0x18000784e  sub     rsp, 80h
0x180007855  mov     r14, rcx
0x180007858  mov     r12d, edx
0x18000785b  mov     ecx, edx
0x18000785d  mov     ebx, r8d
0x180007860  mov     rdx, [rbp+arg_30]
0x180007864  lea     r8, [rbp+arg_20]
0x180007868  mov     r15, r9
0x18000786b  mov     [rbp+arg_20], 0
0x18000786f  call    ??$SidFromPid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)
0x180007874  test    eax, eax
0x180007876  js      short loc_1800078DA
0x180007878  cmp     [rbp+arg_20], 1
0x18000787c  jz      short loc_1800078DA
0x18000787e  mov     rcx, [r14+38h]
0x180007882  lea     r9, [rbp+var_40]
0x180007886  xorps   xmm0, xmm0
0x180007889  mov     rdx, r15
0x18000788c  movdqu  [rbp+var_40], xmm0
0x180007891  call    ??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180007896  test    eax, eax
0x180007898  jns     short loc_1800078EF
0x18000789a  mov     rdi, qword ptr [rbp+var_40+8]
0x18000789e  test    rdi, rdi
0x1800078a1  jz      short loc_1800078DA
0x1800078a3  or      ebx, 0FFFFFFFFh
0x1800078a6  mov     eax, ebx
0x1800078a8  lock xadd [rdi+8], eax
0x1800078ad  add     eax, ebx
0x1800078af  jnz     short loc_1800078DA
0x1800078b1  mov     rax, [rdi]
0x1800078b4  mov     rcx, rdi
0x1800078b7  mov     rax, [rax+8]
0x1800078bb  call    _guard_dispatch_icall
0x1800078c0  mov     eax, ebx
0x1800078c2  lock xadd [rdi+0Ch], eax
0x1800078c7  add     eax, ebx
0x1800078c9  jnz     short loc_1800078DA
0x1800078cb  mov     rax, [rdi]
0x1800078ce  mov     rcx, rdi
0x1800078d1  mov     rax, [rax+10h]
0x1800078d5  call    _guard_dispatch_icall
0x1800078da  xor     al, al
0x1800078dc  add     rsp, 80h
0x1800078e3  pop     r15
0x1800078e5  pop     r14
0x1800078e7  pop     r12
0x1800078e9  pop     rdi
0x1800078ea  pop     rsi
0x1800078eb  pop     rbx
0x1800078ec  pop     rbp
0x1800078ed  retn
0x1800078ef  xorps   xmm0, xmm0
0x1800078f2  mov     [rbp+arg_20], 0
0x1800078f6  xor     edx, edx; SourceString
0x1800078f8  mov     [rbp+var_20], 0
0x180007900  lea     rcx, [rbp+DestinationString]; DestinationString
0x180007904  mov     [rbp+P], 0
0x18000790c  movdqu  [rbp+var_30], xmm0
0x180007911  call    cs:__imp_RtlInitUnicodeString
0x180007918  nop     dword ptr [rax+rax+00h]
0x18000791d  mov     rax, [rbp+arg_48]
0x180007924  lea     r9, [rbp+var_20]
0x180007928  mov     rdi, qword ptr [rbp+var_40]
0x18000792c  lea     r8, [rbp+var_30]
0x180007930  mov     edx, ebx
0x180007932  mov     cl, [rdi+31h]
0x180007935  mov     [rax], cl
0x180007937  lea     rax, [rbp+arg_20]
0x18000793b  mov     rcx, r14
0x18000793e  mov     [rsp+80h+var_60], rax
0x180007943  call    ?ParentProcessIsVirtual@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NKAEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEA_N@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParentProcessIsVirtual(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool &)
0x180007948  test    al, al
0x18000794a  jz      loc_180007B46
0x180007950  cmp     [rbp+arg_20], 0
0x180007954  mov     rsi, qword ptr [rbp+var_30]
0x180007958  jz      loc_180007A45
0x18000795e  mov     rdx, [rdi]
0x180007961  lea     rcx, [rsi+10h]; String1
0x180007965  add     rdx, 10h; String2
0x180007969  mov     r8b, 1; CaseInSensitive
0x18000796c  call    cs:__imp_RtlCompareUnicodeString
0x180007973  nop     dword ptr [rax+rax+00h]
0x180007978  test    eax, eax
0x18000797a  jnz     loc_180007A45
0x180007980  mov     rcx, [rbp+arg_28]
0x180007984  lea     rdx, [rdi+8]
0x180007988  mov     rax, [rdi]
0x18000798b  mov     [rcx], rax
0x18000798e  add     rcx, 8
0x180007992  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180007997  mov     rax, [rbp+arg_38]
0x18000799b  mov     byte ptr [rax], 1
0x18000799e  mov     rax, [rbp+arg_40]
0x1800079a5  mov     byte ptr [rax], 1
0x1800079a8  mov     rcx, [rbp+P]; P
0x1800079ac  test    rcx, rcx
0x1800079af  jz      short loc_1800079BF
0x1800079b1  xor     edx, edx; Tag
0x1800079b3  call    cs:__imp_ExFreePoolWithTag
0x1800079ba  nop     dword ptr [rax+rax+00h]
0x1800079bf  mov     rdi, qword ptr [rbp+var_30+8]
0x1800079c3  or      ebx, 0FFFFFFFFh
0x1800079c6  test    rdi, rdi
0x1800079c9  jz      short loc_1800079FF
0x1800079cb  mov     eax, ebx
0x1800079cd  lock xadd [rdi+8], eax
0x1800079d2  add     eax, ebx
0x1800079d4  jnz     short loc_1800079FF
0x1800079d6  mov     rax, [rdi]
0x1800079d9  mov     rcx, rdi
0x1800079dc  mov     rax, [rax+8]
0x1800079e0  call    _guard_dispatch_icall
0x1800079e5  mov     eax, ebx
0x1800079e7  lock xadd [rdi+0Ch], eax
0x1800079ec  add     eax, ebx
0x1800079ee  jnz     short loc_1800079FF
0x1800079f0  mov     rax, [rdi]
0x1800079f3  mov     rcx, rdi
0x1800079f6  mov     rax, [rax+10h]
0x1800079fa  call    _guard_dispatch_icall
0x1800079ff  mov     rdi, qword ptr [rbp+var_40+8]
0x180007a03  test    rdi, rdi
0x180007a06  jz      loc_180007B3F
0x180007a0c  mov     eax, ebx
0x180007a0e  lock xadd [rdi+8], eax
0x180007a13  add     eax, ebx
0x180007a15  jnz     loc_180007B3F
0x180007a1b  mov     rax, [rdi]
0x180007a1e  mov     rcx, rdi
0x180007a21  mov     rax, [rax+8]
0x180007a25  call    _guard_dispatch_icall
0x180007a2a  mov     eax, ebx
0x180007a2c  lock xadd [rdi+0Ch], eax
0x180007a31  add     eax, ebx
0x180007a33  jnz     loc_180007B3F
0x180007a39  mov     rax, [rdi]
0x180007a3c  mov     rax, [rax+10h]
0x180007a40  jmp     loc_180007B37
0x180007a45  mov     rbx, [rdi+80h]
0x180007a4c  lea     rax, [rdi+68h]
0x180007a50  cmp     rbx, rax
0x180007a53  jz      loc_180007B46
0x180007a59  mov     rax, [rbx]
0x180007a5c  lea     rcx, [rsi+10h]; String1
0x180007a60  mov     r8b, 1; CaseInSensitive
0x180007a63  mov     rdx, [rax]
0x180007a66  add     rdx, 10h; String2
0x180007a6a  call    cs:__imp_RtlCompareUnicodeString
0x180007a71  nop     dword ptr [rax+rax+00h]
0x180007a76  test    eax, eax
0x180007a78  jz      short loc_180007A80
0x180007a7a  mov     rbx, [rbx+18h]
0x180007a7e  jmp     short loc_180007A4C
0x180007a80  mov     rdx, [rbx]
0x180007a83  mov     rcx, [rbp+arg_28]
0x180007a87  mov     rax, [rdx]
0x180007a8a  add     rdx, 8
0x180007a8e  mov     [rcx], rax
0x180007a91  add     rcx, 8
0x180007a95  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180007a9a  mov     rax, [rbp+arg_38]
0x180007a9e  mov     rcx, [rbp+P]; P
0x180007aa2  mov     byte ptr [rax], 0
0x180007aa5  mov     rax, [rbp+arg_40]
0x180007aac  mov     byte ptr [rax], 1
0x180007aaf  test    rcx, rcx
0x180007ab2  jz      short loc_180007AC2
0x180007ab4  xor     edx, edx; Tag
0x180007ab6  call    cs:__imp_ExFreePoolWithTag
0x180007abd  nop     dword ptr [rax+rax+00h]
0x180007ac2  mov     rdi, qword ptr [rbp+var_30+8]
0x180007ac6  or      ebx, 0FFFFFFFFh
0x180007ac9  test    rdi, rdi
0x180007acc  jz      short loc_180007B02
0x180007ace  mov     eax, ebx
0x180007ad0  lock xadd [rdi+8], eax
0x180007ad5  add     eax, ebx
0x180007ad7  jnz     short loc_180007B02
0x180007ad9  mov     rax, [rdi]
0x180007adc  mov     rcx, rdi
0x180007adf  mov     rax, [rax+8]
0x180007ae3  call    _guard_dispatch_icall
0x180007ae8  mov     eax, ebx
0x180007aea  lock xadd [rdi+0Ch], eax
0x180007aef  add     eax, ebx
0x180007af1  jnz     short loc_180007B02
0x180007af3  mov     rax, [rdi]
0x180007af6  mov     rcx, rdi
0x180007af9  mov     rax, [rax+10h]
0x180007afd  call    _guard_dispatch_icall
0x180007b02  mov     rdi, qword ptr [rbp+var_40+8]
0x180007b06  test    rdi, rdi
0x180007b09  jz      short loc_180007B3F
0x180007b0b  mov     eax, ebx
0x180007b0d  lock xadd [rdi+8], eax
0x180007b12  add     eax, ebx
0x180007b14  jnz     short loc_180007B3F
0x180007b16  mov     rax, [rdi]
0x180007b19  mov     rcx, rdi
0x180007b1c  mov     rax, [rax+8]
0x180007b20  call    _guard_dispatch_icall
0x180007b25  mov     edx, ebx
0x180007b27  lock xadd [rdi+0Ch], edx
0x180007b2c  add     edx, ebx
0x180007b2e  jnz     short loc_180007B3F
0x180007b30  mov     rdx, [rdi]
0x180007b33  mov     rax, [rdx+10h]
0x180007b37  mov     rcx, rdi
0x180007b3a  call    _guard_dispatch_icall
0x180007b3f  mov     al, 1
0x180007b41  jmp     loc_1800078DC
0x180007b46  mov     rax, [rbp+arg_38]
0x180007b4a  lea     rdx, [rbp+var_40]
0x180007b4e  mov     r8, [rbp+arg_30]
0x180007b52  mov     r9d, r12d
0x180007b55  mov     rcx, [r14+38h]
0x180007b59  mov     [rsp+80h+var_50], rax
0x180007b5e  mov     rax, [rbp+arg_28]
0x180007b62  mov     [rsp+80h+var_58], rax
0x180007b67  mov     [rsp+80h+var_60], r15
0x180007b6c  call    ??$IsPackagePublished@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K1AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@2@AEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,bool &)
0x180007b71  mov     rcx, [rbp+arg_40]
0x180007b78  mov     [rcx], al
0x180007b7a  jmp     loc_1800079A8
```
