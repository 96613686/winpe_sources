# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::UnpublishGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x1800107e4`
- end: `0x1800109bb`
- name: `??$UnpublishGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180012b34`

## callees

- `0x18000fd14`
- `0x1800107e4`
- `0x180013d4c`
- `0x180013f40`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x180010842`
- `ntoskrnl!EtwActivityIdControl` at `0x180010842`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001097a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001097a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010986`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010986`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010888`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010888`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010875`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010875`

## string_xrefs

- `0x180010908`: `ConfigurationManager::UnpublishGlobally() - Failed to remove global user mappings. moniker %s. result %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::UnpublishGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v7; // rcx
  bool v8; // si
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ecx
  __int64 v15; // r9
  unsigned int v16; // ecx
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  struct _ERESOURCE *v23; // rcx
  int v24; // [rsp+20h] [rbp-58h]
  GUID ActivityId; // [rsp+30h] [rbp-48h] BYREF

  if ( *(_DWORD *)a2 <= 2u && *(_DWORD *)a3 <= 2u )
    return 3221225485LL;
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v7, VEMGR_Global_Unpublish_Start, &ActivityId);
  v8 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v8 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v9 = *(_DWORD *)a3 >> 1;
  if ( v9 <= 0xFFFF && (_WORD)v9 )
    v10 = *(_QWORD *)(a3 + 8);
  else
    v10 = 0;
  v11 = *(_DWORD *)a2 >> 1;
  if ( v11 <= 0xFFFF && (_WORD)v11 )
    v12 = *(_QWORD *)(a2 + 8);
  else
    v12 = 0;
  v13 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(
          v12,
          v10);
  if ( v13 < 0 )
  {
    if ( *(_DWORD *)a2 > 2u )
    {
      v16 = *(_DWORD *)a2 >> 1;
      if ( v16 <= 0xFFFF && (_WORD)v16 )
      {
        v15 = *(_QWORD *)(a2 + 8);
        goto LABEL_25;
      }
    }
    else
    {
      v14 = *(_DWORD *)a3 >> 1;
      if ( v14 <= 0xFFFF && (_WORD)v14 )
      {
        v15 = *(_QWORD *)(a3 + 8);
LABEL_25:
        v24 = v13;
        LogWrite(
          1,
          0,
          L"ConfigurationManager::UnpublishGlobally() - Failed to remove global user mappings. moniker %s. result %d.",
          v15,
          v24);
        goto LABEL_26;
      }
    }
    v15 = 0;
    goto LABEL_25;
  }
LABEL_26:
  v17 = *(_DWORD *)a3 >> 1;
  if ( v17 <= 0xFFFF && (_WORD)v17 )
    v18 = *(_QWORD *)(a3 + 8);
  else
    v18 = 0;
  v19 = *(_DWORD *)a2 >> 1;
  if ( v19 <= 0xFFFF && (_WORD)v19 )
    v20 = *(_QWORD *)(a2 + 8);
  else
    v20 = 0;
  v22 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_flag(
          v20,
          v18);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v21, VEMGR_Global_Unpublish_Finish, &ActivityId);
  if ( v8 )
  {
    v23 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v23 )
    {
      ExReleaseResourceLite(v23);
      KeLeaveCriticalRegion();
    }
  }
  return v22;
}

```

## disassembly

```asm
0x1800107e4  mov     [rsp+arg_0], rbx
0x1800107e9  mov     [rsp+arg_18], rbp
0x1800107ee  push    rsi
0x1800107ef  push    rdi
0x1800107f0  push    r12
0x1800107f2  push    r14
0x1800107f4  push    r15
0x1800107f6  sub     rsp, 50h
0x1800107fa  mov     rax, cs:__security_cookie
0x180010801  xor     rax, rsp
0x180010804  mov     [rsp+78h+var_38], rax
0x180010809  cmp     dword ptr [rdx], 2
0x18001080c  mov     rbx, r8
0x18001080f  mov     rdi, rdx
0x180010812  mov     rbp, rcx
0x180010815  ja      short loc_180010827
0x180010817  cmp     dword ptr [r8], 2
0x18001081b  ja      short loc_180010827
0x18001081d  mov     eax, 0C000000Dh
0x180010822  jmp     loc_180010994
0x180010827  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001082e  mov     r12d, 1
0x180010834  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x180010839  mov     ecx, r12d; ControlCode
0x18001083c  movdqu  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x180010842  call    cs:__imp_EtwActivityIdControl
0x180010849  nop     dword ptr [rax+rax+00h]
0x18001084e  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x180010855  jz      short loc_180010868
0x180010857  lea     r8, [rsp+78h+ActivityId]
0x18001085c  lea     rdx, VEMGR_Global_Unpublish_Start
0x180010863  call    McTemplateK0_EtwWriteTransfer
0x180010868  xor     r14d, r14d
0x18001086b  movzx   esi, r14b
0x18001086f  cmp     [rbp+58h], r14
0x180010873  jz      short loc_18001089B
0x180010875  call    cs:__imp_KeEnterCriticalRegion
0x18001087c  nop     dword ptr [rax+rax+00h]
0x180010881  mov     rcx, [rbp+58h]; Resource
0x180010885  mov     dl, r12b; Wait
0x180010888  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001088f  nop     dword ptr [rax+rax+00h]
0x180010894  cmp     al, r12b
0x180010897  cmovz   esi, r12d
0x18001089b  mov     eax, [rbx]
0x18001089d  mov     r15d, 0FFFFh
0x1800108a3  shr     eax, 1
0x1800108a5  cmp     eax, r15d
0x1800108a8  ja      short loc_1800108B5
0x1800108aa  test    ax, ax
0x1800108ad  jz      short loc_1800108B5
0x1800108af  mov     rdx, [rbx+8]
0x1800108b3  jmp     short loc_1800108B8
0x1800108b5  mov     rdx, r14
0x1800108b8  mov     eax, [rdi]
0x1800108ba  shr     eax, 1
0x1800108bc  cmp     eax, r15d
0x1800108bf  ja      short loc_1800108CC
0x1800108c1  test    ax, ax
0x1800108c4  jz      short loc_1800108CC
0x1800108c6  mov     rcx, [rdi+8]
0x1800108ca  jmp     short loc_1800108CF
0x1800108cc  mov     rcx, r14
0x1800108cf  call    ?remove_global_users@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(wchar_t const *,wchar_t const *)
0x1800108d4  test    eax, eax
0x1800108d6  jns     short loc_18001091D
0x1800108d8  mov     ecx, [rdi]
0x1800108da  cmp     ecx, 2
0x1800108dd  ja      short loc_1800108F3
0x1800108df  mov     ecx, [rbx]
0x1800108e1  shr     ecx, 1
0x1800108e3  cmp     ecx, r15d
0x1800108e6  ja      short loc_180010905
0x1800108e8  test    cx, cx
0x1800108eb  jz      short loc_180010905
0x1800108ed  mov     r9, [rbx+8]
0x1800108f1  jmp     short loc_180010908
0x1800108f3  shr     ecx, 1
0x1800108f5  cmp     ecx, r15d
0x1800108f8  ja      short loc_180010905
0x1800108fa  test    cx, cx
0x1800108fd  jz      short loc_180010905
0x1800108ff  mov     r9, [rdi+8]
0x180010903  jmp     short loc_180010908
0x180010905  mov     r9, r14
0x180010908  lea     r8, aConfigurationm_9; "ConfigurationManager::UnpublishGlobally"...
0x18001090f  mov     [rsp+78h+var_58], eax
0x180010913  xor     edx, edx
0x180010915  mov     ecx, r12d
0x180010918  call    LogWrite
0x18001091d  mov     eax, [rbx]
0x18001091f  shr     eax, 1
0x180010921  cmp     eax, r15d
0x180010924  ja      short loc_180010931
0x180010926  test    ax, ax
0x180010929  jz      short loc_180010931
0x18001092b  mov     rdx, [rbx+8]
0x18001092f  jmp     short loc_180010934
0x180010931  mov     rdx, r14
0x180010934  mov     eax, [rdi]
0x180010936  shr     eax, 1
0x180010938  cmp     eax, r15d
0x18001093b  ja      short loc_180010948
0x18001093d  test    ax, ax
0x180010940  jz      short loc_180010948
0x180010942  mov     rcx, [rdi+8]
0x180010946  jmp     short loc_18001094B
0x180010948  mov     rcx, r14
0x18001094b  call    ?remove_global_flag@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_flag(wchar_t const *,wchar_t const *)
0x180010950  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x180010957  mov     ebx, eax
0x180010959  jz      short loc_18001096C
0x18001095b  lea     r8, [rsp+78h+ActivityId]
0x180010960  lea     rdx, VEMGR_Global_Unpublish_Finish
0x180010967  call    McTemplateK0_EtwWriteTransfer
0x18001096c  test    sil, sil
0x18001096f  jz      short loc_180010992
0x180010971  mov     rcx, [rbp+58h]; Resource
0x180010975  test    rcx, rcx
0x180010978  jz      short loc_180010992
0x18001097a  call    cs:__imp_ExReleaseResourceLite
0x180010981  nop     dword ptr [rax+rax+00h]
0x180010986  call    cs:__imp_KeLeaveCriticalRegion
0x18001098d  nop     dword ptr [rax+rax+00h]
0x180010992  mov     eax, ebx
0x180010994  mov     rcx, [rsp+78h+var_38]
0x180010999  xor     rcx, rsp; StackCookie
0x18001099c  call    __security_check_cookie
0x1800109a1  lea     r11, [rsp+78h+var_28]
0x1800109a6  mov     rbx, [r11+30h]
0x1800109aa  mov     rbp, [r11+48h]
0x1800109ae  mov     rsp, r11
0x1800109b1  pop     r15
0x1800109b3  pop     r14
0x1800109b5  pop     r12
0x1800109b7  pop     rdi
0x1800109b8  pop     rsi
0x1800109b9  retn
```
