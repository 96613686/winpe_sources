# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::PublishGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x18000fe44`
- end: `0x180010051`
- name: `??$PublishGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0@Z`
- size: `525`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013260`

## callees

- `0x18000e354`
- `0x18000f994`
- `0x18000fd14`
- `0x18000fe44`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x18000fea3`
- `ntoskrnl!EtwActivityIdControl` at `0x18000fea3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001000f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001000f`
- `ntoskrnl!ZwClose` at `0x18000ff63`
- `ntoskrnl!ZwClose` at `0x18000ff8e`
- `ntoskrnl!ZwClose` at `0x18000ff63`
- `ntoskrnl!ZwClose` at `0x18000ff8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001001b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001001b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000fee9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000fee9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000fed6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000fed6`

## string_xrefs

- `0x18000ffd2`: `ConfigurationManager::PublishGlobally() - Failed to store global flag. moniker %s. result %d.`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::PublishGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v4; // eax
  __int64 v7; // rcx
  bool v8; // r14
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // ebp
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // r9
  unsigned int v18; // eax
  struct _ERESOURCE *v19; // rcx
  int v20; // [rsp+20h] [rbp-58h]
  HANDLE Handle; // [rsp+30h] [rbp-48h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-40h] BYREF

  v4 = *(_DWORD *)a3;
  if ( *(_DWORD *)a2 <= 2u )
  {
    if ( v4 > 2 )
      goto LABEL_3;
    return 3221225485LL;
  }
  if ( v4 > 2 )
    return 3221225485LL;
LABEL_3:
  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v7, VEMGR_Global_Publish_Start, &ActivityId);
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
  v12 = *(_DWORD *)a2 >> 1;
  if ( v12 <= 0xFFFF && (_WORD)v12 )
    v13 = *(_QWORD *)(a2 + 8);
  else
    v13 = 0;
  Handle = 0;
  v14 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
          &Handle,
          v13,
          v10,
          0);
  if ( v14 >= 0 )
  {
    v14 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(Handle);
    if ( Handle )
      ZwClose(Handle);
    if ( v14 >= 0 )
      goto LABEL_32;
  }
  else if ( Handle )
  {
    ZwClose(Handle);
  }
  if ( *(_DWORD *)a2 > 2u )
  {
    v18 = *(_DWORD *)a2 >> 1;
    if ( v18 <= 0xFFFF && (_WORD)v18 )
    {
      v17 = *(_QWORD *)(a2 + 8);
      goto LABEL_31;
    }
LABEL_30:
    v17 = 0;
    goto LABEL_31;
  }
  v16 = *(_DWORD *)a3 >> 1;
  if ( v16 > 0xFFFF || !(_WORD)v16 )
    goto LABEL_30;
  v17 = *(_QWORD *)(a3 + 8);
LABEL_31:
  v20 = v14;
  LogWrite(
    1,
    0,
    L"ConfigurationManager::PublishGlobally() - Failed to store global flag. moniker %s. result %d.",
    v17,
    v20);
LABEL_32:
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v15, VEMGR_Global_Publish_Finish, &ActivityId);
  if ( v8 )
  {
    v19 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v19 )
    {
      ExReleaseResourceLite(v19);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000fe44  mov     [rsp+arg_0], rbp
0x18000fe49  mov     [rsp+arg_18], rsi
0x18000fe4e  push    rdi
0x18000fe4f  push    r12
0x18000fe51  push    r13
0x18000fe53  push    r14
0x18000fe55  push    r15
0x18000fe57  sub     rsp, 50h
0x18000fe5b  mov     rax, cs:__security_cookie
0x18000fe62  xor     rax, rsp
0x18000fe65  mov     [rsp+78h+var_30], rax
0x18000fe6a  cmp     dword ptr [rdx], 2
0x18000fe6d  mov     rdi, r8
0x18000fe70  mov     eax, [r8]
0x18000fe73  mov     rsi, rdx
0x18000fe76  mov     r15, rcx
0x18000fe79  ja      loc_18000FF12
0x18000fe7f  cmp     eax, 2
0x18000fe82  jbe     loc_18000FF1B
0x18000fe88  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000fe8f  mov     r13d, 1
0x18000fe95  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x18000fe9a  mov     ecx, r13d; ControlCode
0x18000fe9d  movdqu  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x18000fea3  call    cs:__imp_EtwActivityIdControl
0x18000feaa  nop     dword ptr [rax+rax+00h]
0x18000feaf  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r13b
0x18000feb6  jz      short loc_18000FEC9
0x18000feb8  lea     r8, [rsp+78h+ActivityId]
0x18000febd  lea     rdx, VEMGR_Global_Publish_Start
0x18000fec4  call    McTemplateK0_EtwWriteTransfer
0x18000fec9  xor     r12d, r12d
0x18000fecc  movzx   r14d, r12b
0x18000fed0  cmp     [r15+58h], r12
0x18000fed4  jz      short loc_18000FEFC
0x18000fed6  call    cs:__imp_KeEnterCriticalRegion
0x18000fedd  nop     dword ptr [rax+rax+00h]
0x18000fee2  mov     rcx, [r15+58h]; Resource
0x18000fee6  mov     dl, r13b; Wait
0x18000fee9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000fef0  nop     dword ptr [rax+rax+00h]
0x18000fef5  cmp     al, r13b
0x18000fef8  cmovz   r14d, r13d
0x18000fefc  mov     eax, [rdi]
0x18000fefe  shr     eax, 1
0x18000ff00  cmp     eax, 0FFFFh
0x18000ff05  ja      short loc_18000FF25
0x18000ff07  test    ax, ax
0x18000ff0a  jz      short loc_18000FF25
0x18000ff0c  mov     r8, [rdi+8]
0x18000ff10  jmp     short loc_18000FF28
0x18000ff12  cmp     eax, 2
0x18000ff15  jbe     loc_18000FE88
0x18000ff1b  mov     eax, 0C000000Dh
0x18000ff20  jmp     loc_180010029
0x18000ff25  mov     r8, r12
0x18000ff28  mov     eax, [rsi]
0x18000ff2a  shr     eax, 1
0x18000ff2c  cmp     eax, 0FFFFh
0x18000ff31  ja      short loc_18000FF3E
0x18000ff33  test    ax, ax
0x18000ff36  jz      short loc_18000FF3E
0x18000ff38  mov     rdx, [rsi+8]
0x18000ff3c  jmp     short loc_18000FF41
0x18000ff3e  mov     rdx, r12
0x18000ff41  xor     r9d, r9d
0x18000ff44  mov     [rsp+78h+Handle], r12
0x18000ff49  lea     rcx, [rsp+78h+Handle]
0x18000ff4e  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x18000ff53  mov     rcx, [rsp+78h+Handle]; KeyHandle
0x18000ff58  mov     ebp, eax
0x18000ff5a  test    eax, eax
0x18000ff5c  jns     short loc_18000FF71
0x18000ff5e  test    rcx, rcx
0x18000ff61  jz      short loc_18000FF9E
0x18000ff63  call    cs:__imp_ZwClose
0x18000ff6a  nop     dword ptr [rax+rax+00h]
0x18000ff6f  jmp     short loc_18000FF9E
0x18000ff71  mov     r8d, r13d
0x18000ff74  lea     rdx, aGlobal; "Global"
0x18000ff7b  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x18000ff80  mov     ebp, eax
0x18000ff82  cmp     [rsp+78h+Handle], r12
0x18000ff87  jz      short loc_18000FF9A
0x18000ff89  mov     rcx, [rsp+78h+Handle]; Handle
0x18000ff8e  call    cs:__imp_ZwClose
0x18000ff95  nop     dword ptr [rax+rax+00h]
0x18000ff9a  test    ebp, ebp
0x18000ff9c  jns     short loc_18000FFE7
0x18000ff9e  mov     eax, [rsi]
0x18000ffa0  cmp     eax, 2
0x18000ffa3  ja      short loc_18000FFBB
0x18000ffa5  mov     eax, [rdi]
0x18000ffa7  shr     eax, 1
0x18000ffa9  cmp     eax, 0FFFFh
0x18000ffae  ja      short loc_18000FFCF
0x18000ffb0  test    ax, ax
0x18000ffb3  jz      short loc_18000FFCF
0x18000ffb5  mov     r9, [rdi+8]
0x18000ffb9  jmp     short loc_18000FFD2
0x18000ffbb  shr     eax, 1
0x18000ffbd  cmp     eax, 0FFFFh
0x18000ffc2  ja      short loc_18000FFCF
0x18000ffc4  test    ax, ax
0x18000ffc7  jz      short loc_18000FFCF
0x18000ffc9  mov     r9, [rsi+8]
0x18000ffcd  jmp     short loc_18000FFD2
0x18000ffcf  mov     r9, r12
0x18000ffd2  lea     r8, aConfigurationm_1; "ConfigurationManager::PublishGlobally()"...
0x18000ffd9  mov     [rsp+78h+var_58], ebp
0x18000ffdd  xor     edx, edx
0x18000ffdf  mov     ecx, r13d
0x18000ffe2  call    LogWrite
0x18000ffe7  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r13b
0x18000ffee  jz      short loc_180010001
0x18000fff0  lea     r8, [rsp+78h+ActivityId]
0x18000fff5  lea     rdx, VEMGR_Global_Publish_Finish
0x18000fffc  call    McTemplateK0_EtwWriteTransfer
0x180010001  test    r14b, r14b
0x180010004  jz      short loc_180010027
0x180010006  mov     rcx, [r15+58h]; Resource
0x18001000a  test    rcx, rcx
0x18001000d  jz      short loc_180010027
0x18001000f  call    cs:__imp_ExReleaseResourceLite
0x180010016  nop     dword ptr [rax+rax+00h]
0x18001001b  call    cs:__imp_KeLeaveCriticalRegion
0x180010022  nop     dword ptr [rax+rax+00h]
0x180010027  mov     eax, ebp
0x180010029  mov     rcx, [rsp+78h+var_30]
0x18001002e  xor     rcx, rsp; StackCookie
0x180010031  call    __security_check_cookie
0x180010036  lea     r11, [rsp+78h+var_28]
0x18001003b  mov     rbp, [r11+30h]
0x18001003f  mov     rsi, [r11+48h]
0x180010043  mov     rsp, r11
0x180010046  pop     r15
0x180010048  pop     r14
0x18001004a  pop     r13
0x18001004c  pop     r12
0x18001004e  pop     rdi
0x18001004f  retn
```
