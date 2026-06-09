# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_mappings(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000f300`
- end: `0x18000f712`
- name: `?retrieve_mappings@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEAV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z`
- size: `1042`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000e960`
- `0x18001a79c`

## callees

- `0x180001044`
- `0x180004804`
- `0x180005178`
- `0x18000bfb8`
- `0x18000ce10`
- `0x18000cf74`
- `0x18000e23c`
- `0x18000e588`
- `0x18000f300`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000f3d6`
- `ntoskrnl!ExAllocatePool2` at `0x18000f3d6`
- `ntoskrnl!ZwClose` at `0x18000f343`
- `ntoskrnl!ZwClose` at `0x18000f3a2`
- `ntoskrnl!ZwClose` at `0x18000f549`
- `ntoskrnl!ZwClose` at `0x18000f5ab`
- `ntoskrnl!ZwClose` at `0x18000f60b`
- `ntoskrnl!ZwClose` at `0x18000f635`
- `ntoskrnl!ZwClose` at `0x18000f695`
- `ntoskrnl!ZwClose` at `0x18000f6fc`
- `ntoskrnl!ZwClose` at `0x18000f343`
- `ntoskrnl!ZwClose` at `0x18000f3a2`
- `ntoskrnl!ZwClose` at `0x18000f549`
- `ntoskrnl!ZwClose` at `0x18000f5ab`
- `ntoskrnl!ZwClose` at `0x18000f60b`
- `ntoskrnl!ZwClose` at `0x18000f635`
- `ntoskrnl!ZwClose` at `0x18000f695`
- `ntoskrnl!ZwClose` at `0x18000f6fc`

## string_xrefs

- `0x18000f31b`: `CopyOnWriteMappings`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_mappings(
        void **a1,
        void *a2)
{
  void *v2; // rcx
  NTSTATUS v3; // ebx
  HANDLE v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r15d
  int v9; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+38h] [rbp-30h] BYREF
  __int128 *v11; // [rsp+48h] [rbp-20h]
  __int128 *v12; // [rsp+50h] [rbp-18h]
  HANDLE Handle; // [rsp+B8h] [rbp+50h] BYREF

  Handle = a2;
  v2 = *a1;
  Handle = 0;
  v3 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         v2,
         (__int64)L"CopyOnWriteMappings",
         &Handle);
  if ( v3 >= 0 )
  {
    v5 = Handle;
    v12 = &v10;
    v9 = 0;
    v11 = &v10;
    v10 = 0;
    v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(Handle);
    if ( v8 < 0 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v9,
        v6,
        v7);
      if ( v5 )
        ZwClose(v5);
      return (unsigned int)v8;
    }
    else
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v9,
        v6,
        v7);
      if ( v5 )
        ZwClose(v5);
      return 0;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18000f300  mov     [rsp-40h+Handle], rdx
0x18000f305  push    rbp
0x18000f306  push    rbx
0x18000f307  push    rsi
0x18000f308  push    rdi
0x18000f309  push    r12
0x18000f30b  push    r13
0x18000f30d  push    r14
0x18000f30f  push    r15
0x18000f311  mov     rbp, rsp
0x18000f314  sub     rsp, 68h
0x18000f318  mov     rcx, [rcx]
0x18000f31b  lea     rdx, aCopyonwritemap; "CopyOnWriteMappings"
0x18000f322  mov     r12, r8
0x18000f325  xor     edi, edi
0x18000f327  lea     r8, [rbp+Handle]
0x18000f32b  mov     [rbp+Handle], rdi
0x18000f32f  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000f334  mov     ebx, eax
0x18000f336  test    eax, eax
0x18000f338  jns     short loc_18000F356
0x18000f33a  mov     rcx, [rbp+Handle]; Handle
0x18000f33e  test    rcx, rcx
0x18000f341  jz      short loc_18000F34F
0x18000f343  call    cs:__imp_ZwClose
0x18000f34a  nop     dword ptr [rax+rax+00h]
0x18000f34f  mov     eax, ebx
0x18000f351  jmp     loc_18000F61A
0x18000f356  mov     rbx, [rbp+Handle]
0x18000f35a  lea     rax, [rbp+var_30]
0x18000f35e  mov     [rbp+var_18], rax
0x18000f362  lea     rdx, [rbp+var_38]
0x18000f366  lea     rax, [rbp+var_30]
0x18000f36a  mov     [rbp+var_38], edi
0x18000f36d  xorps   xmm0, xmm0
0x18000f370  mov     [rbp+var_20], rax
0x18000f374  mov     rcx, rbx; KeyHandle
0x18000f377  movdqu  [rbp+var_30], xmm0
0x18000f37c  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000f381  mov     r15d, eax
0x18000f384  test    eax, eax
0x18000f386  js      loc_18000F5FA
0x18000f38c  cmp     [rbp+var_38], edi
0x18000f38f  jnz     short loc_18000F3B5
0x18000f391  lea     rcx, [rbp+var_38]
0x18000f395  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000f39a  test    rbx, rbx
0x18000f39d  jz      short loc_18000F3AE
0x18000f39f  mov     rcx, rbx; Handle
0x18000f3a2  call    cs:__imp_ZwClose
0x18000f3a9  nop     dword ptr [rax+rax+00h]
0x18000f3ae  xor     eax, eax
0x18000f3b0  jmp     loc_18000F61A
0x18000f3b5  mov     rsi, [rbp+var_18]
0x18000f3b9  lea     rax, [rbp+var_30]
0x18000f3bd  cmp     rsi, rax
0x18000f3c0  jz      loc_18000F5FA
0x18000f3c6  mov     edx, 0C8h
0x18000f3cb  mov     ecx, 40h ; '@'
0x18000f3d0  mov     r8d, 66446753h
0x18000f3d6  call    cs:__imp_ExAllocatePool2
0x18000f3dd  nop     dword ptr [rax+rax+00h]
0x18000f3e2  test    rax, rax
0x18000f3e5  jz      short loc_18000F3F1
0x18000f3e7  mov     rcx, rax
0x18000f3ea  call    ??0?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@QEAA@XZ; Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void)
0x18000f3ef  jmp     short loc_18000F3F4
0x18000f3f1  mov     rax, rdi
0x18000f3f4  mov     rdx, rax
0x18000f3f7  lea     rcx, [rbp+var_48]
0x18000f3fb  call    ??$?0U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@QEAA@PEAU?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@Z; kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000f400  mov     r13, [rbp+var_48]
0x18000f404  mov     r14, [rbp+var_40]
0x18000f408  test    r13, r13
0x18000f40b  jz      loc_18000F6A8
0x18000f411  test    r14, r14
0x18000f414  jz      loc_18000F6EB
0x18000f41a  mov     eax, [r14+8]
0x18000f41e  test    eax, eax
0x18000f420  jz      loc_18000F6A8
0x18000f426  mov     r8, [rsi]
0x18000f429  mov     r9d, 0FFFFh
0x18000f42f  mov     [rbp+Handle], rdi
0x18000f433  mov     ecx, [r8]
0x18000f436  shr     ecx, 1
0x18000f438  cmp     ecx, r9d
0x18000f43b  ja      short loc_18000F442
0x18000f43d  movzx   edx, cx
0x18000f440  jmp     short loc_18000F445
0x18000f442  mov     edx, r9d
0x18000f445  mov     eax, edi
0x18000f447  cmovbe  ax, dx
0x18000f44b  mov     rdx, rdi
0x18000f44e  test    ax, ax
0x18000f451  jz      short loc_18000F457
0x18000f453  mov     rdx, [r8+8]
0x18000f457  lea     r8, [rbp+Handle]
0x18000f45b  mov     rcx, rbx
0x18000f45e  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000f463  mov     edi, eax
0x18000f465  test    eax, eax
0x18000f467  js      loc_18000F62C
0x18000f46d  mov     rdi, [rbp+Handle]
0x18000f471  lea     r8, [r13+0C0h]
0x18000f478  mov     rcx, rdi
0x18000f47b  lea     rdx, aFlags; "Flags"
0x18000f482  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x18000f487  mov     r15d, eax
0x18000f48a  test    eax, eax
0x18000f48c  js      loc_18000F5A3
0x18000f492  mov     r8, r13
0x18000f495  lea     rdx, aSourcevolumena; "SourceVolumeName"
0x18000f49c  mov     rcx, rdi
0x18000f49f  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f4a4  mov     r15d, eax
0x18000f4a7  test    eax, eax
0x18000f4a9  js      loc_18000F5A3
0x18000f4af  lea     r8, [r13+20h]
0x18000f4b3  mov     rcx, rdi
0x18000f4b6  lea     rdx, aSourcelongname; "SourceLongName"
0x18000f4bd  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f4c2  mov     r15d, eax
0x18000f4c5  test    eax, eax
0x18000f4c7  js      loc_18000F5A3
0x18000f4cd  lea     r8, [r13+40h]
0x18000f4d1  mov     rcx, rdi
0x18000f4d4  lea     rdx, aSourceshortnam; "SourceShortName"
0x18000f4db  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f4e0  lea     r8, [r13+60h]
0x18000f4e4  mov     rcx, rdi
0x18000f4e7  lea     rdx, aTargetvolumena; "TargetVolumeName"
0x18000f4ee  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f4f3  mov     r15d, eax
0x18000f4f6  test    eax, eax
0x18000f4f8  js      loc_18000F5A3
0x18000f4fe  lea     r8, [r13+80h]
0x18000f505  mov     rcx, rdi
0x18000f508  lea     rdx, aTargetlongname; "TargetLongName"
0x18000f50f  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f514  mov     r15d, eax
0x18000f517  test    eax, eax
0x18000f519  js      loc_18000F5A3
0x18000f51f  lea     r8, [r13+0A0h]
0x18000f526  mov     rcx, rdi
0x18000f529  lea     rdx, aTargetshortnam; "TargetShortName"
0x18000f530  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000f535  lea     rdx, [rbp+var_48]
0x18000f539  mov     rcx, r12
0x18000f53c  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000f541  test    rdi, rdi
0x18000f544  jz      short loc_18000F555
0x18000f546  mov     rcx, rdi; Handle
0x18000f549  call    cs:__imp_ZwClose
0x18000f550  nop     dword ptr [rax+rax+00h]
0x18000f555  xor     edi, edi
0x18000f557  test    r14, r14
0x18000f55a  jz      short loc_18000F59A
0x18000f55c  or      r13d, 0FFFFFFFFh
0x18000f560  mov     eax, r13d
0x18000f563  lock xadd [r14+8], eax
0x18000f569  add     eax, r13d
0x18000f56c  jnz     short loc_18000F59A
0x18000f56e  mov     rax, [r14]
0x18000f571  mov     rcx, r14
0x18000f574  mov     rax, [rax+8]
0x18000f578  call    _guard_dispatch_icall
0x18000f57d  mov     eax, r13d
0x18000f580  lock xadd [r14+0Ch], eax
0x18000f586  add     eax, r13d
0x18000f589  jnz     short loc_18000F59A
0x18000f58b  mov     rax, [r14]
0x18000f58e  mov     rcx, r14
0x18000f591  mov     rax, [rax+10h]
0x18000f595  call    _guard_dispatch_icall
0x18000f59a  mov     rsi, [rsi+18h]
0x18000f59e  jmp     loc_18000F3B9
0x18000f5a3  test    rdi, rdi
0x18000f5a6  jz      short loc_18000F5B7
0x18000f5a8  mov     rcx, rdi; Handle
0x18000f5ab  call    cs:__imp_ZwClose
0x18000f5b2  nop     dword ptr [rax+rax+00h]
0x18000f5b7  test    r14, r14
0x18000f5ba  jz      short loc_18000F5FA
0x18000f5bc  or      r13d, 0FFFFFFFFh
0x18000f5c0  mov     eax, r13d
0x18000f5c3  lock xadd [r14+8], eax
0x18000f5c9  add     eax, r13d
0x18000f5cc  jnz     short loc_18000F5FA
0x18000f5ce  mov     rax, [r14]
0x18000f5d1  mov     rcx, r14
0x18000f5d4  mov     rax, [rax+8]
0x18000f5d8  call    _guard_dispatch_icall
0x18000f5dd  mov     eax, r13d
0x18000f5e0  lock xadd [r14+0Ch], eax
0x18000f5e6  add     eax, r13d
0x18000f5e9  jnz     short loc_18000F5FA
0x18000f5eb  mov     rax, [r14]
0x18000f5ee  mov     rcx, r14
0x18000f5f1  mov     rax, [rax+10h]
0x18000f5f5  call    _guard_dispatch_icall
0x18000f5fa  lea     rcx, [rbp+var_38]
0x18000f5fe  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000f603  test    rbx, rbx
0x18000f606  jz      short loc_18000F617
0x18000f608  mov     rcx, rbx; Handle
0x18000f60b  call    cs:__imp_ZwClose
0x18000f612  nop     dword ptr [rax+rax+00h]
0x18000f617  mov     eax, r15d
0x18000f61a  add     rsp, 68h
0x18000f61e  pop     r15
0x18000f620  pop     r14
0x18000f622  pop     r13
0x18000f624  pop     r12
0x18000f626  pop     rdi
0x18000f627  pop     rsi
0x18000f628  pop     rbx
0x18000f629  pop     rbp
0x18000f62a  retn
0x18000f62c  mov     rcx, [rbp+Handle]; Handle
0x18000f630  test    rcx, rcx
0x18000f633  jz      short loc_18000F641
0x18000f635  call    cs:__imp_ZwClose
0x18000f63c  nop     dword ptr [rax+rax+00h]
0x18000f641  test    r14, r14
0x18000f644  jz      short loc_18000F684
0x18000f646  or      r13d, 0FFFFFFFFh
0x18000f64a  mov     eax, r13d
0x18000f64d  lock xadd [r14+8], eax
0x18000f653  add     eax, r13d
0x18000f656  jnz     short loc_18000F684
0x18000f658  mov     rax, [r14]
0x18000f65b  mov     rcx, r14
0x18000f65e  mov     rax, [rax+8]
0x18000f662  call    _guard_dispatch_icall
0x18000f667  mov     eax, r13d
0x18000f66a  lock xadd [r14+0Ch], eax
0x18000f670  add     eax, r13d
0x18000f673  jnz     short loc_18000F684
0x18000f675  mov     rax, [r14]
0x18000f678  mov     rcx, r14
0x18000f67b  mov     rax, [rax+10h]
0x18000f67f  call    _guard_dispatch_icall
0x18000f684  lea     rcx, [rbp+var_38]
0x18000f688  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000f68d  test    rbx, rbx
0x18000f690  jz      short loc_18000F6A1
0x18000f692  mov     rcx, rbx; Handle
0x18000f695  call    cs:__imp_ZwClose
0x18000f69c  nop     dword ptr [rax+rax+00h]
0x18000f6a1  mov     eax, edi
0x18000f6a3  jmp     loc_18000F61A
0x18000f6a8  test    r14, r14
0x18000f6ab  jz      short loc_18000F6EB
0x18000f6ad  or      r13d, 0FFFFFFFFh
0x18000f6b1  mov     eax, r13d
0x18000f6b4  lock xadd [r14+8], eax
0x18000f6ba  add     eax, r13d
0x18000f6bd  jnz     short loc_18000F6EB
0x18000f6bf  mov     rax, [r14]
0x18000f6c2  mov     rcx, r14
0x18000f6c5  mov     rax, [rax+8]
0x18000f6c9  call    _guard_dispatch_icall
0x18000f6ce  mov     eax, r13d
0x18000f6d1  lock xadd [r14+0Ch], eax
0x18000f6d7  add     eax, r13d
0x18000f6da  jnz     short loc_18000F6EB
0x18000f6dc  mov     rax, [r14]
0x18000f6df  mov     rcx, r14
0x18000f6e2  mov     rax, [rax+10h]
0x18000f6e6  call    _guard_dispatch_icall
0x18000f6eb  lea     rcx, [rbp+var_38]
0x18000f6ef  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000f6f4  test    rbx, rbx
0x18000f6f7  jz      short loc_18000F708
0x18000f6f9  mov     rcx, rbx; Handle
0x18000f6fc  call    cs:__imp_ZwClose
0x18000f703  nop     dword ptr [rax+rax+00h]
0x18000f708  mov     eax, 0C000009Ah
0x18000f70d  jmp     loc_18000F61A
```
