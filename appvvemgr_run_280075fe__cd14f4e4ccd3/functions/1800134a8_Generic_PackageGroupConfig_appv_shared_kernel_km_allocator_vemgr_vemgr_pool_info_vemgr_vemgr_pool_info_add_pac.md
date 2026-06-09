# Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package(wchar_t const *)

- ea: `0x1800134a8`
- end: `0x18001365f`
- name: `?add_package@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800110e8`

## callees

- `0x180001448`
- `0x18000a9e4`
- `0x18000e588`
- `0x1800134a8`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800134cb`
- `ntoskrnl!ExAllocatePool2` at `0x1800134cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800134ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800134ef`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800135a6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800135a6`

## pseudocode

```c
__int64 __fastcall Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package(
        __int64 a1,
        __int64 a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rbx
  const UNICODE_STRING *v6; // r14
  volatile signed __int32 *v7; // rdi
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 i; // rbx
  __int64 v11; // rax
  _QWORD v13[9]; // [rsp+20h] [rbp-48h] BYREF

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
    v13,
    v5);
  v6 = (const UNICODE_STRING *)v13[0];
  v7 = (volatile signed __int32 *)v13[1];
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a2 + 2 * v8) );
  }
  else
  {
    v8 = 0;
  }
  v9 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
         v13[0],
         a2,
         v8);
  if ( (v9 & 0x80000000) == 0 )
  {
    for ( i = *(_QWORD *)(a1 + 48); i != a1 + 24; i = *(_QWORD *)(i + 24) )
    {
      if ( *(_QWORD *)i )
      {
        v11 = *(_QWORD *)(i + 8);
        if ( v11 )
        {
          if ( *(_DWORD *)(v11 + 8) && !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)i + 16LL), v6 + 1, 1u) )
          {
            if ( v7 )
            {
              if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
              {
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
                if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
              }
            }
            return 3221226026LL;
          }
        }
      }
    }
    v9 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
           a1 + 16,
           v13);
    if ( !v7 || _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) != 1 )
      return v9;
  }
  else if ( !v7 || _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) != 1 )
  {
    return v9;
  }
  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
  return v9;
}

```

## disassembly

```asm
0x1800134a8  push    rbx
0x1800134aa  push    rbp
0x1800134ab  push    rsi
0x1800134ac  push    rdi
0x1800134ad  push    r12
0x1800134af  push    r14
0x1800134b1  push    r15
0x1800134b3  sub     rsp, 30h
0x1800134b7  mov     rsi, rdx
0x1800134ba  mov     rbp, rcx
0x1800134bd  mov     edx, 20h ; ' '
0x1800134c2  mov     r8d, 66446753h
0x1800134c8  lea     ecx, [rdx+20h]
0x1800134cb  call    cs:__imp_ExAllocatePool2
0x1800134d2  nop     dword ptr [rax+rax+00h]
0x1800134d7  xor     r15d, r15d
0x1800134da  mov     rbx, rax
0x1800134dd  test    rax, rax
0x1800134e0  jz      short loc_1800134FD
0x1800134e2  lea     rcx, [rax+10h]; DestinationString
0x1800134e6  mov     [rax], r15
0x1800134e9  xor     edx, edx; SourceString
0x1800134eb  mov     [rax+8], r15
0x1800134ef  call    cs:__imp_RtlInitUnicodeString
0x1800134f6  nop     dword ptr [rax+rax+00h]
0x1800134fb  jmp     short loc_180013500
0x1800134fd  mov     rbx, r15
0x180013500  mov     rdx, rbx
0x180013503  lea     rcx, [rsp+68h+var_48]
0x180013508  call    ??$?0V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAA@PEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18001350d  mov     r14, [rsp+68h+var_48]
0x180013512  mov     rdi, [rsp+68h+var_40]
0x180013517  test    r14, r14
0x18001351a  jz      short loc_180013524
0x18001351c  test    rdi, rdi
0x18001351f  jz      short loc_180013524
0x180013521  mov     eax, [rdi+8]
0x180013524  or      r12, 0FFFFFFFFFFFFFFFFh
0x180013528  test    rsi, rsi
0x18001352b  jnz     short loc_180013532
0x18001352d  mov     r8, r15
0x180013530  jmp     short loc_18001353F
0x180013532  mov     r8, r12
0x180013535  inc     r8
0x180013538  cmp     [rsi+r8*2], r15w
0x18001353d  jnz     short loc_180013535
0x18001353f  mov     rdx, rsi
0x180013542  mov     rcx, r14
0x180013545  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18001354a  mov     ebx, eax
0x18001354c  test    eax, eax
0x18001354e  jns     short loc_180013576
0x180013550  test    rdi, rdi
0x180013553  jz      loc_18001364D
0x180013559  mov     ecx, r12d
0x18001355c  lock xadd [rdi+8], ecx
0x180013561  add     ecx, r12d
0x180013564  jnz     loc_18001364D
0x18001356a  mov     rdx, [rdi]
0x18001356d  mov     rax, [rdx+8]
0x180013571  jmp     loc_180013629
0x180013576  mov     rbx, [rbp+30h]
0x18001357a  lea     rsi, [rbp+18h]
0x18001357e  cmp     rbx, rsi
0x180013581  jz      short loc_180013600
0x180013583  cmp     [rbx], r15
0x180013586  jz      short loc_1800135B6
0x180013588  mov     rax, [rbx+8]
0x18001358c  test    rax, rax
0x18001358f  jz      short loc_1800135B6
0x180013591  mov     eax, [rax+8]
0x180013594  test    eax, eax
0x180013596  jz      short loc_1800135B6
0x180013598  mov     rcx, [rbx]
0x18001359b  lea     rdx, [r14+10h]; String2
0x18001359f  add     rcx, 10h; String1
0x1800135a3  mov     r8b, 1; CaseInSensitive
0x1800135a6  call    cs:__imp_RtlCompareUnicodeString
0x1800135ad  nop     dword ptr [rax+rax+00h]
0x1800135b2  test    eax, eax
0x1800135b4  jz      short loc_1800135BC
0x1800135b6  mov     rbx, [rbx+18h]
0x1800135ba  jmp     short loc_18001357E
0x1800135bc  test    rdi, rdi
0x1800135bf  jz      short loc_1800135F9
0x1800135c1  mov     eax, r12d
0x1800135c4  lock xadd [rdi+8], eax
0x1800135c9  add     eax, r12d
0x1800135cc  jnz     short loc_1800135F9
0x1800135ce  mov     rax, [rdi]
0x1800135d1  mov     rcx, rdi
0x1800135d4  mov     rax, [rax+8]
0x1800135d8  call    _guard_dispatch_icall
0x1800135dd  mov     eax, r12d
0x1800135e0  lock xadd [rdi+0Ch], eax
0x1800135e5  add     eax, r12d
0x1800135e8  jnz     short loc_1800135F9
0x1800135ea  mov     rax, [rdi]
0x1800135ed  mov     rcx, rdi
0x1800135f0  mov     rax, [rax+10h]
0x1800135f4  call    _guard_dispatch_icall
0x1800135f9  mov     eax, 0C000022Ah
0x1800135fe  jmp     short loc_18001364F
0x180013600  lea     rcx, [rbp+10h]
0x180013604  lea     rdx, [rsp+68h+var_48]
0x180013609  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18001360e  mov     ebx, eax
0x180013610  test    rdi, rdi
0x180013613  jz      short loc_18001364D
0x180013615  mov     ecx, r12d
0x180013618  lock xadd [rdi+8], ecx
0x18001361d  add     ecx, r12d
0x180013620  jnz     short loc_18001364D
0x180013622  mov     rcx, [rdi]
0x180013625  mov     rax, [rcx+8]
0x180013629  mov     rcx, rdi
0x18001362c  call    _guard_dispatch_icall
0x180013631  mov     eax, r12d
0x180013634  lock xadd [rdi+0Ch], eax
0x180013639  add     eax, r12d
0x18001363c  jnz     short loc_18001364D
0x18001363e  mov     rax, [rdi]
0x180013641  mov     rcx, rdi
0x180013644  mov     rax, [rax+10h]
0x180013648  call    _guard_dispatch_icall
0x18001364d  mov     eax, ebx
0x18001364f  add     rsp, 30h
0x180013653  pop     r15
0x180013655  pop     r14
0x180013657  pop     r12
0x180013659  pop     rdi
0x18001365a  pop     rsi
0x18001365b  pop     rbp
0x18001365c  pop     rbx
0x18001365d  retn
```
