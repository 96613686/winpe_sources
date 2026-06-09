# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackage(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180012004`
- end: `0x18001225e`
- name: `?AddPackage@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012804`

## callees

- `0x180002e94`
- `0x18000fd14`
- `0x180012004`
- `0x1800147fc`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x18001206c`
- `ntoskrnl!EtwActivityIdControl` at `0x18001206c`
- `ntoskrnl!ExAllocatePool2` at `0x180012199`
- `ntoskrnl!ExAllocatePool2` at `0x180012199`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800120f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001216a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012216`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800120f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001216a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180012216`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012176`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012222`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012176`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180012222`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800120af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800120af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001209c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001209c`

## string_xrefs

- `0x180012147`: `ConfigurationManager::AddPackage() - Failed to store package configuration. package moniker %s. result %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackage(
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
  const UNICODE_STRING **v16; // rcx
  const UNICODE_STRING ***v17; // rdx
  volatile signed __int32 *v18; // rax
  unsigned int v19; // edi
  __int64 v20; // rax
  struct _ERESOURCE *v21; // rcx
  const UNICODE_STRING *v22; // [rsp+30h] [rbp-58h] BYREF
  char v23[8]; // [rsp+38h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-48h] BYREF

  if ( !*a2 )
    return 3221225485LL;
  v4 = a2[1];
  if ( !v4 || !*((_DWORD *)v4 + 2) )
    return 3221225485LL;
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v5, VEMGR_Add_Package_Start, &ActivityId);
  v6 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v6 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v22 = **a2;
  if ( *(_QWORD *)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
                    a1,
                    (__int64)v23,
                    &v22) == a1 + 8 )
  {
    v9 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(a2);
    v10 = v9;
    if ( v9 >= 0 )
    {
      Pool2 = (const UNICODE_STRING ***)ExAllocatePool2(256, 32, 1733125462);
      v17 = Pool2;
      if ( Pool2 )
      {
        v16 = *a2;
        *Pool2 = *a2;
        v18 = (volatile signed __int32 *)a2[1];
        v17[1] = (const UNICODE_STRING **)v18;
        if ( v18 )
          _InterlockedAdd(v18 + 2, 1u);
        v17[3] = (const UNICODE_STRING **)v17;
        v19 = 0;
        v17[2] = (const UNICODE_STRING **)v17;
        v20 = *(_QWORD *)(a1 + 32);
        ++*(_DWORD *)a1;
        v17[3] = (const UNICODE_STRING **)v20;
        v17[2] = (const UNICODE_STRING **)(a1 + 8);
        *(_QWORD *)(v20 + 16) = v17;
        *(_QWORD *)(a1 + 32) = v17;
      }
      else
      {
        v19 = -1073741670;
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(v16, VEMGR_Add_Package_Finish, &ActivityId);
      if ( v6 )
      {
        v21 = *(struct _ERESOURCE **)(a1 + 88);
        if ( v21 )
        {
          ExReleaseResourceLite(v21);
          KeLeaveCriticalRegion();
        }
      }
      return v19;
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
        L"ConfigurationManager::AddPackage() - Failed to store package configuration. package moniker %s. result %d.",
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
0x180012004  mov     [rsp+arg_10], rbx
0x180012009  mov     [rsp+arg_18], rbp
0x18001200e  push    rsi
0x18001200f  push    rdi
0x180012010  push    r12
0x180012012  push    r14
0x180012014  push    r15
0x180012016  sub     rsp, 60h
0x18001201a  mov     rax, cs:__security_cookie
0x180012021  xor     rax, rsp
0x180012024  mov     [rsp+88h+var_38], rax
0x180012029  xor     r15d, r15d
0x18001202c  mov     rdi, rdx
0x18001202f  mov     rbx, rcx
0x180012032  cmp     [rdx], r15
0x180012035  jz      loc_180012232
0x18001203b  mov     rax, [rdx+8]
0x18001203f  test    rax, rax
0x180012042  jz      loc_180012232
0x180012048  mov     eax, [rax+8]
0x18001204b  test    eax, eax
0x18001204d  jz      loc_180012232
0x180012053  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001205a  lea     r12d, [r15+1]
0x18001205e  lea     rdx, [rsp+88h+ActivityId]; ActivityId
0x180012063  mov     ecx, r12d; ControlCode
0x180012066  movdqu  xmmword ptr [rsp+88h+ActivityId.Data1], xmm0
0x18001206c  call    cs:__imp_EtwActivityIdControl
0x180012073  nop     dword ptr [rax+rax+00h]
0x180012078  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x18001207f  jz      short loc_180012092
0x180012081  lea     r8, [rsp+88h+ActivityId]
0x180012086  lea     rdx, VEMGR_Add_Package_Start
0x18001208d  call    McTemplateK0_EtwWriteTransfer
0x180012092  movzx   esi, r15b
0x180012096  cmp     [rbx+58h], r15
0x18001209a  jz      short loc_1800120C2
0x18001209c  call    cs:__imp_KeEnterCriticalRegion
0x1800120a3  nop     dword ptr [rax+rax+00h]
0x1800120a8  mov     rcx, [rbx+58h]; Resource
0x1800120ac  mov     dl, r12b; Wait
0x1800120af  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800120b6  nop     dword ptr [rax+rax+00h]
0x1800120bb  cmp     al, r12b
0x1800120be  cmovz   esi, r12d
0x1800120c2  mov     rax, [rdi]
0x1800120c5  lea     r8, [rsp+88h+var_58]
0x1800120ca  lea     rdx, [rsp+88h+var_50]
0x1800120cf  lea     r14, [rbx+8]
0x1800120d3  mov     rcx, [rax]
0x1800120d6  mov     [rsp+88h+var_58], rcx
0x1800120db  mov     rcx, rbx
0x1800120de  call    ??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x1800120e3  cmp     [rax], r14
0x1800120e6  jz      short loc_180012118
0x1800120e8  test    sil, sil
0x1800120eb  jz      short loc_18001210E
0x1800120ed  mov     rcx, [rbx+58h]; Resource
0x1800120f1  test    rcx, rcx
0x1800120f4  jz      short loc_18001210E
0x1800120f6  call    cs:__imp_ExReleaseResourceLite
0x1800120fd  nop     dword ptr [rax+rax+00h]
0x180012102  call    cs:__imp_KeLeaveCriticalRegion
0x180012109  nop     dword ptr [rax+rax+00h]
0x18001210e  mov     eax, 0C000022Ah
0x180012113  jmp     loc_180012237
0x180012118  mov     rcx, rdi
0x18001211b  call    ?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180012120  mov     ebp, eax
0x180012122  test    eax, eax
0x180012124  jns     short loc_180012189
0x180012126  mov     rcx, [rdi]
0x180012129  mov     r9, [rcx]
0x18001212c  mov     ecx, [r9]
0x18001212f  shr     ecx, 1
0x180012131  cmp     ecx, 0FFFFh
0x180012137  ja      short loc_180012144
0x180012139  test    cx, cx
0x18001213c  jz      short loc_180012144
0x18001213e  mov     r9, [r9+8]
0x180012142  jmp     short loc_180012147
0x180012144  mov     r9, r15
0x180012147  lea     r8, aConfigurationm_10; "ConfigurationManager::AddPackage() - Fa"...
0x18001214e  mov     [rsp+88h+var_68], ebp
0x180012152  xor     edx, edx
0x180012154  mov     ecx, r12d
0x180012157  call    LogWrite
0x18001215c  test    sil, sil
0x18001215f  jz      short loc_180012182
0x180012161  mov     rcx, [rbx+58h]; Resource
0x180012165  test    rcx, rcx
0x180012168  jz      short loc_180012182
0x18001216a  call    cs:__imp_ExReleaseResourceLite
0x180012171  nop     dword ptr [rax+rax+00h]
0x180012176  call    cs:__imp_KeLeaveCriticalRegion
0x18001217d  nop     dword ptr [rax+rax+00h]
0x180012182  mov     eax, ebp
0x180012184  jmp     loc_180012237
0x180012189  mov     edx, 20h ; ' '
0x18001218e  mov     ecx, 100h
0x180012193  mov     r8d, 674D6556h
0x180012199  call    cs:__imp_ExAllocatePool2
0x1800121a0  nop     dword ptr [rax+rax+00h]
0x1800121a5  mov     rdx, rax
0x1800121a8  test    rax, rax
0x1800121ab  jz      short loc_1800121E9
0x1800121ad  mov     rcx, [rdi]
0x1800121b0  mov     [rax], rcx
0x1800121b3  mov     rax, [rdi+8]
0x1800121b7  mov     [rdx+8], rax
0x1800121bb  test    rax, rax
0x1800121be  jz      short loc_1800121C5
0x1800121c0  lock add [rax+8], r12d
0x1800121c5  mov     [rdx+18h], rdx
0x1800121c9  mov     edi, r15d
0x1800121cc  mov     [rdx+10h], rdx
0x1800121d0  mov     rax, [rbx+20h]
0x1800121d4  add     [rbx], r12d
0x1800121d7  mov     [rdx+18h], rax
0x1800121db  mov     [rdx+10h], r14
0x1800121df  mov     [rax+10h], rdx
0x1800121e3  mov     [rbx+20h], rdx
0x1800121e7  jmp     short loc_1800121EE
0x1800121e9  mov     edi, 0C000009Ah
0x1800121ee  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x1800121f5  jz      short loc_180012208
0x1800121f7  lea     r8, [rsp+88h+ActivityId]
0x1800121fc  lea     rdx, VEMGR_Add_Package_Finish
0x180012203  call    McTemplateK0_EtwWriteTransfer
0x180012208  test    sil, sil
0x18001220b  jz      short loc_18001222E
0x18001220d  mov     rcx, [rbx+58h]; Resource
0x180012211  test    rcx, rcx
0x180012214  jz      short loc_18001222E
0x180012216  call    cs:__imp_ExReleaseResourceLite
0x18001221d  nop     dword ptr [rax+rax+00h]
0x180012222  call    cs:__imp_KeLeaveCriticalRegion
0x180012229  nop     dword ptr [rax+rax+00h]
0x18001222e  mov     eax, edi
0x180012230  jmp     short loc_180012237
0x180012232  mov     eax, 0C000000Dh
0x180012237  mov     rcx, [rsp+88h+var_38]
0x18001223c  xor     rcx, rsp; StackCookie
0x18001223f  call    __security_check_cookie
0x180012244  lea     r11, [rsp+88h+var_28]
0x180012249  mov     rbx, [r11+40h]
0x18001224d  mov     rbp, [r11+48h]
0x180012251  mov     rsp, r11
0x180012254  pop     r15
0x180012256  pop     r14
0x180012258  pop     r12
0x18001225a  pop     rdi
0x18001225b  pop     rsi
0x18001225c  retn
```
