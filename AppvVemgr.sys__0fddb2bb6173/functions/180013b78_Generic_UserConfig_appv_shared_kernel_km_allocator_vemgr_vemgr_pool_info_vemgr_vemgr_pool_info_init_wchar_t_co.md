# Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,wchar_t const *,wchar_t const *,void *,ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,bool,bool)

- ea: `0x180013b78`
- end: `0x180013d43`
- name: `?init@?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_W00PEAXKAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@_N4@Z`
- size: `459`
- prototype: `char(__int64, _WORD *, _WORD *, _WORD *, void *, unsigned int, __int64, __int64, char, char, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011538`

## callees

- `0x180003f50`
- `0x18000a9e4`
- `0x18000ab2c`
- `0x18000e588`
- `0x180013b78`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180013beb`
- `ntoskrnl!ExAllocatePool2` at `0x180013beb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013c0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013c0c`

## pseudocode

```c
char Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
        __int64 a1,
        _WORD *a2,
        _WORD *a3,
        _WORD *a4,
        void *a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        ...)
{
  __int64 Pool2; // rax
  _QWORD *v15; // rbx
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 i; // rbx
  __int64 j; // rbx

  if ( !a2 || !a4 || !a5 || !a6 )
    return 0;
  *(_BYTE *)(a1 + 184) = a9;
  *(_BYTE *)(a1 + 185) = a10;
  Pool2 = ExAllocatePool2(256, 32, 1733125462);
  v15 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v15 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    (_QWORD *)a1,
    v15);
  if ( !*(_QWORD *)a1 )
    return 0;
  v17 = *(_QWORD *)(a1 + 8);
  if ( !v17 )
    return 0;
  if ( !*(_DWORD *)(v17 + 8) )
    return 0;
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
              *(_QWORD *)a1,
              a2,
              v19,
              v16) < 0 )
    return 0;
  if ( a3 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a3[v21] );
  }
  else
  {
    v21 = 0;
  }
  if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
              a1 + 16,
              a3,
              v21,
              v20) < 0 )
    return 0;
  do
    ++v18;
  while ( a4[v18] );
  if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
              a1 + 48,
              a4,
              v18,
              v22) < 0
    || appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(a1 + 80, a5, a6) < 0 )
  {
    return 0;
  }
  for ( i = *(_QWORD *)(a7 + 32); i != a7 + 8; i = *(_QWORD *)(i + 24) )
  {
    if ( (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1 + 104,
                i) < 0 )
      return 0;
  }
  for ( j = *(_QWORD *)(a8 + 32); j != a8 + 8; j = *(_QWORD *)(j + 24) )
  {
    if ( (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1 + 144,
                j) < 0 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180013b78  push    rbx
0x180013b7a  push    rbp
0x180013b7b  push    rsi
0x180013b7c  push    rdi
0x180013b7d  push    r13
0x180013b7f  push    r14
0x180013b81  sub     rsp, 28h
0x180013b85  xor     r13d, r13d
0x180013b88  mov     r14, r9
0x180013b8b  mov     rbp, r8
0x180013b8e  mov     rsi, rdx
0x180013b91  mov     rdi, rcx
0x180013b94  test    rdx, rdx
0x180013b97  jz      loc_180013D33
0x180013b9d  test    r9, r9
0x180013ba0  jz      loc_180013D33
0x180013ba6  cmp     [rsp+58h+arg_20], r13
0x180013bae  jz      loc_180013D33
0x180013bb4  cmp     [rsp+58h+arg_28], r13d
0x180013bbc  jz      loc_180013D33
0x180013bc2  mov     al, [rsp+58h+arg_40]
0x180013bc9  lea     edx, [r13+20h]
0x180013bcd  mov     [rcx+0B8h], al
0x180013bd3  mov     r8d, 674D6556h
0x180013bd9  mov     al, [rsp+58h+arg_48]
0x180013be0  mov     [rcx+0B9h], al
0x180013be6  mov     ecx, 100h
0x180013beb  call    cs:__imp_ExAllocatePool2
0x180013bf2  nop     dword ptr [rax+rax+00h]
0x180013bf7  mov     rbx, rax
0x180013bfa  test    rax, rax
0x180013bfd  jz      short loc_180013C1A
0x180013bff  lea     rcx, [rax+10h]; DestinationString
0x180013c03  mov     [rax], r13
0x180013c06  xor     edx, edx; SourceString
0x180013c08  mov     [rax+8], r13
0x180013c0c  call    cs:__imp_RtlInitUnicodeString
0x180013c13  nop     dword ptr [rax+rax+00h]
0x180013c18  jmp     short loc_180013C1D
0x180013c1a  mov     rbx, r13
0x180013c1d  mov     rdx, rbx
0x180013c20  mov     rcx, rdi
0x180013c23  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x180013c28  cmp     [rdi], r13
0x180013c2b  jz      loc_180013D33
0x180013c31  mov     rax, [rdi+8]
0x180013c35  test    rax, rax
0x180013c38  jz      loc_180013D33
0x180013c3e  mov     eax, [rax+8]
0x180013c41  test    eax, eax
0x180013c43  jz      loc_180013D33
0x180013c49  mov     rcx, [rdi]
0x180013c4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013c50  mov     r8, rbx
0x180013c53  inc     r8
0x180013c56  cmp     [rsi+r8*2], r13w
0x180013c5b  jnz     short loc_180013C53
0x180013c5d  mov     rdx, rsi
0x180013c60  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180013c65  test    eax, eax
0x180013c67  js      loc_180013D33
0x180013c6d  test    rbp, rbp
0x180013c70  jnz     short loc_180013C77
0x180013c72  mov     r8, r13
0x180013c75  jmp     short loc_180013C85
0x180013c77  mov     r8, rbx
0x180013c7a  inc     r8
0x180013c7d  cmp     [rbp+r8*2+0], r13w
0x180013c83  jnz     short loc_180013C7A
0x180013c85  lea     rcx, [rdi+10h]
0x180013c89  mov     rdx, rbp
0x180013c8c  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180013c91  test    eax, eax
0x180013c93  js      loc_180013D33
0x180013c99  inc     rbx
0x180013c9c  cmp     [r14+rbx*2], r13w
0x180013ca1  jnz     short loc_180013C99
0x180013ca3  lea     rcx, [rdi+30h]
0x180013ca7  mov     r8, rbx
0x180013caa  mov     rdx, r14
0x180013cad  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180013cb2  test    eax, eax
0x180013cb4  js      short loc_180013D33
0x180013cb6  mov     r8d, [rsp+58h+arg_28]
0x180013cbe  lea     rcx, [rdi+50h]
0x180013cc2  mov     rdx, [rsp+58h+arg_20]
0x180013cca  call    ?assign@?$sid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEAXK@Z; appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(void *,ulong)
0x180013ccf  test    eax, eax
0x180013cd1  js      short loc_180013D33
0x180013cd3  mov     rax, [rsp+58h+arg_30]
0x180013cdb  mov     rbx, [rax+20h]
0x180013cdf  lea     rsi, [rax+8]
0x180013ce3  cmp     rbx, rsi
0x180013ce6  jz      short loc_180013CFE
0x180013ce8  mov     rdx, rbx
0x180013ceb  lea     rcx, [rdi+68h]
0x180013cef  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180013cf4  test    eax, eax
0x180013cf6  js      short loc_180013D33
0x180013cf8  mov     rbx, [rbx+18h]
0x180013cfc  jmp     short loc_180013CE3
0x180013cfe  mov     rax, [rsp+58h+arg_38]
0x180013d06  lea     rsi, [rdi+90h]
0x180013d0d  mov     rbx, [rax+20h]
0x180013d11  lea     rdi, [rax+8]
0x180013d15  cmp     rbx, rdi
0x180013d18  jz      short loc_180013D2F
0x180013d1a  mov     rdx, rbx
0x180013d1d  mov     rcx, rsi
0x180013d20  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180013d25  test    eax, eax
0x180013d27  js      short loc_180013D33
0x180013d29  mov     rbx, [rbx+18h]
0x180013d2d  jmp     short loc_180013D15
0x180013d2f  mov     al, 1
0x180013d31  jmp     short loc_180013D35
0x180013d33  xor     al, al
0x180013d35  add     rsp, 28h
0x180013d39  pop     r14
0x180013d3b  pop     r13
0x180013d3d  pop     rdi
0x180013d3e  pop     rsi
0x180013d3f  pop     rbp
0x180013d40  pop     rbx
0x180013d41  retn
```
