# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::PublishGroupForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x180010058`
- end: `0x1800101de`
- name: `??$PublishGroupForUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013384`

## callees

- `0x180010058`
- `0x180013718`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1800100b4`
- `ntoskrnl!EtwActivityIdControl` at `0x1800100b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010196`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010196`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800101a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800101a2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800100e0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800100e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800100cd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800100cd`

## string_xrefs

- `0x180010173`: `ConfigurationManager::PublishGroupForUser() - Failed to store user flag. moniker %s. result 0x%08X.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::PublishGroupForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
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
  v16 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(
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
      L"ConfigurationManager::PublishGroupForUser() - Failed to store user flag. moniker %s. result 0x%08X.",
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
0x180010058  mov     [rsp+arg_0], rbx
0x18001005d  mov     [rsp+arg_18], rbp
0x180010062  push    rsi
0x180010063  push    rdi
0x180010064  push    r12
0x180010066  push    r14
0x180010068  push    r15
0x18001006a  sub     rsp, 50h
0x18001006e  mov     rax, cs:__security_cookie
0x180010075  xor     rax, rsp
0x180010078  mov     [rsp+78h+var_38], rax
0x18001007d  cmp     dword ptr [r8], 2
0x180010081  mov     rdi, r8
0x180010084  mov     rbx, rdx
0x180010087  mov     rbp, rcx
0x18001008a  jbe     loc_1800101B2
0x180010090  cmp     dword ptr [rdx], 2
0x180010093  jbe     loc_1800101B2
0x180010099  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800100a0  mov     r12d, 1
0x1800100a6  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x1800100ab  mov     ecx, r12d; ControlCode
0x1800100ae  movdqu  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x1800100b4  call    cs:__imp_EtwActivityIdControl
0x1800100bb  nop     dword ptr [rax+rax+00h]
0x1800100c0  xor     r14d, r14d
0x1800100c3  movzx   esi, r14b
0x1800100c7  cmp     [rbp+58h], r14
0x1800100cb  jz      short loc_1800100F3
0x1800100cd  call    cs:__imp_KeEnterCriticalRegion
0x1800100d4  nop     dword ptr [rax+rax+00h]
0x1800100d9  mov     rcx, [rbp+58h]; Resource
0x1800100dd  mov     dl, r12b; Wait
0x1800100e0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800100e7  nop     dword ptr [rax+rax+00h]
0x1800100ec  cmp     al, r12b
0x1800100ef  cmovz   esi, r12d
0x1800100f3  mov     ecx, [rdi]
0x1800100f5  mov     r15d, 0FFFFh
0x1800100fb  shr     ecx, 1
0x1800100fd  cmp     ecx, r15d
0x180010100  ja      short loc_180010107
0x180010102  movzx   edx, cx
0x180010105  jmp     short loc_18001010A
0x180010107  mov     edx, r15d
0x18001010a  mov     eax, r14d
0x18001010d  mov     r8, r14
0x180010110  cmovbe  ax, dx
0x180010114  test    ax, ax
0x180010117  jz      short loc_18001011D
0x180010119  mov     r8, [rdi+8]
0x18001011d  mov     ecx, [rbx]
0x18001011f  shr     ecx, 1
0x180010121  cmp     ecx, r15d
0x180010124  ja      short loc_18001012B
0x180010126  movzx   edx, cx
0x180010129  jmp     short loc_18001012E
0x18001012b  mov     edx, r15d
0x18001012e  mov     eax, r14d
0x180010131  mov     rcx, r14
0x180010134  cmovbe  ax, dx
0x180010138  test    ax, ax
0x18001013b  jz      short loc_180010141
0x18001013d  mov     rcx, [rbx+8]
0x180010141  mov     rdx, r8
0x180010144  call    ?add_user_sid_to_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(wchar_t const *,wchar_t const *)
0x180010149  mov     edi, eax
0x18001014b  test    eax, eax
0x18001014d  jns     short loc_180010188
0x18001014f  mov     ecx, [rbx]
0x180010151  shr     ecx, 1
0x180010153  cmp     ecx, r15d
0x180010156  ja      short loc_18001015D
0x180010158  movzx   edx, cx
0x18001015b  jmp     short loc_180010160
0x18001015d  mov     edx, r15d
0x180010160  mov     eax, r14d
0x180010163  mov     r9, r14
0x180010166  cmovbe  ax, dx
0x18001016a  test    ax, ax
0x18001016d  jz      short loc_180010173
0x18001016f  mov     r9, [rbx+8]
0x180010173  lea     r8, aConfigurationm_3; "ConfigurationManager::PublishGroupForUs"...
0x18001017a  mov     [rsp+78h+var_58], edi
0x18001017e  xor     edx, edx
0x180010180  mov     ecx, r12d
0x180010183  call    LogWrite
0x180010188  test    sil, sil
0x18001018b  jz      short loc_1800101AE
0x18001018d  mov     rcx, [rbp+58h]; Resource
0x180010191  test    rcx, rcx
0x180010194  jz      short loc_1800101AE
0x180010196  call    cs:__imp_ExReleaseResourceLite
0x18001019d  nop     dword ptr [rax+rax+00h]
0x1800101a2  call    cs:__imp_KeLeaveCriticalRegion
0x1800101a9  nop     dword ptr [rax+rax+00h]
0x1800101ae  mov     eax, edi
0x1800101b0  jmp     short loc_1800101B7
0x1800101b2  mov     eax, 0C000000Dh
0x1800101b7  mov     rcx, [rsp+78h+var_38]
0x1800101bc  xor     rcx, rsp; StackCookie
0x1800101bf  call    __security_check_cookie
0x1800101c4  lea     r11, [rsp+78h+var_28]
0x1800101c9  mov     rbx, [r11+30h]
0x1800101cd  mov     rbp, [r11+48h]
0x1800101d1  mov     rsp, r11
0x1800101d4  pop     r15
0x1800101d6  pop     r14
0x1800101d8  pop     r12
0x1800101da  pop     rdi
0x1800101db  pop     rsi
0x1800101dc  retn
```
