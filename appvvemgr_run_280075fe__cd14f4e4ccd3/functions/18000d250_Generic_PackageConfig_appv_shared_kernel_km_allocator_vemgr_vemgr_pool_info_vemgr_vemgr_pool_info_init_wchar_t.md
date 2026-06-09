# Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,wchar_t const *,bool,bool,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x18000d250`
- end: `0x18000d375`
- name: `?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_W0_N1AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d184`
- `0x180010b50`

## callees

- `0x180003f50`
- `0x18000a9e4`
- `0x18000d250`
- `0x18000e588`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000d28d`
- `ntoskrnl!ExAllocatePool2` at `0x18000d28d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000d2ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000d2ae`

## pseudocode

```c
char __fastcall Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        __int64 a6)
{
  __int64 Pool2; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r8
  _QWORD *i; // rbx

  if ( !a2 || !a3 )
    return 0;
  Pool2 = ExAllocatePool2(256, 32, 1733125462);
  v11 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v11 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a1,
    v11);
  if ( !*(_QWORD *)a1 )
    return 0;
  v12 = *(_QWORD *)(a1 + 8);
  if ( !v12 )
    return 0;
  if ( !*(_DWORD *)(v12 + 8) )
    return 0;
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
              *(_QWORD *)a1,
              a2,
              v14) < 0 )
    return 0;
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
              a1 + 16,
              a3,
              v13) < 0 )
    return 0;
  *(_BYTE *)(a1 + 49) = a5;
  *(_BYTE *)(a1 + 48) = a4;
  for ( i = *(_QWORD **)(a6 + 32); i != (_QWORD *)(a6 + 8); i = (_QWORD *)i[3] )
  {
    if ( (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1 + 56,
                i) < 0 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d250  push    rbx
0x18000d252  push    rbp
0x18000d253  push    rsi
0x18000d254  push    rdi
0x18000d255  push    r14
0x18000d257  push    r15
0x18000d259  sub     rsp, 28h
0x18000d25d  xor     r15d, r15d
0x18000d260  mov     r14b, r9b
0x18000d263  mov     rsi, r8
0x18000d266  mov     rbp, rdx
0x18000d269  mov     rdi, rcx
0x18000d26c  test    rdx, rdx
0x18000d26f  jz      loc_18000D365
0x18000d275  test    r8, r8
0x18000d278  jz      loc_18000D365
0x18000d27e  lea     edx, [r15+20h]
0x18000d282  mov     ecx, 100h
0x18000d287  mov     r8d, 674D6556h
0x18000d28d  call    cs:__imp_ExAllocatePool2
0x18000d294  nop     dword ptr [rax+rax+00h]
0x18000d299  mov     rbx, rax
0x18000d29c  test    rax, rax
0x18000d29f  jz      short loc_18000D2BC
0x18000d2a1  lea     rcx, [rax+10h]; DestinationString
0x18000d2a5  mov     [rax], r15
0x18000d2a8  xor     edx, edx; SourceString
0x18000d2aa  mov     [rax+8], r15
0x18000d2ae  call    cs:__imp_RtlInitUnicodeString
0x18000d2b5  nop     dword ptr [rax+rax+00h]
0x18000d2ba  jmp     short loc_18000D2BF
0x18000d2bc  mov     rbx, r15
0x18000d2bf  mov     rdx, rbx
0x18000d2c2  mov     rcx, rdi
0x18000d2c5  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000d2ca  cmp     [rdi], r15
0x18000d2cd  jz      loc_18000D365
0x18000d2d3  mov     rax, [rdi+8]
0x18000d2d7  test    rax, rax
0x18000d2da  jz      loc_18000D365
0x18000d2e0  mov     eax, [rax+8]
0x18000d2e3  test    eax, eax
0x18000d2e5  jz      short loc_18000D365
0x18000d2e7  mov     rcx, [rdi]
0x18000d2ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d2ee  mov     r8, rbx
0x18000d2f1  inc     r8
0x18000d2f4  cmp     [rbp+r8*2+0], r15w
0x18000d2fa  jnz     short loc_18000D2F1
0x18000d2fc  mov     rdx, rbp
0x18000d2ff  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000d304  test    eax, eax
0x18000d306  js      short loc_18000D365
0x18000d308  inc     rbx
0x18000d30b  cmp     [rsi+rbx*2], r15w
0x18000d310  jnz     short loc_18000D308
0x18000d312  lea     rcx, [rdi+10h]
0x18000d316  mov     r8, rbx
0x18000d319  mov     rdx, rsi
0x18000d31c  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000d321  test    eax, eax
0x18000d323  js      short loc_18000D365
0x18000d325  mov     al, [rsp+58h+arg_20]
0x18000d32c  lea     rsi, [rdi+38h]
0x18000d330  mov     [rdi+31h], al
0x18000d333  mov     rax, [rsp+58h+arg_28]
0x18000d33b  mov     [rdi+30h], r14b
0x18000d33f  mov     rbx, [rax+20h]
0x18000d343  lea     rdi, [rax+8]
0x18000d347  cmp     rbx, rdi
0x18000d34a  jz      short loc_18000D361
0x18000d34c  mov     rdx, rbx
0x18000d34f  mov     rcx, rsi
0x18000d352  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000d357  test    eax, eax
0x18000d359  js      short loc_18000D365
0x18000d35b  mov     rbx, [rbx+18h]
0x18000d35f  jmp     short loc_18000D347
0x18000d361  mov     al, 1
0x18000d363  jmp     short loc_18000D367
0x18000d365  xor     al, al
0x18000d367  add     rsp, 28h
0x18000d36b  pop     r15
0x18000d36d  pop     r14
0x18000d36f  pop     rdi
0x18000d370  pop     rsi
0x18000d371  pop     rbp
0x18000d372  pop     rbx
0x18000d373  retn
```
