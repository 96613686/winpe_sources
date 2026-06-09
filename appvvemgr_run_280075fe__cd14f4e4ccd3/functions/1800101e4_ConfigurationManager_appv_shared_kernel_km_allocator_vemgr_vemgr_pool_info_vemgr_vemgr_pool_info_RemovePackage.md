# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x1800101e4`
- end: `0x18001036d`
- name: `??$RemovePackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012ebc`

## callees

- `0x180002e94`
- `0x18000c5f4`
- `0x1800101e4`
- `0x1800141d0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1800102a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800102f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001033a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800102a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800102f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001033a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800102b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010302`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010346`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800102b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010302`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010346`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010252`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010252`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001023b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001023b`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING *a2)
{
  unsigned int v4; // ecx
  __int16 v5; // dx
  __int16 v6; // ax
  bool v7; // di
  unsigned int v8; // ecx
  bool v9; // cc
  __int16 v10; // dx
  __int16 v11; // ax
  __int64 Buffer; // rcx
  struct _ERESOURCE *v13; // rcx
  struct _ERESOURCE *v15; // rcx
  struct _ERESOURCE *v16; // rcx
  const UNICODE_STRING *v17; // [rsp+58h] [rbp+10h] BYREF
  const UNICODE_STRING *v18; // [rsp+60h] [rbp+18h] BYREF

  v4 = *(_DWORD *)&a2->Length >> 1;
  if ( v4 > 0xFFFF )
    v5 = -1;
  else
    v5 = *(_DWORD *)&a2->Length >> 1;
  v6 = 0;
  if ( v4 <= 0xFFFF )
    v6 = v5;
  if ( !v6 || !a2->Buffer )
    return 3221225485LL;
  v7 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v7 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v8 = *(_DWORD *)&a2->Length >> 1;
  v9 = v8 <= 0xFFFF;
  if ( v8 > 0xFFFF )
    v10 = -1;
  else
    v10 = *(_DWORD *)&a2->Length >> 1;
  v11 = 0;
  Buffer = 0;
  if ( v9 )
    v11 = v10;
  if ( v11 )
    Buffer = (__int64)a2->Buffer;
  if ( (unsigned int)Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(Buffer) == -1073740024 )
  {
    if ( v7 )
    {
      v13 = *(struct _ERESOURCE **)(a1 + 88);
      if ( v13 )
      {
        ExReleaseResourceLite(v13);
        KeLeaveCriticalRegion();
      }
    }
    return 3221227272LL;
  }
  else
  {
    v17 = a2;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
      a1,
      (__int64)&v18,
      &v17);
    if ( v18 == (const UNICODE_STRING *)(a1 + 8) )
    {
      if ( v7 )
      {
        v15 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v15 )
        {
          ExReleaseResourceLite(v15);
          KeLeaveCriticalRegion();
        }
      }
      return 3221225524LL;
    }
    else
    {
      v17 = v18;
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
        (_DWORD *)a1,
        &v18,
        (__int64)&v17);
      if ( v7 )
      {
        v16 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v16 )
        {
          ExReleaseResourceLite(v16);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800101e4  mov     [rsp+arg_0], rbx
0x1800101e9  push    rbp
0x1800101ea  push    rsi
0x1800101eb  push    rdi
0x1800101ec  push    r14
0x1800101ee  push    r15
0x1800101f0  sub     rsp, 20h
0x1800101f4  mov     rbx, rcx
0x1800101f7  mov     r15d, 0FFFFh
0x1800101fd  mov     ecx, [rdx]
0x1800101ff  mov     rsi, rdx
0x180010202  shr     ecx, 1
0x180010204  cmp     ecx, r15d
0x180010207  ja      short loc_18001020E
0x180010209  movzx   edx, cx
0x18001020c  jmp     short loc_180010211
0x18001020e  mov     edx, r15d
0x180010211  xor     r14d, r14d
0x180010214  cmp     ecx, r15d
0x180010217  mov     eax, r14d
0x18001021a  cmovbe  ax, dx
0x18001021e  test    ax, ax
0x180010221  jz      loc_180010356
0x180010227  cmp     [rsi+8], r14
0x18001022b  jz      loc_180010356
0x180010231  movzx   edi, r14b
0x180010235  cmp     [rbx+58h], r14
0x180010239  jz      short loc_180010264
0x18001023b  call    cs:__imp_KeEnterCriticalRegion
0x180010242  nop     dword ptr [rax+rax+00h]
0x180010247  mov     rcx, [rbx+58h]; Resource
0x18001024b  lea     ebp, [r14+1]
0x18001024f  mov     dl, bpl; Wait
0x180010252  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010259  nop     dword ptr [rax+rax+00h]
0x18001025e  cmp     al, bpl
0x180010261  cmovz   edi, ebp
0x180010264  mov     ecx, [rsi]
0x180010266  shr     ecx, 1
0x180010268  cmp     ecx, r15d
0x18001026b  ja      short loc_180010272
0x18001026d  movzx   edx, cx
0x180010270  jmp     short loc_180010275
0x180010272  mov     edx, r15d
0x180010275  mov     eax, r14d
0x180010278  mov     rcx, r14
0x18001027b  cmovbe  ax, dx
0x18001027f  test    ax, ax
0x180010282  jz      short loc_180010288
0x180010284  mov     rcx, [rsi+8]
0x180010288  call    ?remove_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package(wchar_t const *)
0x18001028d  mov     ebp, 0C0000708h
0x180010292  cmp     eax, ebp
0x180010294  jnz     short loc_1800102C3
0x180010296  test    dil, dil
0x180010299  jz      short loc_1800102BC
0x18001029b  mov     rcx, [rbx+58h]; Resource
0x18001029f  test    rcx, rcx
0x1800102a2  jz      short loc_1800102BC
0x1800102a4  call    cs:__imp_ExReleaseResourceLite
0x1800102ab  nop     dword ptr [rax+rax+00h]
0x1800102b0  call    cs:__imp_KeLeaveCriticalRegion
0x1800102b7  nop     dword ptr [rax+rax+00h]
0x1800102bc  mov     eax, ebp
0x1800102be  jmp     loc_18001035B
0x1800102c3  lea     r8, [rsp+48h+arg_8]
0x1800102c8  mov     [rsp+48h+arg_8], rsi
0x1800102cd  lea     rdx, [rsp+48h+arg_10]
0x1800102d2  mov     rcx, rbx
0x1800102d5  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800102da  mov     rax, [rsp+48h+arg_10]
0x1800102df  lea     rcx, [rbx+8]
0x1800102e3  cmp     rax, rcx
0x1800102e6  jnz     short loc_180010315
0x1800102e8  test    dil, dil
0x1800102eb  jz      short loc_18001030E
0x1800102ed  mov     rcx, [rbx+58h]; Resource
0x1800102f1  test    rcx, rcx
0x1800102f4  jz      short loc_18001030E
0x1800102f6  call    cs:__imp_ExReleaseResourceLite
0x1800102fd  nop     dword ptr [rax+rax+00h]
0x180010302  call    cs:__imp_KeLeaveCriticalRegion
0x180010309  nop     dword ptr [rax+rax+00h]
0x18001030e  mov     eax, 0C0000034h
0x180010313  jmp     short loc_18001035B
0x180010315  lea     r8, [rsp+48h+arg_8]
0x18001031a  mov     [rsp+48h+arg_8], rax
0x18001031f  lea     rdx, [rsp+48h+arg_10]
0x180010324  mov     rcx, rbx
0x180010327  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18001032c  test    dil, dil
0x18001032f  jz      short loc_180010352
0x180010331  mov     rcx, [rbx+58h]; Resource
0x180010335  test    rcx, rcx
0x180010338  jz      short loc_180010352
0x18001033a  call    cs:__imp_ExReleaseResourceLite
0x180010341  nop     dword ptr [rax+rax+00h]
0x180010346  call    cs:__imp_KeLeaveCriticalRegion
0x18001034d  nop     dword ptr [rax+rax+00h]
0x180010352  xor     eax, eax
0x180010354  jmp     short loc_18001035B
0x180010356  mov     eax, 0C000000Dh
0x18001035b  mov     rbx, [rsp+48h+arg_0]
0x180010360  add     rsp, 20h
0x180010364  pop     r15
0x180010366  pop     r14
0x180010368  pop     rdi
0x180010369  pop     rsi
0x18001036a  pop     rbp
0x18001036b  retn
```
