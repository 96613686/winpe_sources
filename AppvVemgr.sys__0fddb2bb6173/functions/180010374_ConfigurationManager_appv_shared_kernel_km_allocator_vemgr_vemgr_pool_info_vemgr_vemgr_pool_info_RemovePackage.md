# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x180010374`
- end: `0x1800105eb`
- name: `??$RemovePackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012fd4`

## callees

- `0x180002e94`
- `0x18000c5f4`
- `0x18000fd14`
- `0x180010374`
- `0x180014338`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1800103ea`
- `ntoskrnl!EtwActivityIdControl` at `0x1800103ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001047d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800104cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800105a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001047d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800104cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800105a5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010489`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800104d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800105b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010489`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800104d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800105b1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001042c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001042c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010419`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010419`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemovePackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING *a2)
{
  unsigned int v4; // ecx
  __int16 v5; // dx
  __int16 v6; // ax
  __int64 v7; // rcx
  bool v8; // r14
  unsigned int v9; // ecx
  bool v10; // cc
  __int64 v11; // rdx
  __int16 v12; // ax
  wchar_t *Buffer; // rcx
  struct _ERESOURCE *v14; // rcx
  const UNICODE_STRING *v16; // r15
  struct _ERESOURCE *v17; // rcx
  __int64 i; // rbx
  const UNICODE_STRING *v19; // rdi
  const UNICODE_STRING **v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  struct _ERESOURCE *v23; // rcx
  const UNICODE_STRING *v24; // [rsp+20h] [rbp-40h] BYREF
  const UNICODE_STRING *v25; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v26[8]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v27[8]; // [rsp+38h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-20h] BYREF

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
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v7, VEMGR_Remove_Package_Group_Start, &ActivityId);
  v8 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v8 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v9 = *(_DWORD *)&a2->Length >> 1;
  v10 = v9 <= 0xFFFF;
  if ( v9 > 0xFFFF )
    v11 = 0xFFFF;
  else
    v11 = (unsigned __int16)v9;
  v12 = 0;
  Buffer = 0;
  if ( v10 )
    v12 = v11;
  if ( v12 )
    Buffer = a2->Buffer;
  if ( (unsigned int)Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(
                       Buffer,
                       v11) == -1073740024 )
  {
    if ( v8 )
    {
      v14 = *(struct _ERESOURCE **)(a1 + 88);
      if ( v14 )
      {
        ExReleaseResourceLite(v14);
        KeLeaveCriticalRegion();
      }
    }
    return 3221227272LL;
  }
  else
  {
    v25 = a2;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
      a1 + 40,
      (__int64)&v24,
      &v25);
    v16 = v24;
    if ( v24 == (const UNICODE_STRING *)(a1 + 48) )
    {
      if ( v8 )
      {
        v17 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v17 )
        {
          ExReleaseResourceLite(v17);
          KeLeaveCriticalRegion();
        }
      }
      return 3221225524LL;
    }
    else
    {
      for ( i = *(_QWORD *)(*(_QWORD *)&v24->Length + 48LL); i != *(_QWORD *)&v16->Length + 24LL; i = *(_QWORD *)(i + 24) )
      {
        v24 = *(const UNICODE_STRING **)i;
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
          a1,
          (__int64)&v25,
          &v24);
        v19 = v25;
        if ( v25 != (const UNICODE_STRING *)(a1 + 8) )
        {
          v24 = **(const UNICODE_STRING ***)&v16->Length;
          v20 = (const UNICODE_STRING **)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
                                           *(_QWORD *)&v25->Length + 96LL,
                                           (__int64)v27,
                                           &v24);
          v21 = *(_QWORD *)&v19->Length + 96LL;
          if ( *v20 != (const UNICODE_STRING *)(*(_QWORD *)&v19->Length + 104LL) )
          {
            v24 = *v20;
            appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
              v21,
              v26,
              &v24);
          }
        }
      }
      v24 = v16;
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
        a1 + 40,
        v26,
        &v24);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(v22, VEMGR_Remove_Package_Group_Finish, &ActivityId);
      if ( v8 )
      {
        v23 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v23 )
        {
          ExReleaseResourceLite(v23);
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
0x180010374  mov     [rsp-38h+arg_10], rbx
0x180010379  push    rbp
0x18001037a  push    rsi
0x18001037b  push    rdi
0x18001037c  push    r12
0x18001037e  push    r13
0x180010380  push    r14
0x180010382  push    r15
0x180010384  mov     rbp, rsp
0x180010387  sub     rsp, 60h
0x18001038b  mov     rax, cs:__security_cookie
0x180010392  xor     rax, rsp
0x180010395  mov     [rbp+var_10], rax
0x180010399  mov     rsi, rcx
0x18001039c  mov     edi, 0FFFFh
0x1800103a1  mov     ecx, [rdx]
0x1800103a3  mov     rbx, rdx
0x1800103a6  shr     ecx, 1
0x1800103a8  cmp     ecx, edi
0x1800103aa  ja      short loc_1800103B1
0x1800103ac  movzx   edx, cx
0x1800103af  jmp     short loc_1800103B3
0x1800103b1  mov     edx, edi
0x1800103b3  xor     r12d, r12d
0x1800103b6  cmp     ecx, edi
0x1800103b8  mov     eax, r12d
0x1800103bb  cmovbe  ax, dx
0x1800103bf  test    ax, ax
0x1800103c2  jz      loc_1800105C1
0x1800103c8  cmp     [rbx+8], r12
0x1800103cc  jz      loc_1800105C1
0x1800103d2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800103d9  lea     r15d, [r12+1]
0x1800103de  lea     rdx, [rbp+ActivityId]; ActivityId
0x1800103e2  mov     ecx, r15d; ControlCode
0x1800103e5  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1800103ea  call    cs:__imp_EtwActivityIdControl
0x1800103f1  nop     dword ptr [rax+rax+00h]
0x1800103f6  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r15b
0x1800103fd  jz      short loc_18001040F
0x1800103ff  lea     r8, [rbp+ActivityId]
0x180010403  lea     rdx, VEMGR_Remove_Package_Group_Start
0x18001040a  call    McTemplateK0_EtwWriteTransfer
0x18001040f  movzx   r14d, r12b
0x180010413  cmp     [rsi+58h], r12
0x180010417  jz      short loc_18001043F
0x180010419  call    cs:__imp_KeEnterCriticalRegion
0x180010420  nop     dword ptr [rax+rax+00h]
0x180010425  mov     rcx, [rsi+58h]; Resource
0x180010429  mov     dl, r15b; Wait
0x18001042c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010433  nop     dword ptr [rax+rax+00h]
0x180010438  cmp     al, r15b
0x18001043b  cmovz   r14d, r15d
0x18001043f  mov     ecx, [rbx]
0x180010441  shr     ecx, 1
0x180010443  cmp     ecx, edi
0x180010445  ja      short loc_18001044C
0x180010447  movzx   edx, cx
0x18001044a  jmp     short loc_18001044E
0x18001044c  mov     edx, edi
0x18001044e  mov     eax, r12d
0x180010451  mov     rcx, r12
0x180010454  cmovbe  ax, dx
0x180010458  test    ax, ax
0x18001045b  jz      short loc_180010461
0x18001045d  mov     rcx, [rbx+8]
0x180010461  call    ?remove_package_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(wchar_t const *)
0x180010466  mov     edi, 0C0000708h
0x18001046b  cmp     eax, edi
0x18001046d  jnz     short loc_18001049C
0x18001046f  test    r14b, r14b
0x180010472  jz      short loc_180010495
0x180010474  mov     rcx, [rsi+58h]; Resource
0x180010478  test    rcx, rcx
0x18001047b  jz      short loc_180010495
0x18001047d  call    cs:__imp_ExReleaseResourceLite
0x180010484  nop     dword ptr [rax+rax+00h]
0x180010489  call    cs:__imp_KeLeaveCriticalRegion
0x180010490  nop     dword ptr [rax+rax+00h]
0x180010495  mov     eax, edi
0x180010497  jmp     loc_1800105C6
0x18001049c  lea     r8, [rbp+var_38]
0x1800104a0  mov     [rbp+var_38], rbx
0x1800104a4  lea     rdx, [rbp+var_40]
0x1800104a8  lea     rcx, [rsi+28h]
0x1800104ac  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800104b1  mov     r15, [rbp+var_40]
0x1800104b5  lea     rax, [rsi+30h]
0x1800104b9  cmp     r15, rax
0x1800104bc  jnz     short loc_1800104EE
0x1800104be  test    r14b, r14b
0x1800104c1  jz      short loc_1800104E4
0x1800104c3  mov     rcx, [rsi+58h]; Resource
0x1800104c7  test    rcx, rcx
0x1800104ca  jz      short loc_1800104E4
0x1800104cc  call    cs:__imp_ExReleaseResourceLite
0x1800104d3  nop     dword ptr [rax+rax+00h]
0x1800104d8  call    cs:__imp_KeLeaveCriticalRegion
0x1800104df  nop     dword ptr [rax+rax+00h]
0x1800104e4  mov     eax, 0C0000034h
0x1800104e9  jmp     loc_1800105C6
0x1800104ee  mov     rbx, [r15]
0x1800104f1  mov     rbx, [rbx+30h]
0x1800104f5  mov     rax, [r15]
0x1800104f8  lea     r8, [rbp+var_40]
0x1800104fc  add     rax, 18h
0x180010500  cmp     rbx, rax
0x180010503  jz      short loc_18001056D
0x180010505  mov     rax, [rbx]
0x180010508  lea     rdx, [rbp+var_38]
0x18001050c  mov     rcx, rsi
0x18001050f  mov     [rbp+var_40], rax
0x180010513  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180010518  mov     rdi, [rbp+var_38]
0x18001051c  lea     rax, [rsi+8]
0x180010520  cmp     rdi, rax
0x180010523  jz      short loc_180010567
0x180010525  mov     rax, [r15]
0x180010528  lea     r8, [rbp+var_40]
0x18001052c  lea     rdx, [rbp+var_28]
0x180010530  mov     rcx, [rax]
0x180010533  mov     [rbp+var_40], rcx
0x180010537  mov     rcx, [rdi]
0x18001053a  add     rcx, 60h ; '`'
0x18001053e  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180010543  mov     rcx, [rdi]
0x180010546  add     rcx, 60h ; '`'
0x18001054a  mov     rdx, [rax]
0x18001054d  lea     rax, [rcx+8]
0x180010551  cmp     rdx, rax
0x180010554  jz      short loc_180010567
0x180010556  mov     [rbp+var_40], rdx
0x18001055a  lea     r8, [rbp+var_40]
0x18001055e  lea     rdx, [rbp+var_30]
0x180010562  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x180010567  mov     rbx, [rbx+18h]
0x18001056b  jmp     short loc_1800104F5
0x18001056d  lea     rdx, [rbp+var_30]
0x180010571  mov     [rbp+var_40], r15
0x180010575  lea     rcx, [rsi+28h]
0x180010579  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x18001057e  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x180010585  jz      short loc_180010597
0x180010587  lea     r8, [rbp+ActivityId]
0x18001058b  lea     rdx, VEMGR_Remove_Package_Group_Finish
0x180010592  call    McTemplateK0_EtwWriteTransfer
0x180010597  test    r14b, r14b
0x18001059a  jz      short loc_1800105BD
0x18001059c  mov     rcx, [rsi+58h]; Resource
0x1800105a0  test    rcx, rcx
0x1800105a3  jz      short loc_1800105BD
0x1800105a5  call    cs:__imp_ExReleaseResourceLite
0x1800105ac  nop     dword ptr [rax+rax+00h]
0x1800105b1  call    cs:__imp_KeLeaveCriticalRegion
0x1800105b8  nop     dword ptr [rax+rax+00h]
0x1800105bd  xor     eax, eax
0x1800105bf  jmp     short loc_1800105C6
0x1800105c1  mov     eax, 0C000000Dh
0x1800105c6  mov     rcx, [rbp+var_10]
0x1800105ca  xor     rcx, rsp; StackCookie
0x1800105cd  call    __security_check_cookie
0x1800105d2  mov     rbx, [rsp+60h+arg_10]
0x1800105da  add     rsp, 60h
0x1800105de  pop     r15
0x1800105e0  pop     r14
0x1800105e2  pop     r13
0x1800105e4  pop     r12
0x1800105e6  pop     rdi
0x1800105e7  pop     rsi
0x1800105e8  pop     rbp
0x1800105e9  retn
```
