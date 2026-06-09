# StoreAppsAreDisabled(void)

- ea: `0x18000ee24`
- end: `0x18000ef60`
- name: `?StoreAppsAreDisabled@@YA_NXZ`
- size: `316`
- prototype: `bool(void)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9e0`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x18000ee24`
- `0x180011470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ef19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ef19`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee49`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee49`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000ee83`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000ee83`

## pseudocode

```c
char StoreAppsAreDisabled(void)
{
  char v0; // bl
  unsigned int v2; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  LPVOID Context; // [rsp+68h] [rbp+20h] BYREF

  Context = 0;
  if ( InitOnceExecuteOnce(&initPolicyCheckOnce, (PINIT_ONCE_FN)InitStoreAppsAreDisabled, 0, &Context) )
  {
    v0 = 1;
    if ( canDisableApps == 1 )
    {
      v2 = 0;
      if ( (int)PolicyManager_GetPolicyInt(L"ApplicationManagement", L"DisableStoreOriginatedApps", &v2) >= 0 && v2 <= 1 )
      {
        if ( !v2 )
          return 0;
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
          0xE0u,
          "StoreAppsAreDisabled",
          L"MDM policy has blocked the running and updating of all Windows Store apps on this device.");
        if ( !v2 )
          return 0;
        return v0;
      }
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Policies\\Microsoft\\WindowsStore",
              L"DisableStoreApps",
              0x18u,
              0,
              &pvData,
              &pcbData)
        && pvData )
      {
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
          0xF2u,
          "StoreAppsAreDisabled",
          L"Group policy has blocked the running and updating of all Windows Store apps on this device.");
        return v0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ee24  push    rbx
0x18000ee26  sub     rsp, 40h
0x18000ee2a  lea     r9, [rsp+48h+Context]; Context
0x18000ee2f  mov     [rsp+48h+Context], 0
0x18000ee38  xor     r8d, r8d; Parameter
0x18000ee3b  lea     rdx, ?InitStoreAppsAreDisabled@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000ee42  lea     rcx, ?initPolicyCheckOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000ee49  call    cs:__imp_InitOnceExecuteOnce
0x18000ee4f  test    eax, eax
0x18000ee51  jz      loc_18000EF58
0x18000ee57  mov     ebx, 1
0x18000ee5c  cmp     cs:?canDisableApps@@3KA, ebx; ulong canDisableApps
0x18000ee62  jnz     loc_18000EF58
0x18000ee68  lea     r8, [rsp+48h+arg_0]
0x18000ee6d  mov     [rsp+48h+arg_0], 0
0x18000ee75  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x18000ee7c  lea     rcx, aApplicationman; "ApplicationManagement"
0x18000ee83  call    cs:__imp_PolicyManager_GetPolicyInt
0x18000ee89  test    eax, eax
0x18000ee8b  js      short loc_18000EED1
0x18000ee8d  mov     eax, [rsp+48h+arg_0]
0x18000ee91  cmp     eax, ebx
0x18000ee93  ja      short loc_18000EED1
0x18000ee95  test    eax, eax
0x18000ee97  jz      short loc_18000EEC8
0x18000ee99  lea     rax, aMdmPolicyHasBl; "MDM policy has blocked the running and "...
0x18000eea0  mov     r8d, 0E0h; unsigned int
0x18000eea6  lea     r9, aStoreappsaredi; "StoreAppsAreDisabled"
0x18000eead  mov     [rsp+48h+pdwType], rax; unsigned __int16 *
0x18000eeb2  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000eeb9  lea     ecx, [rbx+1]; unsigned int
0x18000eebc  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000eec1  cmp     [rsp+48h+arg_0], 0
0x18000eec6  jnz     short loc_18000EECA
0x18000eec8  xor     bl, bl
0x18000eeca  mov     al, bl
0x18000eecc  jmp     loc_18000EF5A
0x18000eed1  lea     rax, [rsp+48h+arg_10]
0x18000eed6  mov     [rsp+48h+arg_8], 0
0x18000eede  mov     [rsp+48h+pcbData], rax; pcbData
0x18000eee3  lea     r8, aDisablestoreap; "DisableStoreApps"
0x18000eeea  lea     rax, [rsp+48h+arg_8]
0x18000eeef  mov     [rsp+48h+arg_10], 4
0x18000eef7  mov     [rsp+48h+pvData], rax; pvData
0x18000eefc  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\WindowsS"...
0x18000ef03  mov     r9d, 18h; dwFlags
0x18000ef09  mov     [rsp+48h+pdwType], 0; pdwType
0x18000ef12  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000ef19  call    cs:__imp_RegGetValueW
0x18000ef1f  test    eax, eax
0x18000ef21  jnz     short loc_18000EF58
0x18000ef23  cmp     [rsp+48h+arg_8], eax
0x18000ef27  jz      short loc_18000EF58
0x18000ef29  lea     rax, aGroupPolicyHas; "Group policy has blocked the running an"...
0x18000ef30  mov     r8d, 0F2h; unsigned int
0x18000ef36  lea     r9, aStoreappsaredi; "StoreAppsAreDisabled"
0x18000ef3d  mov     [rsp+48h+pdwType], rax; unsigned __int16 *
0x18000ef42  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000ef49  mov     ecx, 2; unsigned int
0x18000ef4e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000ef53  jmp     loc_18000EECA
0x18000ef58  xor     al, al
0x18000ef5a  add     rsp, 40h
0x18000ef5e  pop     rbx
0x18000ef5f  retn
```
