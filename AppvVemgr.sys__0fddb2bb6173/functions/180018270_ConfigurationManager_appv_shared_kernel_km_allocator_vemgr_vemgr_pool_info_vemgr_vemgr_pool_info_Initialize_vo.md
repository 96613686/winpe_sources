# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Initialize(void)

- ea: `0x180018270`
- end: `0x18001847c`
- name: `?Initialize@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJXZ`
- size: `524`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017334`

## callees

- `0x180005178`
- `0x18000c5f4`
- `0x18000e23c`
- `0x18000e588`
- `0x180013668`
- `0x180018270`
- `0x180019b1c`
- `0x18001a024`
- `0x18001a1f4`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800182c7`
- `ntoskrnl!ZwClose` at `0x1800182e3`
- `ntoskrnl!ZwClose` at `0x1800182c7`
- `ntoskrnl!ZwClose` at `0x1800182e3`

## string_xrefs

- `0x18001828f`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Volumes`
- `0x1800182ac`: `Data_Store::validate_store() - Failed to delete user configurations. Error: %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Initialize(
        __int64 a1)
{
  int v2; // eax
  int v3; // ebx
  int v5; // r14d
  void *i; // rax
  __int128 *j; // rbx
  void *k; // rax
  __int128 *m; // rbx
  __int64 n; // rbx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-50h] BYREF
  __int128 v13; // [rsp+28h] [rbp-48h] BYREF
  __int128 *v14; // [rsp+38h] [rbp-38h]
  __int128 *v15; // [rsp+40h] [rbp-30h]
  int v16; // [rsp+48h] [rbp-28h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF
  __int128 *v18; // [rsp+60h] [rbp-10h]
  __int128 *v19; // [rsp+68h] [rbp-8h]
  char v20; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+48h] BYREF

  Handle = 0;
  if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              0,
              L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Volumes",
              &Handle) >= 0 )
  {
    v2 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_all_user_configurations();
    v3 = v2;
    if ( v2 < 0 )
    {
      LogWrite(
        1,
        0,
        L"Data_Store::validate_store() - Failed to delete user configurations. Error: %d.",
        (unsigned int)v2);
      if ( Handle )
        ZwClose(Handle);
      return (unsigned int)v3;
    }
  }
  if ( Handle )
    ZwClose(Handle);
  v12 = 0;
  v15 = &v13;
  v20 = 0;
  v14 = &v13;
  v13 = 0;
  v3 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_packages(
         (__int64)&v12,
         &v20);
  if ( v3 < 0 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v12);
    return (unsigned int)v3;
  }
  v16 = 0;
  v19 = &v17;
  v18 = &v17;
  v17 = 0;
  v5 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_package_groups((__int64)&v16);
  if ( v5 < 0 )
    goto LABEL_34;
  if ( (int *)a1 != &v12 )
  {
    for ( i = *(void **)(a1 + 32);
          i != (void *)(a1 + 8);
          i = (void *)*appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                         (_DWORD *)a1,
                         &v22,
                         (__int64)&Handle) )
    {
      Handle = i;
    }
    for ( j = v15;
          j != &v13
       && (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                 a1,
                 j) >= 0;
          j = (__int128 *)*((_QWORD *)j + 3) )
    {
      ;
    }
  }
  if ( (int *)(a1 + 40) != &v16 )
  {
    for ( k = *(void **)(a1 + 72);
          k != (void *)(a1 + 48);
          k = (void *)*appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                         (_DWORD *)(a1 + 40),
                         &v22,
                         (__int64)&Handle) )
    {
      Handle = k;
    }
    for ( m = v19;
          m != &v17
       && (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                 a1 + 40,
                 m) >= 0;
          m = (__int128 *)*((_QWORD *)m + 3) )
    {
      ;
    }
  }
  *(_BYTE *)(a1 + 104) = v20;
  if ( *(_DWORD *)a1 == v12 && *(_DWORD *)(a1 + 40) == v16 )
  {
    for ( n = *(_QWORD *)(a1 + 72); n != a1 + 48; n = *(_QWORD *)(n + 24) )
    {
      v11 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(
              a1,
              n);
      if ( v11 < 0 )
      {
        v5 = v11;
        break;
      }
    }
LABEL_34:
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v16);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v12);
    return (unsigned int)v5;
  }
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v16);
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v12);
  return 3221225626LL;
}

```

## disassembly

```asm
0x180018270  push    rbp
0x180018272  push    rbx
0x180018273  push    rsi
0x180018274  push    rdi
0x180018275  push    r14
0x180018277  mov     rbp, rsp
0x18001827a  sub     rsp, 70h
0x18001827e  mov     rdi, rcx
0x180018281  mov     [rbp+Handle], 0
0x180018289  xor     ecx, ecx
0x18001828b  lea     r8, [rbp+Handle]
0x18001828f  lea     rdx, aRegistryMachin_6; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180018296  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001829b  test    eax, eax
0x18001829d  js      short loc_1800182DA
0x18001829f  call    ?delete_all_user_configurations@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJXZ; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_all_user_configurations(void)
0x1800182a4  mov     ebx, eax
0x1800182a6  test    eax, eax
0x1800182a8  jns     short loc_1800182DA
0x1800182aa  xor     edx, edx
0x1800182ac  lea     r8, aDataStoreValid; "Data_Store::validate_store() - Failed t"...
0x1800182b3  mov     r9d, eax
0x1800182b6  lea     ecx, [rdx+1]
0x1800182b9  call    LogWrite
0x1800182be  mov     rcx, [rbp+Handle]; Handle
0x1800182c2  test    rcx, rcx
0x1800182c5  jz      short loc_1800182D3
0x1800182c7  call    cs:__imp_ZwClose
0x1800182ce  nop     dword ptr [rax+rax+00h]
0x1800182d3  mov     eax, ebx
0x1800182d5  jmp     loc_180018470
0x1800182da  mov     rcx, [rbp+Handle]; Handle
0x1800182de  test    rcx, rcx
0x1800182e1  jz      short loc_1800182EF
0x1800182e3  call    cs:__imp_ZwClose
0x1800182ea  nop     dword ptr [rax+rax+00h]
0x1800182ef  lea     rax, [rbp+var_48]
0x1800182f3  mov     [rbp+var_50], 0
0x1800182fa  mov     [rbp+var_30], rax
0x1800182fe  lea     rdx, [rbp+arg_8]
0x180018302  lea     rax, [rbp+var_48]
0x180018306  mov     [rbp+arg_8], 0
0x18001830a  xorps   xmm0, xmm0
0x18001830d  mov     [rbp+var_38], rax
0x180018311  lea     rcx, [rbp+var_50]
0x180018315  movdqu  [rbp+var_48], xmm0
0x18001831a  call    ?enum_packages@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEA_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_packages(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &,bool &)
0x18001831f  mov     ebx, eax
0x180018321  test    eax, eax
0x180018323  jns     short loc_180018330
0x180018325  lea     rcx, [rbp+var_50]
0x180018329  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001832e  jmp     short loc_1800182D3
0x180018330  lea     rax, [rbp+var_20]
0x180018334  mov     [rbp+var_28], 0
0x18001833b  mov     [rbp+var_8], rax
0x18001833f  lea     rcx, [rbp+var_28]
0x180018343  lea     rax, [rbp+var_20]
0x180018347  xorps   xmm0, xmm0
0x18001834a  mov     [rbp+var_10], rax
0x18001834e  movdqu  [rbp+var_20], xmm0
0x180018353  call    ?enum_package_groups@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_package_groups(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &)
0x180018358  mov     r14d, eax
0x18001835b  test    eax, eax
0x18001835d  js      loc_180018442
0x180018363  lea     rax, [rbp+var_50]
0x180018367  cmp     rdi, rax
0x18001836a  jz      short loc_1800183B4
0x18001836c  mov     rax, [rdi+20h]
0x180018370  lea     rbx, [rdi+8]
0x180018374  cmp     rax, rbx
0x180018377  jz      short loc_180018392
0x180018379  lea     r8, [rbp+Handle]
0x18001837d  mov     [rbp+Handle], rax
0x180018381  lea     rdx, [rbp+arg_18]
0x180018385  mov     rcx, rdi
0x180018388  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18001838d  mov     rax, [rax]
0x180018390  jmp     short loc_180018374
0x180018392  mov     rbx, [rbp+var_30]
0x180018396  lea     rax, [rbp+var_48]
0x18001839a  cmp     rbx, rax
0x18001839d  jz      short loc_1800183B4
0x18001839f  mov     rdx, rbx
0x1800183a2  mov     rcx, rdi
0x1800183a5  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x1800183aa  test    eax, eax
0x1800183ac  js      short loc_1800183B4
0x1800183ae  mov     rbx, [rbx+18h]
0x1800183b2  jmp     short loc_180018396
0x1800183b4  lea     rsi, [rdi+28h]
0x1800183b8  lea     rax, [rbp+var_28]
0x1800183bc  cmp     rsi, rax
0x1800183bf  jz      short loc_180018409
0x1800183c1  mov     rax, [rsi+20h]
0x1800183c5  lea     rbx, [rsi+8]
0x1800183c9  cmp     rax, rbx
0x1800183cc  jz      short loc_1800183E7
0x1800183ce  lea     r8, [rbp+Handle]
0x1800183d2  mov     [rbp+Handle], rax
0x1800183d6  lea     rdx, [rbp+arg_18]
0x1800183da  mov     rcx, rsi
0x1800183dd  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x1800183e2  mov     rax, [rax]
0x1800183e5  jmp     short loc_1800183C9
0x1800183e7  mov     rbx, [rbp+var_8]
0x1800183eb  lea     rax, [rbp+var_20]
0x1800183ef  cmp     rbx, rax
0x1800183f2  jz      short loc_180018409
0x1800183f4  mov     rdx, rbx
0x1800183f7  mov     rcx, rsi
0x1800183fa  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x1800183ff  test    eax, eax
0x180018401  js      short loc_180018409
0x180018403  mov     rbx, [rbx+18h]
0x180018407  jmp     short loc_1800183EB
0x180018409  mov     al, [rbp+arg_8]
0x18001840c  mov     [rdi+68h], al
0x18001840f  mov     eax, [rbp+var_50]
0x180018412  cmp     [rdi], eax
0x180018414  jnz     short loc_180018459
0x180018416  mov     eax, [rbp+var_28]
0x180018419  cmp     [rsi], eax
0x18001841b  jnz     short loc_180018459
0x18001841d  mov     rbx, [rdi+48h]
0x180018421  lea     rsi, [rdi+30h]
0x180018425  cmp     rbx, rsi
0x180018428  jz      short loc_180018442
0x18001842a  mov     rdx, rbx
0x18001842d  mov     rcx, rdi
0x180018430  call    ?add_package_group_to_package_configuration@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180018435  test    eax, eax
0x180018437  js      short loc_18001843F
0x180018439  mov     rbx, [rbx+18h]
0x18001843d  jmp     short loc_180018425
0x18001843f  mov     r14d, eax
0x180018442  lea     rcx, [rbp+var_28]
0x180018446  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001844b  lea     rcx, [rbp+var_50]
0x18001844f  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180018454  mov     eax, r14d
0x180018457  jmp     short loc_180018470
0x180018459  lea     rcx, [rbp+var_28]
0x18001845d  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180018462  lea     rcx, [rbp+var_50]
0x180018466  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001846b  mov     eax, 0C000009Ah
0x180018470  add     rsp, 70h
0x180018474  pop     r14
0x180018476  pop     rdi
0x180018477  pop     rsi
0x180018478  pop     rbx
0x180018479  pop     rbp
0x18001847a  retn
```
