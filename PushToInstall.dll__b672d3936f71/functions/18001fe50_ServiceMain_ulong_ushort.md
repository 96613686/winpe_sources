# ServiceMain(ulong,ushort * *)

- ea: `0x18001fe50`
- end: `0x180020078`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `552`
- prototype: `void __fastcall(unsigned int, const WCHAR **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003540`
- `0x18001fe50`
- `0x1800212ac`
- `0x18002c4b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ff65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002002a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ff65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002002a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fe84`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fe84`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001fec5`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001fec5`

## string_xrefs

- `0x18001feff`: `onecoreuap\enduser\winstore\pushtoinstall\svc\svcmain.cpp`
- `0x18001ffce`: `onecoreuap\enduser\winstore\pushtoinstall\svc\svcmain.cpp`
- `0x18002005a`: `onecoreuap\enduser\winstore\pushtoinstall\svc\svcmain.cpp`
- `0x18001ffbb`: `Failed to read MDM policy on this device: PolicyManager_GetPolicyIntPresent API not present.`
- `0x18001ff31`: `DisablePushToInstall`
- `0x18001ff48`: `SOFTWARE\Policies\Microsoft\PushToInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ServiceMain(unsigned int a1, const WCHAR **a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 **v5; // r9
  int v6; // [rsp+40h] [rbp-20h] BYREF
  DWORD v7; // [rsp+44h] [rbp-1Ch] BYREF
  LPVOID Context[3]; // [rsp+48h] [rbp-18h] BYREF
  int pvData; // [rsp+80h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+28h] BYREF

  Context[0] = 0;
  if ( InitOnceExecuteOnce(&initPolicyCheckOnce, InitStoreAppsAreDisabled, 0, Context) && canDisableApps == 1 )
  {
    pcbData = 0;
    if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    {
      if ( (int)PolicyManager_GetPolicyInt(L"ApplicationManagement", L"DisableStoreOriginatedApps", &pcbData) >= 0
        && pcbData <= 1 )
      {
        if ( pcbData )
        {
          LogMessage(
            2u,
            "onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
            0x73u,
            "IsDisableStore",
            -1,
            L"MDM policy has blocked the running and updating of all Windows Store apps on this device.");
          if ( pcbData )
            return;
        }
        goto LABEL_8;
      }
    }
    else
    {
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
        0x47u,
        "GetPolicyInt",
        -1,
        L"Failed to read MDM policy on this device: PolicyManager_GetPolicyIntPresent API not present.");
    }
    v6 = 0;
    v7 = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\WindowsStore",
            L"DisableStoreApps",
            0x18u,
            0,
            &v6,
            &v7)
      && v6 )
    {
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
        0x85u,
        "IsDisableStore",
        -1,
        L"Group policy has blocked the running and updating of all Windows Store apps on this device.");
      return;
    }
  }
LABEL_8:
  pcbData = 4;
  pvData = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\PushToInstall",
         L"DisablePushToInstall",
         0x10u,
         0,
         &pvData,
         &pcbData)
    || pvData != 1 )
  {
    v4 = *a2;
    Context[0] = &PushToInstallCallback::`vftable';
    v5 = (unsigned __int16 **)(a2 + 1);
    Context[1] = 0;
    if ( a1 <= 1 )
      v5 = 0;
    ServiceMainImpl(v4, (struct ServiceMainCallback *)Context, a1 - 1, v5);
  }
}

```

## disassembly

```asm
0x18001fe50  mov     [rsp-8+arg_0], rbx
0x18001fe55  mov     [rsp-8+arg_8], rdi
0x18001fe5a  push    rbp
0x18001fe5b  mov     rbp, rsp
0x18001fe5e  sub     rsp, 60h
0x18001fe62  mov     rbx, rdx
0x18001fe65  mov     [rbp+Context], 0
0x18001fe6d  mov     edi, ecx
0x18001fe6f  lea     rdx, ?InitStoreAppsAreDisabled@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001fe76  lea     rcx, ?initPolicyCheckOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18001fe7d  xor     r8d, r8d; Parameter
0x18001fe80  lea     r9, [rbp+Context]; Context
0x18001fe84  call    cs:__imp_InitOnceExecuteOnce
0x18001fe8a  test    eax, eax
0x18001fe8c  jz      loc_18001FF21
0x18001fe92  cmp     cs:?canDisableApps@@3KA, 1; ulong canDisableApps
0x18001fe99  jnz     loc_18001FF21
0x18001fe9f  mov     [rbp+arg_18], 0
0x18001fea6  call    IsPolicyManager_GetPolicyIntPresent
0x18001feab  test    al, al
0x18001fead  jz      loc_18001FFB5
0x18001feb3  lea     r8, [rbp+arg_18]
0x18001feb7  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x18001febe  lea     rcx, aApplicationman; "ApplicationManagement"
0x18001fec5  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001fecb  shr     eax, 1Fh
0x18001fece  xor     al, 1
0x18001fed0  jz      loc_18001FFE6
0x18001fed6  mov     eax, [rbp+arg_18]
0x18001fed9  cmp     eax, 1
0x18001fedc  ja      loc_18001FFE6
0x18001fee2  test    eax, eax
0x18001fee4  jz      short loc_18001FF21
0x18001fee6  mov     r8d, 73h ; 's'; unsigned int
0x18001feec  lea     rax, aMdmPolicyHasBl; "MDM policy has blocked the running and "...
0x18001fef3  mov     [rsp+60h+pvData], rax; unsigned __int16 *
0x18001fef8  lea     r9, aIsdisablestore; "IsDisableStore"
0x18001feff  lea     rdx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18001ff06  mov     dword ptr [rsp+60h+pdwType], 0FFFFFFFFh; int
0x18001ff0e  lea     ecx, [r8-71h]; unsigned int
0x18001ff12  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18001ff17  cmp     [rbp+arg_18], 0
0x18001ff1b  jnz     loc_18001FFA5
0x18001ff21  lea     rax, [rbp+arg_18]
0x18001ff25  mov     [rbp+arg_18], 4
0x18001ff2c  mov     [rsp+60h+pcbData], rax; pcbData
0x18001ff31  lea     r8, Value; "DisablePushToInstall"
0x18001ff38  lea     rax, [rbp+arg_10]
0x18001ff3c  mov     [rbp+arg_10], 0
0x18001ff43  mov     [rsp+60h+pvData], rax; pvData
0x18001ff48  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\PushToIn"...
0x18001ff4f  mov     r9d, 10h; dwFlags
0x18001ff55  mov     [rsp+60h+pdwType], 0; pdwType
0x18001ff5e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ff65  call    cs:__imp_RegGetValueW
0x18001ff6b  test    eax, eax
0x18001ff6d  jnz     short loc_18001FF75
0x18001ff6f  cmp     [rbp+arg_10], 1
0x18001ff73  jz      short loc_18001FFA5
0x18001ff75  mov     rcx, [rbx]; lpServiceName
0x18001ff78  lea     rax, ??_7PushToInstallCallback@@6B@; const PushToInstallCallback::`vftable'
0x18001ff7f  mov     [rbp+Context], rax
0x18001ff83  lea     r9, [rbx+8]
0x18001ff87  xor     eax, eax
0x18001ff89  mov     [rbp+var_10], 0
0x18001ff91  cmp     edi, 1
0x18001ff94  lea     r8d, [rdi-1]; unsigned int
0x18001ff98  lea     rdx, [rbp+Context]; struct ServiceMainCallback *
0x18001ff9c  cmovbe  r9, rax; unsigned __int16 **
0x18001ffa0  call    ?ServiceMainImpl@@YAJPEBGPEAUServiceMainCallback@@KPEAPEAG@Z; ServiceMainImpl(ushort const *,ServiceMainCallback *,ulong,ushort * *)
0x18001ffa5  mov     rbx, [rsp+60h+arg_0]
0x18001ffaa  mov     rdi, [rsp+60h+arg_8]
0x18001ffaf  add     rsp, 60h
0x18001ffb3  pop     rbp
0x18001ffb4  retn
0x18001ffb5  mov     r8d, 47h ; 'G'; unsigned int
0x18001ffbb  lea     rax, aFailedToReadMd; "Failed to read MDM policy on this devic"...
0x18001ffc2  mov     [rsp+60h+pvData], rax; unsigned __int16 *
0x18001ffc7  lea     r9, aGetpolicyint; "GetPolicyInt"
0x18001ffce  lea     rdx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18001ffd5  mov     dword ptr [rsp+60h+pdwType], 0FFFFFFFFh; int
0x18001ffdd  lea     ecx, [r8-45h]; unsigned int
0x18001ffe1  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18001ffe6  lea     rax, [rbp+var_1C]
0x18001ffea  mov     [rbp+var_20], 0
0x18001fff1  mov     [rsp+60h+pcbData], rax; pcbData
0x18001fff6  lea     r8, aDisablestoreap; "DisableStoreApps"
0x18001fffd  lea     rax, [rbp+var_20]
0x180020001  mov     [rbp+var_1C], 4
0x180020008  mov     [rsp+60h+pvData], rax; pvData
0x18002000d  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\WindowsS"...
0x180020014  mov     r9d, 18h; dwFlags
0x18002001a  mov     [rsp+60h+pdwType], 0; pdwType
0x180020023  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002002a  call    cs:__imp_RegGetValueW
0x180020030  test    eax, eax
0x180020032  jnz     loc_18001FF21
0x180020038  cmp     [rbp+var_20], eax
0x18002003b  jz      loc_18001FF21
0x180020041  lea     rax, aGroupPolicyHas; "Group policy has blocked the running an"...
0x180020048  mov     r8d, 85h; unsigned int
0x18002004e  mov     [rsp+60h+pvData], rax; unsigned __int16 *
0x180020053  lea     r9, aIsdisablestore; "IsDisableStore"
0x18002005a  lea     rdx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180020061  mov     dword ptr [rsp+60h+pdwType], 0FFFFFFFFh; int
0x180020069  mov     ecx, 2; unsigned int
0x18002006e  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180020073  jmp     loc_18001FFA5
```
