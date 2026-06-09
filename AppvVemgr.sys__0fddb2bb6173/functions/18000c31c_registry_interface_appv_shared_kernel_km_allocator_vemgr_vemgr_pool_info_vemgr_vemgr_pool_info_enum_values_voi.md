# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000c31c`
- end: `0x18000c5eb`
- name: `?enum_values@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000f718`
- `0x180019014`

## callees

- `0x180003f50`
- `0x18000a9e4`
- `0x18000c31c`
- `0x18000e588`
- `0x18000e8d4`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000c3f6`
- `ntoskrnl!ExAllocatePool2` at `0x18000c3f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c379`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c518`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c57e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c5d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c379`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c518`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c57e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c5d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c41a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c41a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18000c3b0`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18000c4b8`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18000c3b0`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18000c4b8`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(
        HANDLE KeyHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  ULONG v8; // r12d
  ULONG v9; // r15d
  _DWORD *v10; // rsi
  NTSTATUS v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  volatile signed __int32 *v14; // rbx
  __int64 Pool2; // rax
  _QWORD *v16; // rbx
  __int64 v17; // r9
  int v18; // r14d
  ULONG Length[2]; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h]
  __int128 v21; // [rsp+40h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+48h] BYREF

  if ( !KeyHandle )
    return 3221225485LL;
  *(_QWORD *)Length = 0;
  P = 0;
  ResultLength = 0;
  v21 = 0;
  v7 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
         Length,
         1040,
         a3,
         a4);
  if ( v7 < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v7;
  }
  v8 = Length[0];
  v9 = 0;
  v10 = P;
  v11 = ZwEnumerateValueKey(KeyHandle, 0, KeyValueBasicInformation, P, Length[0], &ResultLength);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
  while ( 1 )
  {
    v18 = v11;
    if ( v11 == -2147483622 )
    {
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
      return 0;
    }
    if ( v11 == -2147483643 || v11 == -1073741789 )
    {
      appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
        Length,
        ResultLength,
        v12,
        v13);
      v10 = P;
      v8 = Length[0];
      goto LABEL_20;
    }
    if ( v11 < 0 )
    {
      if ( v14 )
      {
LABEL_37:
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
      return (unsigned int)v18;
    }
    Pool2 = ExAllocatePool2(64, 32, 1715758931);
    v16 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = 0;
      *(_QWORD *)(Pool2 + 8) = 0;
      RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
    }
    else
    {
      v16 = 0;
    }
    kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
      &v21,
      v16);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
    if ( !(_QWORD)v21 )
      break;
    if ( !*((_QWORD *)&v21 + 1) )
      goto LABEL_33;
    if ( !*(_DWORD *)(*((_QWORD *)&v21 + 1) + 8LL) )
      break;
    v18 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
            v21,
            v10 + 3,
            (unsigned __int16)(v10[2] >> 1),
            v17);
    if ( v18 < 0 )
      goto LABEL_37;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
      a2,
      &v21);
    ++v9;
LABEL_20:
    v11 = ZwEnumerateValueKey(KeyHandle, v9, KeyValueBasicInformation, v10, v8, &ResultLength);
  }
  if ( *((_QWORD *)&v21 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_33:
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return 3221225626LL;
}

```

## disassembly

```asm
0x18000c31c  push    rbp
0x18000c31e  push    rbx
0x18000c31f  push    rsi
0x18000c320  push    rdi
0x18000c321  push    r12
0x18000c323  push    r13
0x18000c325  push    r14
0x18000c327  push    r15
0x18000c329  mov     rbp, rsp
0x18000c32c  sub     rsp, 58h
0x18000c330  xor     esi, esi
0x18000c332  mov     r13, rdx
0x18000c335  mov     rdi, rcx
0x18000c338  test    rcx, rcx
0x18000c33b  jnz     short loc_18000C347
0x18000c33d  mov     eax, 0C000000Dh
0x18000c342  jmp     loc_18000C526
0x18000c347  xorps   xmm0, xmm0
0x18000c34a  mov     qword ptr [rbp+var_28], rsi
0x18000c34e  mov     edx, 410h
0x18000c353  mov     [rbp+P], rsi
0x18000c357  lea     rcx, [rbp+var_28]
0x18000c35b  mov     [rbp+arg_0], esi
0x18000c35e  movdqu  [rbp+var_18], xmm0
0x18000c363  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000c368  mov     ebx, eax
0x18000c36a  test    eax, eax
0x18000c36c  jns     short loc_18000C38C
0x18000c36e  mov     rcx, [rbp+P]; P
0x18000c372  test    rcx, rcx
0x18000c375  jz      short loc_18000C385
0x18000c377  xor     edx, edx; Tag
0x18000c379  call    cs:__imp_ExFreePoolWithTag
0x18000c380  nop     dword ptr [rax+rax+00h]
0x18000c385  mov     eax, ebx
0x18000c387  jmp     loc_18000C526
0x18000c38c  mov     r12d, [rbp+var_28]
0x18000c390  lea     rax, [rbp+arg_0]
0x18000c394  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000c399  mov     r15d, esi
0x18000c39c  mov     rsi, [rbp+P]
0x18000c3a0  xor     r8d, r8d; KeyValueInformationClass
0x18000c3a3  mov     r9, rsi; KeyValueInformation
0x18000c3a6  mov     [rsp+58h+Length], r12d; Length
0x18000c3ab  xor     edx, edx; Index
0x18000c3ad  mov     rcx, rdi; KeyHandle
0x18000c3b0  call    cs:__imp_ZwEnumerateValueKey
0x18000c3b7  nop     dword ptr [rax+rax+00h]
0x18000c3bc  mov     rbx, qword ptr [rbp+var_18+8]
0x18000c3c0  jmp     loc_18000C4C4
0x18000c3c5  cmp     r14d, 80000005h
0x18000c3cc  jz      loc_18000C48A
0x18000c3d2  cmp     r14d, 0C0000023h
0x18000c3d9  jz      loc_18000C48A
0x18000c3df  test    r14d, r14d
0x18000c3e2  js      loc_18000C591
0x18000c3e8  mov     edx, 20h ; ' '
0x18000c3ed  mov     r8d, 66446753h
0x18000c3f3  lea     ecx, [rdx+20h]
0x18000c3f6  call    cs:__imp_ExAllocatePool2
0x18000c3fd  nop     dword ptr [rax+rax+00h]
0x18000c402  xor     r14d, r14d
0x18000c405  mov     rbx, rax
0x18000c408  test    rax, rax
0x18000c40b  jz      short loc_18000C428
0x18000c40d  lea     rcx, [rax+10h]; DestinationString
0x18000c411  mov     [rax], r14
0x18000c414  xor     edx, edx; SourceString
0x18000c416  mov     [rax+8], r14
0x18000c41a  call    cs:__imp_RtlInitUnicodeString
0x18000c421  nop     dword ptr [rax+rax+00h]
0x18000c426  jmp     short loc_18000C42B
0x18000c428  mov     rbx, r14
0x18000c42b  mov     rdx, rbx
0x18000c42e  lea     rcx, [rbp+var_18]
0x18000c432  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000c437  mov     rcx, qword ptr [rbp+var_18]
0x18000c43b  mov     rbx, qword ptr [rbp+var_18+8]
0x18000c43f  test    rcx, rcx
0x18000c442  jz      loc_18000C538
0x18000c448  test    rbx, rbx
0x18000c44b  jz      loc_18000C574
0x18000c451  mov     eax, [rbx+8]
0x18000c454  test    eax, eax
0x18000c456  jz      loc_18000C538
0x18000c45c  mov     eax, [rsi+8]
0x18000c45f  lea     rdx, [rsi+0Ch]
0x18000c463  shr     eax, 1
0x18000c465  movzx   r8d, ax
0x18000c469  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000c46e  mov     r14d, eax
0x18000c471  test    eax, eax
0x18000c473  js      loc_18000C596
0x18000c479  lea     rdx, [rbp+var_18]
0x18000c47d  mov     rcx, r13
0x18000c480  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000c485  inc     r15d
0x18000c488  jmp     short loc_18000C49E
0x18000c48a  mov     edx, [rbp+arg_0]
0x18000c48d  lea     rcx, [rbp+var_28]
0x18000c491  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000c496  mov     rsi, [rbp+P]
0x18000c49a  mov     r12d, [rbp+var_28]
0x18000c49e  lea     rax, [rbp+arg_0]
0x18000c4a2  mov     r9, rsi; KeyValueInformation
0x18000c4a5  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000c4aa  xor     r8d, r8d; KeyValueInformationClass
0x18000c4ad  mov     edx, r15d; Index
0x18000c4b0  mov     [rsp+58h+Length], r12d; Length
0x18000c4b5  mov     rcx, rdi; KeyHandle
0x18000c4b8  call    cs:__imp_ZwEnumerateValueKey
0x18000c4bf  nop     dword ptr [rax+rax+00h]
0x18000c4c4  mov     r14d, eax
0x18000c4c7  cmp     eax, 8000001Ah
0x18000c4cc  jnz     loc_18000C3C5
0x18000c4d2  test    rbx, rbx
0x18000c4d5  jz      short loc_18000C50E
0x18000c4d7  or      edi, 0FFFFFFFFh
0x18000c4da  mov     eax, edi
0x18000c4dc  lock xadd [rbx+8], eax
0x18000c4e1  add     eax, edi
0x18000c4e3  jnz     short loc_18000C50E
0x18000c4e5  mov     rax, [rbx]
0x18000c4e8  mov     rcx, rbx
0x18000c4eb  mov     rax, [rax+8]
0x18000c4ef  call    _guard_dispatch_icall
0x18000c4f4  mov     eax, edi
0x18000c4f6  lock xadd [rbx+0Ch], eax
0x18000c4fb  add     eax, edi
0x18000c4fd  jnz     short loc_18000C50E
0x18000c4ff  mov     rax, [rbx]
0x18000c502  mov     rcx, rbx
0x18000c505  mov     rax, [rax+10h]
0x18000c509  call    _guard_dispatch_icall
0x18000c50e  test    rsi, rsi
0x18000c511  jz      short loc_18000C524
0x18000c513  xor     edx, edx; Tag
0x18000c515  mov     rcx, rsi; P
0x18000c518  call    cs:__imp_ExFreePoolWithTag
0x18000c51f  nop     dword ptr [rax+rax+00h]
0x18000c524  xor     eax, eax
0x18000c526  add     rsp, 58h
0x18000c52a  pop     r15
0x18000c52c  pop     r14
0x18000c52e  pop     r13
0x18000c530  pop     r12
0x18000c532  pop     rdi
0x18000c533  pop     rsi
0x18000c534  pop     rbx
0x18000c535  pop     rbp
0x18000c536  retn
0x18000c538  test    rbx, rbx
0x18000c53b  jz      short loc_18000C574
0x18000c53d  or      edi, 0FFFFFFFFh
0x18000c540  mov     eax, edi
0x18000c542  lock xadd [rbx+8], eax
0x18000c547  add     eax, edi
0x18000c549  jnz     short loc_18000C574
0x18000c54b  mov     rax, [rbx]
0x18000c54e  mov     rcx, rbx
0x18000c551  mov     rax, [rax+8]
0x18000c555  call    _guard_dispatch_icall
0x18000c55a  mov     eax, edi
0x18000c55c  lock xadd [rbx+0Ch], eax
0x18000c561  add     eax, edi
0x18000c563  jnz     short loc_18000C574
0x18000c565  mov     rax, [rbx]
0x18000c568  mov     rcx, rbx
0x18000c56b  mov     rax, [rax+10h]
0x18000c56f  call    _guard_dispatch_icall
0x18000c574  test    rsi, rsi
0x18000c577  jz      short loc_18000C58A
0x18000c579  xor     edx, edx; Tag
0x18000c57b  mov     rcx, rsi; P
0x18000c57e  call    cs:__imp_ExFreePoolWithTag
0x18000c585  nop     dword ptr [rax+rax+00h]
0x18000c58a  mov     eax, 0C000009Ah
0x18000c58f  jmp     short loc_18000C526
0x18000c591  test    rbx, rbx
0x18000c594  jz      short loc_18000C5CD
0x18000c596  or      edi, 0FFFFFFFFh
0x18000c599  mov     eax, edi
0x18000c59b  lock xadd [rbx+8], eax
0x18000c5a0  add     eax, edi
0x18000c5a2  jnz     short loc_18000C5CD
0x18000c5a4  mov     rax, [rbx]
0x18000c5a7  mov     rcx, rbx
0x18000c5aa  mov     rax, [rax+8]
0x18000c5ae  call    _guard_dispatch_icall
0x18000c5b3  mov     eax, edi
0x18000c5b5  lock xadd [rbx+0Ch], eax
0x18000c5ba  add     eax, edi
0x18000c5bc  jnz     short loc_18000C5CD
0x18000c5be  mov     rax, [rbx]
0x18000c5c1  mov     rcx, rbx
0x18000c5c4  mov     rax, [rax+10h]
0x18000c5c8  call    _guard_dispatch_icall
0x18000c5cd  test    rsi, rsi
0x18000c5d0  jz      short loc_18000C5E3
0x18000c5d2  xor     edx, edx; Tag
0x18000c5d4  mov     rcx, rsi; P
0x18000c5d7  call    cs:__imp_ExFreePoolWithTag
0x18000c5de  nop     dword ptr [rax+rax+00h]
0x18000c5e3  mov     eax, r14d
0x18000c5e6  jmp     loc_18000C526
```
