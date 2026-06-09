# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageGroup(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180012264`
- end: `0x1800124c8`
- name: `?AddPackageGroup@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012924`

## callees

- `0x180002e94`
- `0x18000fd14`
- `0x180012264`
- `0x180013668`
- `0x180014964`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1800122cb`
- `ntoskrnl!EtwActivityIdControl` at `0x1800122cb`
- `ntoskrnl!ExAllocatePool2` at `0x1800123f9`
- `ntoskrnl!ExAllocatePool2` at `0x1800123f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012356`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800123ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012481`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012356`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800123ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012481`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012362`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800123d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001248d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012362`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800123d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001248d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001230e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001230e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800122fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800122fb`

## string_xrefs

- `0x1800123a7`: `ConfigurationManager::AddPackageGroup() - Failed to store package group configuration. group moniker %s. result %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageGroup(
        __int64 a1,
        const UNICODE_STRING ***a2)
{
  const UNICODE_STRING **v4; // rax
  __int64 v5; // rcx
  bool v6; // si
  struct _ERESOURCE *v7; // rcx
  int v9; // eax
  unsigned int v10; // ebp
  const UNICODE_STRING *v11; // r9
  unsigned int v12; // ecx
  wchar_t *Buffer; // r9
  struct _ERESOURCE *v14; // rcx
  const UNICODE_STRING ***Pool2; // rax
  __int64 v16; // rcx
  const UNICODE_STRING ***v17; // rdx
  volatile signed __int32 *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // ebx
  struct _ERESOURCE *v21; // rcx
  const UNICODE_STRING *v22; // [rsp+30h] [rbp-68h] BYREF
  char v23[8]; // [rsp+38h] [rbp-60h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-58h] BYREF

  if ( !*a2 )
    return 3221225485LL;
  v4 = a2[1];
  if ( !v4 || !*((_DWORD *)v4 + 2) )
    return 3221225485LL;
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v5, VEMGR_Add_Package_Group_Start, &ActivityId);
  v6 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v6 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v22 = **a2;
  if ( *(_QWORD *)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
                    a1 + 40,
                    (__int64)v23,
                    &v22) == a1 + 48 )
  {
    v9 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(a2);
    v10 = v9;
    if ( v9 >= 0 )
    {
      Pool2 = (const UNICODE_STRING ***)ExAllocatePool2(256, 32, 1733125462);
      v17 = Pool2;
      if ( Pool2 )
      {
        *Pool2 = *a2;
        v18 = (volatile signed __int32 *)a2[1];
        v17[1] = (const UNICODE_STRING **)v18;
        if ( v18 )
          _InterlockedAdd(v18 + 2, 1u);
        v17[3] = (const UNICODE_STRING **)v17;
        v17[2] = (const UNICODE_STRING **)v17;
        v19 = *(_QWORD *)(a1 + 72);
        ++*(_DWORD *)(a1 + 40);
        v17[3] = (const UNICODE_STRING **)v19;
        v17[2] = (const UNICODE_STRING **)(a1 + 48);
        *(_QWORD *)(v19 + 16) = v17;
        *(_QWORD *)(a1 + 72) = v17;
        v20 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(
                a1,
                (__int64)a2);
      }
      else
      {
        v20 = -1073741670;
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 4) != 0 )
        McTemplateK0_EtwWriteTransfer(v16, VEMGR_Add_Package_Group_Finish, &ActivityId);
      if ( v6 )
      {
        v21 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v21 )
        {
          ExReleaseResourceLite(v21);
          KeLeaveCriticalRegion();
        }
      }
      return v20;
    }
    else
    {
      v11 = **a2;
      v12 = *(_DWORD *)&v11->Length >> 1;
      if ( v12 <= 0xFFFF && (_WORD)v12 )
        Buffer = v11->Buffer;
      else
        Buffer = 0;
      LogWrite(
        1,
        0,
        L"ConfigurationManager::AddPackageGroup() - Failed to store package group configuration. group moniker %s. result %d.",
        Buffer,
        v9);
      if ( v6 )
      {
        v14 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v14 )
        {
          ExReleaseResourceLite(v14);
          KeLeaveCriticalRegion();
        }
      }
      return v10;
    }
  }
  else
  {
    if ( v6 )
    {
      v7 = *(struct _ERESOURCE **)(a1 + 88);
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    return 3221226026LL;
  }
}

```

## disassembly

```asm
0x180012264  mov     [rsp+arg_10], rbx
0x180012269  push    rbp
0x18001226a  push    rsi
0x18001226b  push    rdi
0x18001226c  push    r12
0x18001226e  push    r13
0x180012270  push    r14
0x180012272  push    r15
0x180012274  sub     rsp, 60h
0x180012278  mov     rax, cs:__security_cookie
0x18001227f  xor     rax, rsp
0x180012282  mov     [rsp+98h+var_48], rax
0x180012287  xor     r12d, r12d
0x18001228a  mov     rbx, rdx
0x18001228d  mov     rdi, rcx
0x180012290  cmp     [rdx], r12
0x180012293  jz      loc_18001249D
0x180012299  mov     rax, [rdx+8]
0x18001229d  test    rax, rax
0x1800122a0  jz      loc_18001249D
0x1800122a6  mov     eax, [rax+8]
0x1800122a9  test    eax, eax
0x1800122ab  jz      loc_18001249D
0x1800122b1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800122b8  lea     r13d, [r12+1]
0x1800122bd  lea     rdx, [rsp+98h+ActivityId]; ActivityId
0x1800122c2  mov     ecx, r13d; ControlCode
0x1800122c5  movdqu  xmmword ptr [rsp+98h+ActivityId.Data1], xmm0
0x1800122cb  call    cs:__imp_EtwActivityIdControl
0x1800122d2  nop     dword ptr [rax+rax+00h]
0x1800122d7  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r13b
0x1800122de  jz      short loc_1800122F1
0x1800122e0  lea     r8, [rsp+98h+ActivityId]
0x1800122e5  lea     rdx, VEMGR_Add_Package_Group_Start
0x1800122ec  call    McTemplateK0_EtwWriteTransfer
0x1800122f1  movzx   esi, r12b
0x1800122f5  cmp     [rdi+58h], r12
0x1800122f9  jz      short loc_180012321
0x1800122fb  call    cs:__imp_KeEnterCriticalRegion
0x180012302  nop     dword ptr [rax+rax+00h]
0x180012307  mov     rcx, [rdi+58h]; Resource
0x18001230b  mov     dl, r13b; Wait
0x18001230e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180012315  nop     dword ptr [rax+rax+00h]
0x18001231a  cmp     al, r13b
0x18001231d  cmovz   esi, r13d
0x180012321  mov     rax, [rbx]
0x180012324  lea     r8, [rsp+98h+var_68]
0x180012329  lea     rdx, [rsp+98h+var_60]
0x18001232e  lea     r15, [rdi+30h]
0x180012332  mov     rcx, [rax]
0x180012335  mov     [rsp+98h+var_68], rcx
0x18001233a  lea     rcx, [rdi+28h]
0x18001233e  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180012343  cmp     [rax], r15
0x180012346  jz      short loc_180012378
0x180012348  test    sil, sil
0x18001234b  jz      short loc_18001236E
0x18001234d  mov     rcx, [rdi+58h]; Resource
0x180012351  test    rcx, rcx
0x180012354  jz      short loc_18001236E
0x180012356  call    cs:__imp_ExReleaseResourceLite
0x18001235d  nop     dword ptr [rax+rax+00h]
0x180012362  call    cs:__imp_KeLeaveCriticalRegion
0x180012369  nop     dword ptr [rax+rax+00h]
0x18001236e  mov     eax, 0C000022Ah
0x180012373  jmp     loc_1800124A2
0x180012378  mov     rcx, rbx
0x18001237b  call    ?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180012380  mov     ebp, eax
0x180012382  test    eax, eax
0x180012384  jns     short loc_1800123E9
0x180012386  mov     rcx, [rbx]
0x180012389  mov     r9, [rcx]
0x18001238c  mov     ecx, [r9]
0x18001238f  shr     ecx, 1
0x180012391  cmp     ecx, 0FFFFh
0x180012397  ja      short loc_1800123A4
0x180012399  test    cx, cx
0x18001239c  jz      short loc_1800123A4
0x18001239e  mov     r9, [r9+8]
0x1800123a2  jmp     short loc_1800123A7
0x1800123a4  mov     r9, r12
0x1800123a7  lea     r8, aConfigurationm; "ConfigurationManager::AddPackageGroup()"...
0x1800123ae  mov     [rsp+98h+var_78], ebp
0x1800123b2  xor     edx, edx
0x1800123b4  mov     ecx, r13d
0x1800123b7  call    LogWrite
0x1800123bc  test    sil, sil
0x1800123bf  jz      short loc_1800123E2
0x1800123c1  mov     rcx, [rdi+58h]; Resource
0x1800123c5  test    rcx, rcx
0x1800123c8  jz      short loc_1800123E2
0x1800123ca  call    cs:__imp_ExReleaseResourceLite
0x1800123d1  nop     dword ptr [rax+rax+00h]
0x1800123d6  call    cs:__imp_KeLeaveCriticalRegion
0x1800123dd  nop     dword ptr [rax+rax+00h]
0x1800123e2  mov     eax, ebp
0x1800123e4  jmp     loc_1800124A2
0x1800123e9  mov     edx, 20h ; ' '
0x1800123ee  mov     ecx, 100h
0x1800123f3  mov     r8d, 674D6556h
0x1800123f9  call    cs:__imp_ExAllocatePool2
0x180012400  nop     dword ptr [rax+rax+00h]
0x180012405  mov     rdx, rax
0x180012408  test    rax, rax
0x18001240b  jz      short loc_180012454
0x18001240d  mov     rcx, [rbx]
0x180012410  mov     [rax], rcx
0x180012413  mov     rax, [rbx+8]
0x180012417  mov     [rdx+8], rax
0x18001241b  test    rax, rax
0x18001241e  jz      short loc_180012425
0x180012420  lock add [rax+8], r13d
0x180012425  mov     [rdx+18h], rdx
0x180012429  mov     rcx, rdi
0x18001242c  mov     [rdx+10h], rdx
0x180012430  mov     rax, [rdi+48h]
0x180012434  add     [rdi+28h], r13d
0x180012438  mov     [rdx+18h], rax
0x18001243c  mov     [rdx+10h], r15
0x180012440  mov     [rax+10h], rdx
0x180012444  mov     [rdi+48h], rdx
0x180012448  mov     rdx, rbx
0x18001244b  call    ?add_package_group_to_package_configuration@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180012450  mov     ebx, eax
0x180012452  jmp     short loc_180012459
0x180012454  mov     ebx, 0C000009Ah
0x180012459  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 4
0x180012460  jz      short loc_180012473
0x180012462  lea     r8, [rsp+98h+ActivityId]
0x180012467  lea     rdx, VEMGR_Add_Package_Group_Finish
0x18001246e  call    McTemplateK0_EtwWriteTransfer
0x180012473  test    sil, sil
0x180012476  jz      short loc_180012499
0x180012478  mov     rcx, [rdi+58h]; Resource
0x18001247c  test    rcx, rcx
0x18001247f  jz      short loc_180012499
0x180012481  call    cs:__imp_ExReleaseResourceLite
0x180012488  nop     dword ptr [rax+rax+00h]
0x18001248d  call    cs:__imp_KeLeaveCriticalRegion
0x180012494  nop     dword ptr [rax+rax+00h]
0x180012499  mov     eax, ebx
0x18001249b  jmp     short loc_1800124A2
0x18001249d  mov     eax, 0C000000Dh
0x1800124a2  mov     rcx, [rsp+98h+var_48]
0x1800124a7  xor     rcx, rsp; StackCookie
0x1800124aa  call    __security_check_cookie
0x1800124af  mov     rbx, [rsp+98h+arg_10]
0x1800124b7  add     rsp, 60h
0x1800124bb  pop     r15
0x1800124bd  pop     r14
0x1800124bf  pop     r13
0x1800124c1  pop     r12
0x1800124c3  pop     rdi
0x1800124c4  pop     rsi
0x1800124c5  pop     rbp
0x1800124c6  retn
```
