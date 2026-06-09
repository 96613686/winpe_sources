# DdcToastHelper::PostToastNotification(uint,uint,ushort const *,ulong)

- ea: `0x18001b530`
- end: `0x18001b722`
- name: `?PostToastNotification@DdcToastHelper@@SAJIIPEBGK@Z`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180007838`

## callees

- `0x1800050b8`
- `0x180011e74`
- `0x18001b1e0`
- `0x18001b530`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b581`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b581`

## string_xrefs

- `0x18001b6d6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctoasthelper.cpp`
- `0x18001b59a`: `CHR(spPlatform.CoCreateInstance( __uuidof(CWindowsPushNotificationPlatform), 0, CLSCTX_LOCAL_SERVER))`
- `0x18001b5da`: `CHR(spPlatform->CreateAppEndpoint(&spAppEndpoint))`
- `0x18001b617`: `CHR(BuildToastPayload( uiResIdDescription, uiResIdAction, pcszDescriptionParam, cchDescriptionParam, &pszFormattedToastXMLPayload))`
- `0x18001b6c2`: `CHR(spAppEndpoint->PostNotification( pszPackageName, pszAppId, 0, WPN_FLAGS_NONE, pszFormattedToastXMLPayload, sc_szSettingsTag, sc_szSettingsGroup, wftExpirationTime, 0, 0, nullptr, nullptr, nullptr, 0, &dwCookie))`
- `0x18001b678`: `UpdateGroup`
- `0x18001b684`: `UpdateTag`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcToastHelper::PostToastNotification(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  int v3; // edx
  int v4; // ecx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  const unsigned __int16 *v8; // r8
  __int64 v9; // r9
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  __int64 v15; // [rsp+98h] [rbp+27h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+2Fh] BYREF
  _BYTE v17[12]; // [rsp+A8h] [rbp+37h]
  __int64 v18; // [rsp+B8h] [rbp+47h] BYREF
  int v19; // [rsp+C0h] [rbp+4Fh]
  LPVOID pv; // [rsp+E8h] [rbp+77h] BYREF
  int v21; // [rsp+F0h] [rbp+7Fh] BYREF

  pv = 0;
  *(_QWORD *)&v17[4] = 0;
  v21 = 0;
  ppv = 0;
  v15 = 0;
  v5 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v15);
    if ( v5 >= 0 )
    {
      *(_DWORD *)v17 = 0;
      v5 = DdcToastHelper::BuildToastPayload(v7, v6, v8, v9, (LPWSTR)&pv);
      if ( v5 >= 0 )
      {
        v18 = *(_QWORD *)v17;
        v19 = *(_DWORD *)&v17[8];
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _DWORD, LPVOID, const wchar_t *, const wchar_t *, __int64 *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(*(_QWORD *)v15 + 64LL))(
               v15,
               L"windows.immersivecontrolpanel_cw5n1h2txyewy",
               L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
               0,
               0,
               pv,
               L"UpdateTag",
               L"UpdateGroup",
               &v18,
               0,
               0,
               0,
               0,
               0,
               0,
               &v21);
        if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v13,
            v12,
            v5,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
            103,
            "CHR(spAppEndpoint->PostNotification( pszPackageName, pszAppId, 0, WPN_FLAGS_NONE, pszFormattedToastXMLPayloa"
            "d, sc_szSettingsTag, sc_szSettingsGroup, wftExpirationTime, 0, 0, nullptr, nullptr, nullptr, 0, &dwCookie))");
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
          83,
          "CHR(BuildToastPayload( uiResIdDescription, uiResIdAction, pcszDescriptionParam, cchDescriptionParam, &pszForma"
          "ttedToastXMLPayload))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        v5,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
        73,
        "CHR(spPlatform->CreateAppEndpoint(&spAppEndpoint))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      v3,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
      71,
      "CHR(spPlatform.CoCreateInstance( __uuidof(CWindowsPushNotificationPlatform), 0, CLSCTX_LOCAL_SERVER))");
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v15);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>((__int64 *)&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b530  mov     rax, rsp
0x18001b533  mov     [rax+8], rbx
0x18001b537  mov     [rax+10h], rdi
0x18001b53b  mov     [rax+20h], r9d
0x18001b53f  mov     [rax+18h], r8
0x18001b543  push    rbp
0x18001b544  lea     rbp, [rax-5Fh]
0x18001b548  sub     rsp, 0C0h
0x18001b54f  xor     edi, edi
0x18001b551  mov     [rbp+57h+pv], rdi
0x18001b555  mov     [rbp+57h+var_20+4], rdi
0x18001b559  mov     [rbp+57h+arg_18], edi
0x18001b55c  mov     [rbp+57h+var_28], rdi
0x18001b560  mov     [rbp+57h+var_30], rdi
0x18001b564  lea     rax, [rbp+57h+var_28]
0x18001b568  mov     [rsp+0C0h+ppv], rax; ppv
0x18001b56d  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18001b574  xor     edx, edx; pUnkOuter
0x18001b576  lea     r8d, [rdi+4]; dwClsContext
0x18001b57a  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18001b581  call    cs:__imp_CoCreateInstance
0x18001b587  mov     ebx, eax
0x18001b589  test    eax, eax
0x18001b58b  jns     short loc_18001B5B3
0x18001b58d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b594  jz      loc_18001B6E5
0x18001b59a  lea     rax, aChrSpplatformC_0; "CHR(spPlatform.CoCreateInstance( __uuid"...
0x18001b5a1  mov     [rsp+0C0h+var_98], rax
0x18001b5a6  mov     dword ptr [rsp+0C0h+ppv], 47h ; 'G'
0x18001b5ae  jmp     loc_18001B6D6
0x18001b5b3  mov     rcx, [rbp+57h+var_28]
0x18001b5b7  mov     rax, [rcx]
0x18001b5ba  lea     rdx, [rbp+57h+var_30]
0x18001b5be  mov     rax, [rax+18h]
0x18001b5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c7  mov     ebx, eax
0x18001b5c9  test    eax, eax
0x18001b5cb  jns     short loc_18001B5F3
0x18001b5cd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b5d4  jz      loc_18001B6E5
0x18001b5da  lea     rax, aChrSpplatformC; "CHR(spPlatform->CreateAppEndpoint(&spAp"...
0x18001b5e1  mov     [rsp+0C0h+var_98], rax
0x18001b5e6  mov     dword ptr [rsp+0C0h+ppv], 49h ; 'I'
0x18001b5ee  jmp     loc_18001B6D6
0x18001b5f3  mov     dword ptr [rbp+57h+var_20], edi
0x18001b5f6  lea     rax, [rbp+57h+pv]
0x18001b5fa  mov     [rsp+0C0h+ppv], rax; lpBuffer
0x18001b5ff  call    ?BuildToastPayload@DdcToastHelper@@CAJIIPEBGKPEAPEAG@Z; DdcToastHelper::BuildToastPayload(uint,uint,ushort const *,ulong,ushort * *)
0x18001b604  mov     ebx, eax
0x18001b606  test    eax, eax
0x18001b608  jns     short loc_18001B630
0x18001b60a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b611  jz      loc_18001B6E5
0x18001b617  lea     rax, aChrBuildtoastp; "CHR(BuildToastPayload( uiResIdDescripti"...
0x18001b61e  mov     [rsp+0C0h+var_98], rax
0x18001b623  mov     dword ptr [rsp+0C0h+ppv], 53h ; 'S'
0x18001b62b  jmp     loc_18001B6D6
0x18001b630  mov     rcx, [rbp+57h+var_30]
0x18001b634  mov     rdx, [rbp+57h+pv]
0x18001b638  movsd   xmm0, [rbp+57h+var_20]
0x18001b63d  movsd   [rbp+57h+var_10], xmm0
0x18001b642  mov     eax, [rbp+57h+var_18]
0x18001b645  mov     [rbp+57h+var_8], eax
0x18001b648  mov     rax, [rcx]
0x18001b64b  lea     r8, [rbp+57h+arg_18]
0x18001b64f  mov     [rsp+0C0h+var_48], r8
0x18001b654  mov     dword ptr [rsp+0C0h+var_50], edi
0x18001b658  mov     qword ptr [rsp+0C0h+var_58], rdi
0x18001b65d  mov     [rsp+0C0h+var_60], rdi
0x18001b662  mov     [rsp+0C0h+var_68], rdi
0x18001b667  mov     dword ptr [rsp+0C0h+var_70], edi
0x18001b66b  mov     [rsp+0C0h+var_78], edi
0x18001b66f  lea     r8, [rbp+57h+var_10]
0x18001b673  mov     qword ptr [rsp+0C0h+var_80], r8
0x18001b678  lea     r8, aUpdategroup; "UpdateGroup"
0x18001b67f  mov     [rsp+0C0h+var_88], r8
0x18001b684  lea     r8, aUpdatetag; "UpdateTag"
0x18001b68b  mov     [rsp+0C0h+var_90], r8
0x18001b690  mov     [rsp+0C0h+var_98], rdx
0x18001b695  mov     dword ptr [rsp+0C0h+ppv], edi
0x18001b699  xor     r9d, r9d
0x18001b69c  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18001b6a3  lea     rdx, aWindowsImmersi_0; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18001b6aa  mov     rax, [rax+40h]
0x18001b6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6b3  mov     ebx, eax
0x18001b6b5  test    eax, eax
0x18001b6b7  jns     short loc_18001B6E5
0x18001b6b9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b6c0  jz      short loc_18001B6E5
0x18001b6c2  lea     rax, aChrSpappendpoi; "CHR(spAppEndpoint->PostNotification( ps"...
0x18001b6c9  mov     [rsp+0C0h+var_98], rax
0x18001b6ce  mov     dword ptr [rsp+0C0h+ppv], 67h ; 'g'
0x18001b6d6  lea     r9, aOnecoreuapShel_15; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001b6dd  mov     r8d, ebx
0x18001b6e0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b6e5  mov     rcx, [rbp+57h+pv]; pv
0x18001b6e9  test    rcx, rcx
0x18001b6ec  jz      short loc_18001B6F8
0x18001b6ee  call    cs:__imp_CoTaskMemFree
0x18001b6f4  mov     [rbp+57h+pv], rdi
0x18001b6f8  lea     rcx, [rbp+57h+var_30]
0x18001b6fc  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x18001b701  nop
0x18001b702  lea     rcx, [rbp+57h+var_28]
0x18001b706  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x18001b70b  mov     eax, ebx
0x18001b70d  lea     r11, [rsp+0C0h+var_s0]
0x18001b715  mov     rbx, [r11+10h]
0x18001b719  mov     rdi, [r11+18h]
0x18001b71d  mov     rsp, r11
0x18001b720  pop     rbp
0x18001b721  retn
```
