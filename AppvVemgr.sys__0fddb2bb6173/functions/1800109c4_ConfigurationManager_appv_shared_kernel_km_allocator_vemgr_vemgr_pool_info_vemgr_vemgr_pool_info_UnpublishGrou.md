# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::UnpublishGroupForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x1800109c4`
- end: `0x180010b4a`
- name: `??$UnpublishGroupForUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012c58`

## callees

- `0x1800109c4`
- `0x1800145a8`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x180010a20`
- `ntoskrnl!EtwActivityIdControl` at `0x180010a20`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010b02`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010b02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010b0e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010b0e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010a39`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010a39`

## string_xrefs

- `0x180010adf`: `ConfigurationManager::UnpublishGroupForUser() - Failed to store user flag. moniker %s. result 0x%08X.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::UnpublishGroupForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  bool v6; // si
  unsigned int v7; // ecx
  __int16 v8; // dx
  __int16 v9; // ax
  __int64 v10; // r8
  unsigned int v11; // ecx
  bool v12; // cc
  __int16 v13; // dx
  __int16 v14; // ax
  __int64 v15; // rcx
  int v16; // edi
  unsigned int v17; // ecx
  __int16 v18; // dx
  __int16 v19; // ax
  __int64 v20; // r9
  struct _ERESOURCE *v21; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-48h] BYREF

  if ( *(_DWORD *)a3 <= 2u || *(_DWORD *)a2 <= 2u )
    return 3221225485LL;
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  v6 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v6 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v7 = *(_DWORD *)a3 >> 1;
  if ( v7 > 0xFFFF )
    v8 = -1;
  else
    v8 = *(_DWORD *)a3 >> 1;
  v9 = 0;
  v10 = 0;
  if ( v7 <= 0xFFFF )
    v9 = v8;
  if ( v9 )
    v10 = *(_QWORD *)(a3 + 8);
  v11 = *(_DWORD *)a2 >> 1;
  v12 = v11 <= 0xFFFF;
  if ( v11 > 0xFFFF )
    v13 = -1;
  else
    v13 = *(_DWORD *)a2 >> 1;
  v14 = 0;
  v15 = 0;
  if ( v12 )
    v14 = v13;
  if ( v14 )
    v15 = *(_QWORD *)(a2 + 8);
  v16 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user_sid_from_group(
          v15,
          v10);
  if ( v16 < 0 )
  {
    v17 = *(_DWORD *)a2 >> 1;
    if ( v17 > 0xFFFF )
      v18 = -1;
    else
      v18 = *(_DWORD *)a2 >> 1;
    v19 = 0;
    v20 = 0;
    if ( v17 <= 0xFFFF )
      v19 = v18;
    if ( v19 )
      v20 = *(_QWORD *)(a2 + 8);
    LogWrite(
      1,
      0,
      L"ConfigurationManager::UnpublishGroupForUser() - Failed to store user flag. moniker %s. result 0x%08X.",
      v20,
      v16);
  }
  if ( v6 )
  {
    v21 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v21 )
    {
      ExReleaseResourceLite(v21);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800109c4  mov     [rsp+arg_0], rbx
0x1800109c9  mov     [rsp+arg_18], rbp
0x1800109ce  push    rsi
0x1800109cf  push    rdi
0x1800109d0  push    r12
0x1800109d2  push    r14
0x1800109d4  push    r15
0x1800109d6  sub     rsp, 50h
0x1800109da  mov     rax, cs:__security_cookie
0x1800109e1  xor     rax, rsp
0x1800109e4  mov     [rsp+78h+var_38], rax
0x1800109e9  cmp     dword ptr [r8], 2
0x1800109ed  mov     rdi, r8
0x1800109f0  mov     rbx, rdx
0x1800109f3  mov     rbp, rcx
0x1800109f6  jbe     loc_180010B1E
0x1800109fc  cmp     dword ptr [rdx], 2
0x1800109ff  jbe     loc_180010B1E
0x180010a05  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010a0c  mov     r12d, 1
0x180010a12  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x180010a17  mov     ecx, r12d; ControlCode
0x180010a1a  movdqu  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x180010a20  call    cs:__imp_EtwActivityIdControl
0x180010a27  nop     dword ptr [rax+rax+00h]
0x180010a2c  xor     r14d, r14d
0x180010a2f  movzx   esi, r14b
0x180010a33  cmp     [rbp+58h], r14
0x180010a37  jz      short loc_180010A5F
0x180010a39  call    cs:__imp_KeEnterCriticalRegion
0x180010a40  nop     dword ptr [rax+rax+00h]
0x180010a45  mov     rcx, [rbp+58h]; Resource
0x180010a49  mov     dl, r12b; Wait
0x180010a4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010a53  nop     dword ptr [rax+rax+00h]
0x180010a58  cmp     al, r12b
0x180010a5b  cmovz   esi, r12d
0x180010a5f  mov     ecx, [rdi]
0x180010a61  mov     r15d, 0FFFFh
0x180010a67  shr     ecx, 1
0x180010a69  cmp     ecx, r15d
0x180010a6c  ja      short loc_180010A73
0x180010a6e  movzx   edx, cx
0x180010a71  jmp     short loc_180010A76
0x180010a73  mov     edx, r15d
0x180010a76  mov     eax, r14d
0x180010a79  mov     r8, r14
0x180010a7c  cmovbe  ax, dx
0x180010a80  test    ax, ax
0x180010a83  jz      short loc_180010A89
0x180010a85  mov     r8, [rdi+8]
0x180010a89  mov     ecx, [rbx]
0x180010a8b  shr     ecx, 1
0x180010a8d  cmp     ecx, r15d
0x180010a90  ja      short loc_180010A97
0x180010a92  movzx   edx, cx
0x180010a95  jmp     short loc_180010A9A
0x180010a97  mov     edx, r15d
0x180010a9a  mov     eax, r14d
0x180010a9d  mov     rcx, r14
0x180010aa0  cmovbe  ax, dx
0x180010aa4  test    ax, ax
0x180010aa7  jz      short loc_180010AAD
0x180010aa9  mov     rcx, [rbx+8]
0x180010aad  mov     rdx, r8
0x180010ab0  call    ?remove_user_sid_from_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user_sid_from_group(wchar_t const *,wchar_t const *)
0x180010ab5  mov     edi, eax
0x180010ab7  test    eax, eax
0x180010ab9  jns     short loc_180010AF4
0x180010abb  mov     ecx, [rbx]
0x180010abd  shr     ecx, 1
0x180010abf  cmp     ecx, r15d
0x180010ac2  ja      short loc_180010AC9
0x180010ac4  movzx   edx, cx
0x180010ac7  jmp     short loc_180010ACC
0x180010ac9  mov     edx, r15d
0x180010acc  mov     eax, r14d
0x180010acf  mov     r9, r14
0x180010ad2  cmovbe  ax, dx
0x180010ad6  test    ax, ax
0x180010ad9  jz      short loc_180010ADF
0x180010adb  mov     r9, [rbx+8]
0x180010adf  lea     r8, aConfigurationm_6; "ConfigurationManager::UnpublishGroupFor"...
0x180010ae6  mov     [rsp+78h+var_58], edi
0x180010aea  xor     edx, edx
0x180010aec  mov     ecx, r12d
0x180010aef  call    LogWrite
0x180010af4  test    sil, sil
0x180010af7  jz      short loc_180010B1A
0x180010af9  mov     rcx, [rbp+58h]; Resource
0x180010afd  test    rcx, rcx
0x180010b00  jz      short loc_180010B1A
0x180010b02  call    cs:__imp_ExReleaseResourceLite
0x180010b09  nop     dword ptr [rax+rax+00h]
0x180010b0e  call    cs:__imp_KeLeaveCriticalRegion
0x180010b15  nop     dword ptr [rax+rax+00h]
0x180010b1a  mov     eax, edi
0x180010b1c  jmp     short loc_180010B23
0x180010b1e  mov     eax, 0C000000Dh
0x180010b23  mov     rcx, [rsp+78h+var_38]
0x180010b28  xor     rcx, rsp; StackCookie
0x180010b2b  call    __security_check_cookie
0x180010b30  lea     r11, [rsp+78h+var_28]
0x180010b35  mov     rbx, [r11+30h]
0x180010b39  mov     rbp, [r11+48h]
0x180010b3d  mov     rsp, r11
0x180010b40  pop     r15
0x180010b42  pop     r14
0x180010b44  pop     r12
0x180010b46  pop     rdi
0x180010b47  pop     rsi
0x180010b48  retn
```
