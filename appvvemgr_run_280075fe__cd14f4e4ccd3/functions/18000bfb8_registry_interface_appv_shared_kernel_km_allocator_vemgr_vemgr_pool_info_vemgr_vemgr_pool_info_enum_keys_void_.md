# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000bfb8`
- end: `0x18000c287`
- name: `?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000c290`
- `0x18000ef74`
- `0x18000f300`
- `0x180013e14`
- `0x180013f40`
- `0x18001a024`
- `0x18001a1f4`

## callees

- `0x180003f50`
- `0x18000a9e4`
- `0x18000bfb8`
- `0x18000e588`
- `0x18000e8d4`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000c092`
- `ntoskrnl!ExAllocatePool2` at `0x18000c092`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c04c`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c154`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c04c`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c154`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c015`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c1b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c21a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c273`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c015`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c1b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c21a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c273`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c0b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c0b6`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
        HANDLE KeyHandle,
        __int64 a2)
{
  int v5; // ebx
  ULONG v6; // r12d
  ULONG v7; // r15d
  _DWORD *v8; // rsi
  NTSTATUS v9; // eax
  volatile signed __int32 *v10; // rbx
  __int64 Pool2; // rax
  __int64 v12; // rbx
  int v13; // r14d
  ULONG Length[2]; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h]
  __int128 v16; // [rsp+40h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+48h] BYREF

  if ( !KeyHandle )
    return 3221225485LL;
  *(_QWORD *)Length = 0;
  P = 0;
  ResultLength = 0;
  v16 = 0;
  v5 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(Length, 1048);
  if ( v5 < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v5;
  }
  v6 = Length[0];
  v7 = 0;
  v8 = P;
  v9 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, P, Length[0], &ResultLength);
  v10 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
  while ( 1 )
  {
    v13 = v9;
    if ( v9 == -2147483622 )
    {
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      return 0;
    }
    if ( v9 == -2147483643 || v9 == -1073741789 )
    {
      appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
        Length,
        ResultLength);
      v8 = P;
      v6 = Length[0];
      goto LABEL_20;
    }
    if ( v9 < 0 )
    {
      if ( v10 )
      {
LABEL_37:
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      return (unsigned int)v13;
    }
    Pool2 = ExAllocatePool2(64, 32, 1715758931);
    v12 = Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = 0;
      *(_QWORD *)(Pool2 + 8) = 0;
      RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
    }
    else
    {
      v12 = 0;
    }
    kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
      &v16,
      v12);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
    if ( !(_QWORD)v16 )
      break;
    if ( !*((_QWORD *)&v16 + 1) )
      goto LABEL_33;
    if ( !*(_DWORD *)(*((_QWORD *)&v16 + 1) + 8LL) )
      break;
    v13 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
            v16,
            v8 + 4,
            (unsigned __int16)(v8[3] >> 1));
    if ( v13 < 0 )
      goto LABEL_37;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
      a2,
      &v16);
    ++v7;
LABEL_20:
    v9 = ZwEnumerateKey(KeyHandle, v7, KeyBasicInformation, v8, v6, &ResultLength);
  }
  if ( *((_QWORD *)&v16 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
LABEL_33:
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return 3221225626LL;
}

```

## disassembly

```asm
0x18000bfb8  push    rbp
0x18000bfba  push    rbx
0x18000bfbb  push    rsi
0x18000bfbc  push    rdi
0x18000bfbd  push    r12
0x18000bfbf  push    r13
0x18000bfc1  push    r14
0x18000bfc3  push    r15
0x18000bfc5  mov     rbp, rsp
0x18000bfc8  sub     rsp, 58h
0x18000bfcc  xor     esi, esi
0x18000bfce  mov     r13, rdx
0x18000bfd1  mov     rdi, rcx
0x18000bfd4  test    rcx, rcx
0x18000bfd7  jnz     short loc_18000BFE3
0x18000bfd9  mov     eax, 0C000000Dh
0x18000bfde  jmp     loc_18000C1C2
0x18000bfe3  xorps   xmm0, xmm0
0x18000bfe6  mov     qword ptr [rbp+var_28], rsi
0x18000bfea  mov     edx, 418h
0x18000bfef  mov     [rbp+P], rsi
0x18000bff3  lea     rcx, [rbp+var_28]
0x18000bff7  mov     [rbp+arg_0], esi
0x18000bffa  movdqu  [rbp+var_18], xmm0
0x18000bfff  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000c004  mov     ebx, eax
0x18000c006  test    eax, eax
0x18000c008  jns     short loc_18000C028
0x18000c00a  mov     rcx, [rbp+P]; P
0x18000c00e  test    rcx, rcx
0x18000c011  jz      short loc_18000C021
0x18000c013  xor     edx, edx; Tag
0x18000c015  call    cs:__imp_ExFreePoolWithTag
0x18000c01c  nop     dword ptr [rax+rax+00h]
0x18000c021  mov     eax, ebx
0x18000c023  jmp     loc_18000C1C2
0x18000c028  mov     r12d, [rbp+var_28]
0x18000c02c  lea     rax, [rbp+arg_0]
0x18000c030  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000c035  mov     r15d, esi
0x18000c038  mov     rsi, [rbp+P]
0x18000c03c  xor     r8d, r8d; KeyInformationClass
0x18000c03f  mov     r9, rsi; KeyInformation
0x18000c042  mov     [rsp+58h+Length], r12d; Length
0x18000c047  xor     edx, edx; Index
0x18000c049  mov     rcx, rdi; KeyHandle
0x18000c04c  call    cs:__imp_ZwEnumerateKey
0x18000c053  nop     dword ptr [rax+rax+00h]
0x18000c058  mov     rbx, qword ptr [rbp+var_18+8]
0x18000c05c  jmp     loc_18000C160
0x18000c061  cmp     r14d, 80000005h
0x18000c068  jz      loc_18000C126
0x18000c06e  cmp     r14d, 0C0000023h
0x18000c075  jz      loc_18000C126
0x18000c07b  test    r14d, r14d
0x18000c07e  js      loc_18000C22D
0x18000c084  mov     edx, 20h ; ' '
0x18000c089  mov     r8d, 66446753h
0x18000c08f  lea     ecx, [rdx+20h]
0x18000c092  call    cs:__imp_ExAllocatePool2
0x18000c099  nop     dword ptr [rax+rax+00h]
0x18000c09e  xor     r14d, r14d
0x18000c0a1  mov     rbx, rax
0x18000c0a4  test    rax, rax
0x18000c0a7  jz      short loc_18000C0C4
0x18000c0a9  lea     rcx, [rax+10h]; DestinationString
0x18000c0ad  mov     [rax], r14
0x18000c0b0  xor     edx, edx; SourceString
0x18000c0b2  mov     [rax+8], r14
0x18000c0b6  call    cs:__imp_RtlInitUnicodeString
0x18000c0bd  nop     dword ptr [rax+rax+00h]
0x18000c0c2  jmp     short loc_18000C0C7
0x18000c0c4  mov     rbx, r14
0x18000c0c7  mov     rdx, rbx
0x18000c0ca  lea     rcx, [rbp+var_18]
0x18000c0ce  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000c0d3  mov     rcx, qword ptr [rbp+var_18]
0x18000c0d7  mov     rbx, qword ptr [rbp+var_18+8]
0x18000c0db  test    rcx, rcx
0x18000c0de  jz      loc_18000C1D4
0x18000c0e4  test    rbx, rbx
0x18000c0e7  jz      loc_18000C210
0x18000c0ed  mov     eax, [rbx+8]
0x18000c0f0  test    eax, eax
0x18000c0f2  jz      loc_18000C1D4
0x18000c0f8  mov     eax, [rsi+0Ch]
0x18000c0fb  lea     rdx, [rsi+10h]
0x18000c0ff  shr     eax, 1
0x18000c101  movzx   r8d, ax
0x18000c105  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000c10a  mov     r14d, eax
0x18000c10d  test    eax, eax
0x18000c10f  js      loc_18000C232
0x18000c115  lea     rdx, [rbp+var_18]
0x18000c119  mov     rcx, r13
0x18000c11c  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000c121  inc     r15d
0x18000c124  jmp     short loc_18000C13A
0x18000c126  mov     edx, [rbp+arg_0]
0x18000c129  lea     rcx, [rbp+var_28]
0x18000c12d  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000c132  mov     rsi, [rbp+P]
0x18000c136  mov     r12d, [rbp+var_28]
0x18000c13a  lea     rax, [rbp+arg_0]
0x18000c13e  mov     r9, rsi; KeyInformation
0x18000c141  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000c146  xor     r8d, r8d; KeyInformationClass
0x18000c149  mov     edx, r15d; Index
0x18000c14c  mov     [rsp+58h+Length], r12d; Length
0x18000c151  mov     rcx, rdi; KeyHandle
0x18000c154  call    cs:__imp_ZwEnumerateKey
0x18000c15b  nop     dword ptr [rax+rax+00h]
0x18000c160  mov     r14d, eax
0x18000c163  cmp     eax, 8000001Ah
0x18000c168  jnz     loc_18000C061
0x18000c16e  test    rbx, rbx
0x18000c171  jz      short loc_18000C1AA
0x18000c173  or      edi, 0FFFFFFFFh
0x18000c176  mov     eax, edi
0x18000c178  lock xadd [rbx+8], eax
0x18000c17d  add     eax, edi
0x18000c17f  jnz     short loc_18000C1AA
0x18000c181  mov     rax, [rbx]
0x18000c184  mov     rcx, rbx
0x18000c187  mov     rax, [rax+8]
0x18000c18b  call    _guard_dispatch_icall
0x18000c190  mov     eax, edi
0x18000c192  lock xadd [rbx+0Ch], eax
0x18000c197  add     eax, edi
0x18000c199  jnz     short loc_18000C1AA
0x18000c19b  mov     rax, [rbx]
0x18000c19e  mov     rcx, rbx
0x18000c1a1  mov     rax, [rax+10h]
0x18000c1a5  call    _guard_dispatch_icall
0x18000c1aa  test    rsi, rsi
0x18000c1ad  jz      short loc_18000C1C0
0x18000c1af  xor     edx, edx; Tag
0x18000c1b1  mov     rcx, rsi; P
0x18000c1b4  call    cs:__imp_ExFreePoolWithTag
0x18000c1bb  nop     dword ptr [rax+rax+00h]
0x18000c1c0  xor     eax, eax
0x18000c1c2  add     rsp, 58h
0x18000c1c6  pop     r15
0x18000c1c8  pop     r14
0x18000c1ca  pop     r13
0x18000c1cc  pop     r12
0x18000c1ce  pop     rdi
0x18000c1cf  pop     rsi
0x18000c1d0  pop     rbx
0x18000c1d1  pop     rbp
0x18000c1d2  retn
0x18000c1d4  test    rbx, rbx
0x18000c1d7  jz      short loc_18000C210
0x18000c1d9  or      edi, 0FFFFFFFFh
0x18000c1dc  mov     eax, edi
0x18000c1de  lock xadd [rbx+8], eax
0x18000c1e3  add     eax, edi
0x18000c1e5  jnz     short loc_18000C210
0x18000c1e7  mov     rax, [rbx]
0x18000c1ea  mov     rcx, rbx
0x18000c1ed  mov     rax, [rax+8]
0x18000c1f1  call    _guard_dispatch_icall
0x18000c1f6  mov     eax, edi
0x18000c1f8  lock xadd [rbx+0Ch], eax
0x18000c1fd  add     eax, edi
0x18000c1ff  jnz     short loc_18000C210
0x18000c201  mov     rax, [rbx]
0x18000c204  mov     rcx, rbx
0x18000c207  mov     rax, [rax+10h]
0x18000c20b  call    _guard_dispatch_icall
0x18000c210  test    rsi, rsi
0x18000c213  jz      short loc_18000C226
0x18000c215  xor     edx, edx; Tag
0x18000c217  mov     rcx, rsi; P
0x18000c21a  call    cs:__imp_ExFreePoolWithTag
0x18000c221  nop     dword ptr [rax+rax+00h]
0x18000c226  mov     eax, 0C000009Ah
0x18000c22b  jmp     short loc_18000C1C2
0x18000c22d  test    rbx, rbx
0x18000c230  jz      short loc_18000C269
0x18000c232  or      edi, 0FFFFFFFFh
0x18000c235  mov     eax, edi
0x18000c237  lock xadd [rbx+8], eax
0x18000c23c  add     eax, edi
0x18000c23e  jnz     short loc_18000C269
0x18000c240  mov     rax, [rbx]
0x18000c243  mov     rcx, rbx
0x18000c246  mov     rax, [rax+8]
0x18000c24a  call    _guard_dispatch_icall
0x18000c24f  mov     eax, edi
0x18000c251  lock xadd [rbx+0Ch], eax
0x18000c256  add     eax, edi
0x18000c258  jnz     short loc_18000C269
0x18000c25a  mov     rax, [rbx]
0x18000c25d  mov     rcx, rbx
0x18000c260  mov     rax, [rax+10h]
0x18000c264  call    _guard_dispatch_icall
0x18000c269  test    rsi, rsi
0x18000c26c  jz      short loc_18000C27F
0x18000c26e  xor     edx, edx; Tag
0x18000c270  mov     rcx, rsi; P
0x18000c273  call    cs:__imp_ExFreePoolWithTag
0x18000c27a  nop     dword ptr [rax+rax+00h]
0x18000c27f  mov     eax, r14d
0x18000c282  jmp     loc_18000C1C2
```
