# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUser(kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x1800124d0`
- end: `0x18001266a`
- name: `?AddUser@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012a2c`

## callees

- `0x18000fd14`
- `0x1800124d0`
- `0x180014acc`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x18001252f`
- `ntoskrnl!EtwActivityIdControl` at `0x18001252f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001262e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001262e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001263a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001263a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180012572`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180012572`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001255f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001255f`

## string_xrefs

- `0x1800125f3`: `ConfigurationManager::AddUser() - Failed to store user configuration. package moniker %s. group moniker %s. user sid %s. result %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUser(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  bool v6; // di
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // rcx
  unsigned int v10; // edx
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // r9
  struct _ERESOURCE *v16; // rcx
  int v18; // [rsp+30h] [rbp-68h]
  GUID ActivityId; // [rsp+40h] [rbp-58h] BYREF

  if ( !*a2 )
    return 3221225485LL;
  v4 = a2[1];
  if ( !v4 || !*(_DWORD *)(v4 + 8) )
    return 3221225485LL;
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v5, VEMGR_Add_User_Start, &ActivityId);
  v6 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v6 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v8 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(a2);
  if ( v8 < 0 )
  {
    v9 = *a2;
    v10 = *(_DWORD *)(*a2 + 48LL) >> 1;
    if ( v10 <= 0xFFFF && (_WORD)v10 )
      v11 = *(_QWORD *)(v9 + 56);
    else
      v11 = 0;
    v12 = *(_DWORD *)(v9 + 16) >> 1;
    if ( v12 <= 0xFFFF && (_WORD)v12 )
      v13 = *(_QWORD *)(v9 + 24);
    else
      v13 = 0;
    v14 = **(_DWORD **)v9 >> 1;
    if ( v14 <= 0xFFFF && (_WORD)v14 )
      v15 = *(_QWORD *)(*(_QWORD *)v9 + 8LL);
    else
      v15 = 0;
    v18 = v8;
    LogWrite(
      1,
      0,
      L"ConfigurationManager::AddUser() - Failed to store user configuration. package moniker %s. group moniker %s. user s"
       "id %s. result %d.",
      v15,
      v13,
      v11,
      v18);
  }
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v7, VEMGR_Add_User_Finish, &ActivityId);
  if ( v6 )
  {
    v16 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v16 )
    {
      ExReleaseResourceLite(v16);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800124d0  push    rbx
0x1800124d2  push    rbp
0x1800124d3  push    rsi
0x1800124d4  push    rdi
0x1800124d5  push    r14
0x1800124d7  push    r15
0x1800124d9  sub     rsp, 68h
0x1800124dd  mov     rax, cs:__security_cookie
0x1800124e4  xor     rax, rsp
0x1800124e7  mov     [rsp+98h+var_48], rax
0x1800124ec  xor     r14d, r14d
0x1800124ef  mov     rbx, rdx
0x1800124f2  mov     rbp, rcx
0x1800124f5  cmp     [rdx], r14
0x1800124f8  jz      loc_18001264A
0x1800124fe  mov     rax, [rdx+8]
0x180012502  test    rax, rax
0x180012505  jz      loc_18001264A
0x18001250b  mov     eax, [rax+8]
0x18001250e  test    eax, eax
0x180012510  jz      loc_18001264A
0x180012516  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001251d  lea     r15d, [r14+1]
0x180012521  lea     rdx, [rsp+98h+ActivityId]; ActivityId
0x180012526  mov     ecx, r15d; ControlCode
0x180012529  movdqu  xmmword ptr [rsp+98h+ActivityId.Data1], xmm0
0x18001252f  call    cs:__imp_EtwActivityIdControl
0x180012536  nop     dword ptr [rax+rax+00h]
0x18001253b  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r15b
0x180012542  jz      short loc_180012555
0x180012544  lea     r8, [rsp+98h+ActivityId]
0x180012549  lea     rdx, VEMGR_Add_User_Start
0x180012550  call    McTemplateK0_EtwWriteTransfer
0x180012555  movzx   edi, r14b
0x180012559  cmp     [rbp+58h], r14
0x18001255d  jz      short loc_180012585
0x18001255f  call    cs:__imp_KeEnterCriticalRegion
0x180012566  nop     dword ptr [rax+rax+00h]
0x18001256b  mov     rcx, [rbp+58h]; Resource
0x18001256f  mov     dl, r15b; Wait
0x180012572  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180012579  nop     dword ptr [rax+rax+00h]
0x18001257e  cmp     al, r15b
0x180012581  cmovz   edi, r15d
0x180012585  mov     rcx, rbx
0x180012588  call    ?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18001258d  mov     esi, eax
0x18001258f  test    eax, eax
0x180012591  jns     short loc_180012606
0x180012593  mov     rcx, [rbx]
0x180012596  mov     r10d, 0FFFFh
0x18001259c  mov     edx, [rcx+30h]
0x18001259f  shr     edx, 1
0x1800125a1  cmp     edx, r10d
0x1800125a4  ja      short loc_1800125B1
0x1800125a6  test    dx, dx
0x1800125a9  jz      short loc_1800125B1
0x1800125ab  mov     r8, [rcx+38h]
0x1800125af  jmp     short loc_1800125B4
0x1800125b1  mov     r8, r14
0x1800125b4  mov     eax, [rcx+10h]
0x1800125b7  shr     eax, 1
0x1800125b9  cmp     eax, r10d
0x1800125bc  ja      short loc_1800125C9
0x1800125be  test    ax, ax
0x1800125c1  jz      short loc_1800125C9
0x1800125c3  mov     rdx, [rcx+18h]
0x1800125c7  jmp     short loc_1800125CC
0x1800125c9  mov     rdx, r14
0x1800125cc  mov     r9, [rcx]
0x1800125cf  mov     eax, [r9]
0x1800125d2  shr     eax, 1
0x1800125d4  cmp     eax, r10d
0x1800125d7  ja      short loc_1800125E4
0x1800125d9  test    ax, ax
0x1800125dc  jz      short loc_1800125E4
0x1800125de  mov     r9, [r9+8]
0x1800125e2  jmp     short loc_1800125E7
0x1800125e4  mov     r9, r14
0x1800125e7  mov     [rsp+98h+var_68], esi
0x1800125eb  mov     ecx, r15d
0x1800125ee  mov     [rsp+98h+var_70], r8
0x1800125f3  lea     r8, aConfigurationm_8; "ConfigurationManager::AddUser() - Faile"...
0x1800125fa  mov     [rsp+98h+var_78], rdx
0x1800125ff  xor     edx, edx
0x180012601  call    LogWrite
0x180012606  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r15b
0x18001260d  jz      short loc_180012620
0x18001260f  lea     r8, [rsp+98h+ActivityId]
0x180012614  lea     rdx, VEMGR_Add_User_Finish
0x18001261b  call    McTemplateK0_EtwWriteTransfer
0x180012620  test    dil, dil
0x180012623  jz      short loc_180012646
0x180012625  mov     rcx, [rbp+58h]; Resource
0x180012629  test    rcx, rcx
0x18001262c  jz      short loc_180012646
0x18001262e  call    cs:__imp_ExReleaseResourceLite
0x180012635  nop     dword ptr [rax+rax+00h]
0x18001263a  call    cs:__imp_KeLeaveCriticalRegion
0x180012641  nop     dword ptr [rax+rax+00h]
0x180012646  mov     eax, esi
0x180012648  jmp     short loc_18001264F
0x18001264a  mov     eax, 0C000000Dh
0x18001264f  mov     rcx, [rsp+98h+var_48]
0x180012654  xor     rcx, rsp; StackCookie
0x180012657  call    __security_check_cookie
0x18001265c  add     rsp, 68h
0x180012660  pop     r15
0x180012662  pop     r14
0x180012664  pop     rdi
0x180012665  pop     rsi
0x180012666  pop     rbp
0x180012667  pop     rbx
0x180012668  retn
```
