# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000c9a8`
- end: `0x18000ce09`
- name: `?generate_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f718`
- `0x1800153c8`

## callees

- `0x180003f50`
- `0x180005430`
- `0x18000acbc`
- `0x18000c5f4`
- `0x18000c9a8`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000cb25`
- `ntoskrnl!ExAllocatePool2` at `0x18000cbcc`
- `ntoskrnl!ExAllocatePool2` at `0x18000cb25`
- `ntoskrnl!ExAllocatePool2` at `0x18000cbcc`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000cb48`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000cbf0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000cb48`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000cbf0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000ca4d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000cab0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000ca4d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000cab0`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(
        __int64 a1,
        __int64 a2)
{
  unsigned int **v2; // rax
  unsigned int **v3; // r12
  unsigned int **v6; // rdi
  unsigned int **v7; // rax
  unsigned int **v8; // rbx
  volatile signed __int32 *v9; // r14
  __int64 v10; // r15
  volatile signed __int32 *v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  __int64 Pool2; // rax
  _QWORD *v17; // rbx
  __int64 v18; // r8
  __int64 v19; // r9
  __int128 v21; // [rsp+20h] [rbp-20h] BYREF
  __int128 v22; // [rsp+30h] [rbp-10h] BYREF
  unsigned int **v23; // [rsp+80h] [rbp+40h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  v2 = *(unsigned int ***)(a2 + 32);
  v3 = (unsigned int **)(a2 + 8);
  while ( v2 != v3 )
  {
    v23 = v2;
    v2 = (unsigned int **)*appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                             (_DWORD *)a2,
                             &v24,
                             (__int64)&v23);
  }
  v6 = *(unsigned int ***)(a1 + 32);
  v7 = (unsigned int **)(a1 + 8);
  v23 = (unsigned int **)(a1 + 8);
  while ( 2 )
  {
    if ( v6 == v7 )
      return 0;
    v8 = *(unsigned int ***)(a2 + 32);
    v22 = 0;
    v9 = 0;
    v10 = 0;
    v21 = 0;
    v11 = 0;
    while ( v8 != v3 )
    {
      if ( (_QWORD)v21 && v11 && *((_DWORD *)v11 + 2)
        || RtlCompareUnicodeString((PCUNICODE_STRING)*v6 + 1, (PCUNICODE_STRING)*v8 + 1, 1u) )
      {
        goto LABEL_17;
      }
      *(_QWORD *)&v21 = *v8;
      kernel_std::detail::shared_count::operator=(
        (volatile signed __int32 **)&v21 + 1,
        (volatile signed __int32 **)v8 + 1);
      if ( !v9 || !*((_DWORD *)v9 + 2) )
      {
        v11 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
LABEL_17:
        if ( v10 && v9 && *((_DWORD *)v9 + 2) )
          goto LABEL_25;
        goto LABEL_20;
      }
      v11 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
      if ( v10 )
        break;
LABEL_20:
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)*v6 + 7, (PCUNICODE_STRING)*v8 + 1, 1u) )
      {
        *(_QWORD *)&v22 = *v8;
        kernel_std::detail::shared_count::operator=(
          (volatile signed __int32 **)&v22 + 1,
          (volatile signed __int32 **)v8 + 1);
        if ( v11 && *((_DWORD *)v11 + 2) && (_QWORD)v21 )
        {
          v9 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
          v10 = v22;
          break;
        }
        v9 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
        v10 = v22;
      }
LABEL_25:
      v8 = (unsigned int **)v8[3];
    }
    if ( (_QWORD)v21 && v11 && *((_DWORD *)v11 + 2) )
    {
LABEL_38:
      if ( v10 && v9 && *((_DWORD *)v9 + 2) )
        goto LABEL_49;
      Pool2 = ExAllocatePool2(64, 32, 1715758931);
      v17 = (_QWORD *)Pool2;
      if ( Pool2 )
      {
        *(_QWORD *)Pool2 = 0;
        *(_QWORD *)(Pool2 + 8) = 0;
        RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
      }
      else
      {
        v17 = 0;
      }
      kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        &v22,
        v17);
      v9 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
      if ( (_QWORD)v22 )
      {
        if ( !*((_QWORD *)&v22 + 1) )
        {
LABEL_71:
          if ( v11 )
          {
            if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
              if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          return 3221225626LL;
        }
        if ( *(_DWORD *)(*((_QWORD *)&v22 + 1) + 8LL) )
        {
          v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
                  v22,
                  *v6 + 24,
                  v18,
                  v19);
          if ( v15 < 0 )
            goto LABEL_59;
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
            a2,
            &v22);
LABEL_49:
          if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
            if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
          }
          v6 = (unsigned int **)v6[3];
          v7 = v23;
          continue;
        }
      }
LABEL_67:
      if ( v9 )
      {
        if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
          if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
      goto LABEL_71;
    }
    break;
  }
  v12 = ExAllocatePool2(64, 32, 1715758931);
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    *(_QWORD *)(v12 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(v12 + 16), 0);
  }
  else
  {
    v12 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    &v21,
    (_QWORD *)v12);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
  if ( !(_QWORD)v21 || !*((_QWORD *)&v21 + 1) || !*(_DWORD *)(*((_QWORD *)&v21 + 1) + 8LL) )
    goto LABEL_67;
  v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
          v21,
          *v6,
          v13,
          v14);
  if ( v15 >= 0 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
      a2,
      &v21);
    goto LABEL_38;
  }
  if ( v9 )
  {
LABEL_59:
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000c9a8  mov     [rsp-38h+arg_10], rbx
0x18000c9ad  push    rbp
0x18000c9ae  push    rsi
0x18000c9af  push    rdi
0x18000c9b0  push    r12
0x18000c9b2  push    r13
0x18000c9b4  push    r14
0x18000c9b6  push    r15
0x18000c9b8  mov     rbp, rsp
0x18000c9bb  sub     rsp, 40h
0x18000c9bf  mov     rax, [rdx+20h]
0x18000c9c3  lea     r12, [rdx+8]
0x18000c9c7  mov     r13, rdx
0x18000c9ca  mov     rbx, rcx
0x18000c9cd  cmp     rax, r12
0x18000c9d0  jz      short loc_18000C9EB
0x18000c9d2  lea     r8, [rbp+arg_0]
0x18000c9d6  mov     [rbp+arg_0], rax
0x18000c9da  lea     rdx, [rbp+arg_8]
0x18000c9de  mov     rcx, r13
0x18000c9e1  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18000c9e6  mov     rax, [rax]
0x18000c9e9  jmp     short loc_18000C9CD
0x18000c9eb  mov     rdi, [rbx+20h]
0x18000c9ef  lea     rax, [rbx+8]
0x18000c9f3  mov     [rbp+arg_0], rax
0x18000c9f7  cmp     rdi, rax
0x18000c9fa  jz      loc_18000CDEE
0x18000ca00  mov     rbx, [r13+20h]
0x18000ca04  xorps   xmm0, xmm0
0x18000ca07  xorps   xmm1, xmm1
0x18000ca0a  movdqu  [rbp+var_10], xmm1
0x18000ca0f  mov     r14, qword ptr [rbp+var_10+8]
0x18000ca13  mov     r15, qword ptr [rbp+var_10]
0x18000ca17  movdqu  [rbp+var_20], xmm0
0x18000ca1c  mov     rsi, qword ptr [rbp+var_20+8]
0x18000ca20  cmp     rbx, r12
0x18000ca23  jz      loc_18000CB00
0x18000ca29  cmp     qword ptr [rbp+var_20], 0
0x18000ca2e  jz      short loc_18000CA3C
0x18000ca30  test    rsi, rsi
0x18000ca33  jz      short loc_18000CA3C
0x18000ca35  mov     eax, [rsi+8]
0x18000ca38  test    eax, eax
0x18000ca3a  jnz     short loc_18000CA8D
0x18000ca3c  mov     rdx, [rbx]
0x18000ca3f  mov     r8b, 1; CaseInSensitive
0x18000ca42  mov     rcx, [rdi]
0x18000ca45  add     rdx, 10h; String2
0x18000ca49  add     rcx, 10h; String1
0x18000ca4d  call    cs:__imp_RtlCompareUnicodeString
0x18000ca54  nop     dword ptr [rax+rax+00h]
0x18000ca59  test    eax, eax
0x18000ca5b  jnz     short loc_18000CA8D
0x18000ca5d  mov     rax, [rbx]
0x18000ca60  lea     rdx, [rbx+8]
0x18000ca64  lea     rcx, [rbp+var_20+8]
0x18000ca68  mov     qword ptr [rbp+var_20], rax
0x18000ca6c  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000ca71  test    r14, r14
0x18000ca74  jz      short loc_18000CA89
0x18000ca76  mov     eax, [r14+8]
0x18000ca7a  test    eax, eax
0x18000ca7c  jz      short loc_18000CA89
0x18000ca7e  mov     rsi, qword ptr [rbp+var_20+8]
0x18000ca82  test    r15, r15
0x18000ca85  jnz     short loc_18000CB00
0x18000ca87  jmp     short loc_18000CA9F
0x18000ca89  mov     rsi, qword ptr [rbp+var_20+8]
0x18000ca8d  test    r15, r15
0x18000ca90  jz      short loc_18000CA9F
0x18000ca92  test    r14, r14
0x18000ca95  jz      short loc_18000CA9F
0x18000ca97  mov     eax, [r14+8]
0x18000ca9b  test    eax, eax
0x18000ca9d  jnz     short loc_18000CAEF
0x18000ca9f  mov     rdx, [rbx]
0x18000caa2  mov     r8b, 1; CaseInSensitive
0x18000caa5  mov     rcx, [rdi]
0x18000caa8  add     rdx, 10h; String2
0x18000caac  add     rcx, 70h ; 'p'; String1
0x18000cab0  call    cs:__imp_RtlCompareUnicodeString
0x18000cab7  nop     dword ptr [rax+rax+00h]
0x18000cabc  test    eax, eax
0x18000cabe  jnz     short loc_18000CAEF
0x18000cac0  mov     rax, [rbx]
0x18000cac3  lea     rdx, [rbx+8]
0x18000cac7  lea     rcx, [rbp+var_10+8]
0x18000cacb  mov     qword ptr [rbp+var_10], rax
0x18000cacf  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000cad4  test    rsi, rsi
0x18000cad7  jz      short loc_18000CAE7
0x18000cad9  mov     eax, [rsi+8]
0x18000cadc  test    eax, eax
0x18000cade  jz      short loc_18000CAE7
0x18000cae0  cmp     qword ptr [rbp+var_20], 0
0x18000cae5  jnz     short loc_18000CAF8
0x18000cae7  mov     r14, qword ptr [rbp+var_10+8]
0x18000caeb  mov     r15, qword ptr [rbp+var_10]
0x18000caef  mov     rbx, [rbx+18h]
0x18000caf3  jmp     loc_18000CA20
0x18000caf8  mov     r14, qword ptr [rbp+var_10+8]
0x18000cafc  mov     r15, qword ptr [rbp+var_10]
0x18000cb00  cmp     qword ptr [rbp+var_20], 0
0x18000cb05  jz      short loc_18000CB17
0x18000cb07  test    rsi, rsi
0x18000cb0a  jz      short loc_18000CB17
0x18000cb0c  mov     eax, [rsi+8]
0x18000cb0f  test    eax, eax
0x18000cb11  jnz     loc_18000CBA8
0x18000cb17  mov     edx, 20h ; ' '
0x18000cb1c  mov     r8d, 66446753h
0x18000cb22  lea     ecx, [rdx+20h]
0x18000cb25  call    cs:__imp_ExAllocatePool2
0x18000cb2c  nop     dword ptr [rax+rax+00h]
0x18000cb31  mov     rbx, rax
0x18000cb34  xor     eax, eax
0x18000cb36  test    rbx, rbx
0x18000cb39  jz      short loc_18000CB56
0x18000cb3b  lea     rcx, [rbx+10h]; DestinationString
0x18000cb3f  mov     [rbx], rax
0x18000cb42  xor     edx, edx; SourceString
0x18000cb44  mov     [rbx+8], rax
0x18000cb48  call    cs:__imp_RtlInitUnicodeString
0x18000cb4f  nop     dword ptr [rax+rax+00h]
0x18000cb54  jmp     short loc_18000CB59
0x18000cb56  mov     rbx, rax
0x18000cb59  mov     rdx, rbx
0x18000cb5c  lea     rcx, [rbp+var_20]
0x18000cb60  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000cb65  mov     rcx, qword ptr [rbp+var_20]
0x18000cb69  mov     rsi, qword ptr [rbp+var_20+8]
0x18000cb6d  test    rcx, rcx
0x18000cb70  jz      loc_18000CD61
0x18000cb76  test    rsi, rsi
0x18000cb79  jz      loc_18000CD61
0x18000cb7f  mov     eax, [rsi+8]
0x18000cb82  test    eax, eax
0x18000cb84  jz      loc_18000CD61
0x18000cb8a  mov     rdx, [rdi]
0x18000cb8d  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x18000cb92  mov     ebx, eax
0x18000cb94  test    eax, eax
0x18000cb96  js      loc_18000CCDA
0x18000cb9c  lea     rdx, [rbp+var_20]
0x18000cba0  mov     rcx, r13
0x18000cba3  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000cba8  test    r15, r15
0x18000cbab  jz      short loc_18000CBBE
0x18000cbad  test    r14, r14
0x18000cbb0  jz      short loc_18000CBBE
0x18000cbb2  mov     eax, [r14+8]
0x18000cbb6  test    eax, eax
0x18000cbb8  jnz     loc_18000CC55
0x18000cbbe  mov     edx, 20h ; ' '
0x18000cbc3  mov     r8d, 66446753h
0x18000cbc9  lea     ecx, [rdx+20h]
0x18000cbcc  call    cs:__imp_ExAllocatePool2
0x18000cbd3  nop     dword ptr [rax+rax+00h]
0x18000cbd8  xor     r15d, r15d
0x18000cbdb  mov     rbx, rax
0x18000cbde  test    rax, rax
0x18000cbe1  jz      short loc_18000CBFE
0x18000cbe3  lea     rcx, [rax+10h]; DestinationString
0x18000cbe7  mov     [rax], r15
0x18000cbea  xor     edx, edx; SourceString
0x18000cbec  mov     [rax+8], r15
0x18000cbf0  call    cs:__imp_RtlInitUnicodeString
0x18000cbf7  nop     dword ptr [rax+rax+00h]
0x18000cbfc  jmp     short loc_18000CC01
0x18000cbfe  mov     rbx, r15
0x18000cc01  mov     rdx, rbx
0x18000cc04  lea     rcx, [rbp+var_10]
0x18000cc08  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000cc0d  mov     rcx, qword ptr [rbp+var_10]
0x18000cc11  mov     r14, qword ptr [rbp+var_10+8]
0x18000cc15  test    rcx, rcx
0x18000cc18  jz      loc_18000CD61
0x18000cc1e  test    r14, r14
0x18000cc21  jz      loc_18000CDA6
0x18000cc27  mov     eax, [r14+8]
0x18000cc2b  test    eax, eax
0x18000cc2d  jz      loc_18000CD61
0x18000cc33  mov     rdx, [rdi]
0x18000cc36  add     rdx, 60h ; '`'
0x18000cc3a  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x18000cc3f  mov     ebx, eax
0x18000cc41  test    eax, eax
0x18000cc43  js      loc_18000CCD4
0x18000cc49  lea     rdx, [rbp+var_10]
0x18000cc4d  mov     rcx, r13
0x18000cc50  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000cc55  or      ebx, 0FFFFFFFFh
0x18000cc58  mov     eax, ebx
0x18000cc5a  lock xadd [r14+8], eax
0x18000cc60  add     eax, ebx
0x18000cc62  jnz     short loc_18000CC8E
0x18000cc64  mov     rax, [r14]
0x18000cc67  mov     rcx, r14
0x18000cc6a  mov     rax, [rax+8]
0x18000cc6e  call    _guard_dispatch_icall
0x18000cc73  mov     eax, ebx
0x18000cc75  lock xadd [r14+0Ch], eax
0x18000cc7b  add     eax, ebx
0x18000cc7d  jnz     short loc_18000CC8E
0x18000cc7f  mov     rax, [r14]
0x18000cc82  mov     rcx, r14
0x18000cc85  mov     rax, [rax+10h]
0x18000cc89  call    _guard_dispatch_icall
0x18000cc8e  test    rsi, rsi
0x18000cc91  jz      short loc_18000CCC7
0x18000cc93  mov     eax, ebx
0x18000cc95  lock xadd [rsi+8], eax
0x18000cc9a  add     eax, ebx
0x18000cc9c  jnz     short loc_18000CCC7
0x18000cc9e  mov     rax, [rsi]
0x18000cca1  mov     rcx, rsi
0x18000cca4  mov     rax, [rax+8]
0x18000cca8  call    _guard_dispatch_icall
0x18000ccad  mov     eax, ebx
0x18000ccaf  lock xadd [rsi+0Ch], eax
0x18000ccb4  add     eax, ebx
0x18000ccb6  jnz     short loc_18000CCC7
0x18000ccb8  mov     rax, [rsi]
0x18000ccbb  mov     rcx, rsi
0x18000ccbe  mov     rax, [rax+10h]
0x18000ccc2  call    _guard_dispatch_icall
0x18000ccc7  mov     rdi, [rdi+18h]
0x18000cccb  mov     rax, [rbp+arg_0]
0x18000cccf  jmp     loc_18000C9F7
0x18000ccd4  or      r15d, 0FFFFFFFFh
0x18000ccd8  jmp     short loc_18000CCE3
0x18000ccda  or      r15d, 0FFFFFFFFh
0x18000ccde  test    r14, r14
0x18000cce1  jz      short loc_18000CD1D
0x18000cce3  mov     eax, r15d
0x18000cce6  lock xadd [r14+8], eax
0x18000ccec  add     eax, r15d
0x18000ccef  jnz     short loc_18000CD1D
0x18000ccf1  mov     rax, [r14]
0x18000ccf4  mov     rcx, r14
0x18000ccf7  mov     rax, [rax+8]
0x18000ccfb  call    _guard_dispatch_icall
0x18000cd00  mov     eax, r15d
0x18000cd03  lock xadd [r14+0Ch], eax
0x18000cd09  add     eax, r15d
0x18000cd0c  jnz     short loc_18000CD1D
0x18000cd0e  mov     rax, [r14]
0x18000cd11  mov     rcx, r14
0x18000cd14  mov     rax, [rax+10h]
0x18000cd18  call    _guard_dispatch_icall
0x18000cd1d  test    rsi, rsi
0x18000cd20  jz      short loc_18000CD5A
0x18000cd22  mov     eax, r15d
0x18000cd25  lock xadd [rsi+8], eax
0x18000cd2a  add     eax, r15d
0x18000cd2d  jnz     short loc_18000CD5A
0x18000cd2f  mov     rax, [rsi]
0x18000cd32  mov     rcx, rsi
0x18000cd35  mov     rax, [rax+8]
0x18000cd39  call    _guard_dispatch_icall
0x18000cd3e  mov     eax, r15d
0x18000cd41  lock xadd [rsi+0Ch], eax
0x18000cd46  add     eax, r15d
0x18000cd49  jnz     short loc_18000CD5A
0x18000cd4b  mov     rax, [rsi]
0x18000cd4e  mov     rcx, rsi
0x18000cd51  mov     rax, [rax+10h]
0x18000cd55  call    _guard_dispatch_icall
0x18000cd5a  mov     eax, ebx
0x18000cd5c  jmp     loc_18000CDF0
0x18000cd61  test    r14, r14
0x18000cd64  jz      short loc_18000CDA6
0x18000cd66  or      r15d, 0FFFFFFFFh
0x18000cd6a  mov     eax, r15d
0x18000cd6d  lock xadd [r14+8], eax
0x18000cd73  add     eax, r15d
0x18000cd76  jnz     short loc_18000CDAA
0x18000cd78  mov     rax, [r14]
0x18000cd7b  mov     rcx, r14
0x18000cd7e  mov     rax, [rax+8]
0x18000cd82  call    _guard_dispatch_icall
0x18000cd87  mov     eax, r15d
0x18000cd8a  lock xadd [r14+0Ch], eax
0x18000cd90  add     eax, r15d
0x18000cd93  jnz     short loc_18000CDAA
0x18000cd95  mov     rax, [r14]
0x18000cd98  mov     rcx, r14
0x18000cd9b  mov     rax, [rax+10h]
0x18000cd9f  call    _guard_dispatch_icall
0x18000cda4  jmp     short loc_18000CDAA
0x18000cda6  or      r15d, 0FFFFFFFFh
0x18000cdaa  test    rsi, rsi
0x18000cdad  jz      short loc_18000CDE7
0x18000cdaf  mov     eax, r15d
0x18000cdb2  lock xadd [rsi+8], eax
0x18000cdb7  add     eax, r15d
0x18000cdba  jnz     short loc_18000CDE7
0x18000cdbc  mov     rax, [rsi]
0x18000cdbf  mov     rcx, rsi
  ... truncated ...
```
