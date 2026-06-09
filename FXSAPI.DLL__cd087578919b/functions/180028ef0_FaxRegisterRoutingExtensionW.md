# FaxRegisterRoutingExtensionW

- ea: `0x180028ef0`
- end: `0x180029bc9`
- name: `FaxRegisterRoutingExtensionW`
- size: `3289`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, LPCWSTR ExtensionName, LPCWSTR FriendlyName, LPCWSTR ImageName, PFAX_ROUTING_INSTALLATION_CALLBACKW CallBack, LPVOID Context)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008374`
- `0x180008438`
- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x18000c0d0`
- `0x180016124`
- `0x180021530`
- `0x180027b70`
- `0x180028c8c`
- `0x180028ef0`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002bb9c`
- `0x18002c31c`
- `0x18002cd9c`
- `0x18002d4cc`
- `0x18002d54c`
- `0x18002d854`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003d5a0`
- `0x18003e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180029034`
- `msvcrt!_wcsicmp` at `0x1800295c5`
- `msvcrt!_wcsicmp` at `0x180029608`
- `msvcrt!_wcsicmp` at `0x180029034`
- `msvcrt!_wcsicmp` at `0x1800295c5`
- `msvcrt!_wcsicmp` at `0x180029608`
- `KERNEL32!SetLastError` at `0x180029b25`
- `KERNEL32!SetLastError` at `0x180029b3b`
- `KERNEL32!SetLastError` at `0x180029b97`
- `KERNEL32!SetLastError` at `0x180029b25`
- `KERNEL32!SetLastError` at `0x180029b3b`
- `KERNEL32!SetLastError` at `0x180029b97`
- `KERNEL32!GetLastError` at `0x1800290b6`
- `KERNEL32!GetLastError` at `0x1800291c0`
- `KERNEL32!GetLastError` at `0x1800293c7`
- `KERNEL32!GetLastError` at `0x180029671`
- `KERNEL32!GetLastError` at `0x1800298fb`
- `KERNEL32!GetLastError` at `0x1800290b6`
- `KERNEL32!GetLastError` at `0x1800291c0`
- `KERNEL32!GetLastError` at `0x1800293c7`
- `KERNEL32!GetLastError` at `0x180029671`
- `KERNEL32!GetLastError` at `0x1800298fb`
- `ADVAPI32!RegCloseKey` at `0x180029254`
- `ADVAPI32!RegCloseKey` at `0x1800294b0`
- `ADVAPI32!RegCloseKey` at `0x18002994b`
- `ADVAPI32!RegCloseKey` at `0x180029a59`
- `ADVAPI32!RegCloseKey` at `0x180029a99`
- `ADVAPI32!RegCloseKey` at `0x180029254`
- `ADVAPI32!RegCloseKey` at `0x1800294b0`
- `ADVAPI32!RegCloseKey` at `0x18002994b`
- `ADVAPI32!RegCloseKey` at `0x180029a59`
- `ADVAPI32!RegCloseKey` at `0x180029a99`

## string_xrefs

- `0x180029028`: `Microsoft Routing Extension`
- `0x1800290f9`: `Routing Extensions`
- `0x18002933b`: `Routing Extensions`
- `0x1800297cc`: `Routing Extensions`
- `0x1800298d8`: `Routing Extensions`
- `0x180029934`: `Routing Extensions`

## pseudocode

```c
BOOL __stdcall FaxRegisterRoutingExtensionW(
        HANDLE FaxHandle,
        LPCWSTR ExtensionName,
        LPCWSTR FriendlyName,
        LPCWSTR ImageName,
        PFAX_ROUTING_INSTALLATION_CALLBACKW CallBack,
        LPVOID Context)
{
  PFAX_ROUTING_INSTALLATION_CALLBACKW v9; // rax
  _QWORD *v10; // rcx
  DWORD v11; // ecx
  DWORD LastError; // eax
  int v13; // eax
  signed int v14; // ebx
  HKEY v15; // rax
  HKEY v16; // rax
  HKEY v17; // rbx
  DWORD v18; // eax
  unsigned int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  HKEY v24; // r12
  DWORD v25; // eax
  unsigned int v26; // eax
  BOOL v27; // r12d
  __int64 v28; // rax
  signed int valid; // eax
  signed int v30; // r12d
  int v31; // r12d
  DWORD v32; // r13d
  const wchar_t **v33; // r13
  int v34; // r12d
  DWORD v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  unsigned __int16 *v41; // rax
  unsigned __int16 *v42; // r13
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rdx
  int v46; // eax
  signed int v47; // r12d
  unsigned __int64 v48; // rcx
  void *v49; // rax
  unsigned int v50; // eax
  int v51; // eax
  __int64 v52; // rax
  HKEY v53; // r13
  int v54; // eax
  unsigned int v55; // eax
  LPVOID *v56; // r14
  DWORD v57; // esi
  DWORD v58; // r15d
  int v60; // [rsp+20h] [rbp-1398h]
  DWORD MethodsReturned; // [rsp+40h] [rbp-1378h] BYREF
  DWORD v62; // [rsp+44h] [rbp-1374h]
  wchar_t *String1; // [rsp+48h] [rbp-1370h]
  HKEY hKey; // [rsp+50h] [rbp-1368h]
  LPVOID lpMem; // [rsp+58h] [rbp-1360h]
  PFAX_GLOBAL_ROUTING_INFOW RoutingInfo; // [rsp+60h] [rbp-1358h] BYREF
  PFAX_ROUTING_INSTALLATION_CALLBACKW v67; // [rsp+68h] [rbp-1350h]
  LPVOID v68; // [rsp+70h] [rbp-1348h]
  HANDLE v69; // [rsp+78h] [rbp-1340h]
  HKEY v70; // [rsp+80h] [rbp-1338h]
  LPCWSTR v71; // [rsp+88h] [rbp-1330h]
  wchar_t String2[104]; // [rsp+90h] [rbp-1328h] BYREF
  WCHAR SubKey[104]; // [rsp+160h] [rbp-1258h] BYREF
  unsigned __int16 v74[104]; // [rsp+230h] [rbp-1188h] BYREF
  unsigned __int16 v75[104]; // [rsp+300h] [rbp-10B8h] BYREF
  unsigned __int16 v76[2000]; // [rsp+3D0h] [rbp-FE8h] BYREF

  String1 = (wchar_t *)ExtensionName;
  v69 = FaxHandle;
  v71 = ExtensionName;
  v9 = CallBack;
  v67 = CallBack;
  v68 = Context;
  RoutingInfo = 0;
  MethodsReturned = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    v10 = WPP_GLOBAL_Control;
    v9 = v67;
    ExtensionName = String1;
  }
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x1000) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_(v10[2], 11, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    v11 = 6;
    goto LABEL_199;
  }
  if ( !ExtensionName || !FriendlyName || !ImageName || !v9 )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    }
    return 0;
  }
  if ( !(unsigned int)IsLocalFaxConnection(FaxHandle) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    }
    v11 = 1;
LABEL_199:
    SetLastError(v11);
    return 0;
  }
  if ( _wcsicmp(String1, L"Microsoft Routing Extension") && !(unsigned int)IsServerSku() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
    }
    v11 = 7011;
    goto LABEL_199;
  }
  if ( !FaxEnumGlobalRoutingInfoW(FaxHandle, &RoutingInfo, &MethodsReturned) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, LastError);
    }
    return 0;
  }
  v62 = MethodsReturned;
  lpMem = 0;
  v13 = StringCchPrintfW(v76, 0x7D0u, L"%s\\%s\\%s", L"Software\\Microsoft\\Fax");
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
        (unsigned int)v13);
    }
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v14 = (unsigned __int16)v14;
LABEL_182:
    v27 = 0;
    goto LABEL_183;
  }
  v15 = (HKEY)OpenRegistryKey(-2147483646, v76, 0, 131359);
  if ( v15 )
  {
    RegCloseKey(v15);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v76);
    }
    v14 = 87;
    goto LABEL_182;
  }
  v16 = (HKEY)OpenRegistryKey(-2147483646, v76, 1, 131359);
  v17 = v16;
  hKey = v16;
  if ( !v16 )
  {
    v18 = GetLastError();
    v14 = v18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
        (unsigned int)v76,
        v18);
    }
    goto LABEL_182;
  }
  if ( !SetRegistryStringValue(v16, 1u, L"FriendlyName", FriendlyName, (int)L"Routing Extensions")
    || !SetRegistryStringValue(v17, 2u, L"ImageName", ImageName, v60) )
  {
    v35 = GetLastError();
    v14 = v35;
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = 19;
LABEL_154:
      WPP_SF_d(v36[2], v37, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v35);
    }
    goto LABEL_155;
  }
  v19 = RegCloseKey(v17);
  if ( !v19 )
    goto LABEL_50;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v19);
LABEL_50:
    v20 = WPP_GLOBAL_Control;
  }
  v21 = -1;
  do
    ++v21;
  while ( v76[v21] );
  if ( (unsigned __int64)(v21 + 16) >= 0x7D0 )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x1000) != 0 && *((_BYTE *)v20 + 25) >= 2u )
      WPP_SF_S(v20[2], 21, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v76);
LABEL_58:
    v14 = 87;
    goto LABEL_155;
  }
  v14 = StringCchCatW(v76, 0x7D0u, L"\\");
  if ( v14 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = 22;
LABEL_64:
      WPP_SF_d(v22[2], v23, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, (unsigned int)v14);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  v14 = StringCchCatW(v76, 0x7D0u, L"Routing Methods");
  if ( v14 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = 23;
      goto LABEL_64;
    }
LABEL_65:
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v14 = (unsigned __int16)v14;
    goto LABEL_155;
  }
  v24 = (HKEY)OpenRegistryKey(-2147483646, v76, 1, 131359);
  hKey = v24;
  v70 = v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    v14 = v25;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
        (unsigned int)v76,
        v25);
    }
    goto LABEL_155;
  }
  v14 = 0;
  while ( 1 )
  {
    memset_0(SubKey, 0, 0xCAu);
    memset_0(v75, 0, 0xCAu);
    memset_0(v74, 0, 0xCAu);
    memset_0(String2, 0, 0xCAu);
    if ( !((unsigned int (__fastcall *)(HANDLE, LPVOID, WCHAR *, unsigned __int16 *, unsigned __int16 *, wchar_t *))v67)(
            v69,
            v68,
            SubKey,
            v75,
            v74,
            String2) )
    {
      v26 = RegCloseKey(v24);
      if ( v26 )
      {
        v14 = v26;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v26);
        }
      }
      v27 = 1;
      goto LABEL_183;
    }
    v28 = -1;
    do
      ++v28;
    while ( SubKey[v28] );
    if ( !v28 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
      }
      goto LABEL_58;
    }
    valid = IsValidGUID(String2);
    v30 = valid;
    if ( valid )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
          (unsigned int)String2,
          valid);
      }
      v14 = v30;
      goto LABEL_155;
    }
    v31 = 0;
    v32 = v62;
    if ( v62 )
    {
      while ( _wcsicmp(RoutingInfo[v31].Guid, String2) )
      {
        if ( ++v31 >= v32 )
          goto LABEL_101;
      }
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = 28;
        goto LABEL_114;
      }
      goto LABEL_115;
    }
LABEL_101:
    v33 = (const wchar_t **)lpMem;
    if ( lpMem )
    {
      v34 = 0;
      if ( MethodsReturned != v62 )
      {
        while ( _wcsicmp(v33[v34], String2) )
        {
          if ( ++v34 >= MethodsReturned - v62 )
            goto LABEL_105;
        }
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = 29;
LABEL_114:
          WPP_SF_S(v38[2], v39, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, String2);
        }
LABEL_115:
        v14 = 8361;
        goto LABEL_155;
      }
    }
LABEL_105:
    if ( !(unsigned int)AddMethodKey(hKey, SubKey, v75, v74, String2, ++MethodsReturned) )
    {
      v35 = GetLastError();
      v14 = v35;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v37 = 30;
        goto LABEL_154;
      }
      goto LABEL_155;
    }
    v40 = -1;
    do
      ++v40;
    while ( String2[v40] );
    v41 = (unsigned __int16 *)pMemAlloc(2 * v40 + 2);
    v42 = v41;
    if ( !v41 )
    {
      v14 = 8;
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = 31;
        goto LABEL_127;
      }
      goto LABEL_155;
    }
    v45 = -1;
    do
      ++v45;
    while ( String2[v45] );
    v46 = StringCchCopyW(v41, v45 + 1, String2);
    v47 = v46;
    if ( v46 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
          (unsigned int)v46);
      }
      if ( (v47 & 0x1FFF0000) == 0x70000 )
        v14 = (unsigned __int16)v47;
      else
        v14 = v47;
      goto LABEL_155;
    }
    if ( MethodsReturned < v62 || (v48 = 8LL * (MethodsReturned - v62), v48 > 0xFFFFFFFF) )
    {
      v14 = 534;
      goto LABEL_155;
    }
    v49 = (void *)(lpMem ? pMemReAlloc(lpMem, (unsigned int)v48) : pMemAlloc((unsigned int)v48));
    if ( !v49 )
      break;
    lpMem = v49;
    *((_QWORD *)v49 + MethodsReturned - v62 - 1) = v42;
    v24 = hKey;
  }
  v14 = 8;
  v43 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v44 = 33;
LABEL_127:
    WPP_SF_(v43[2], v44, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
LABEL_155:
  v27 = 0;
  if ( hKey )
  {
    v50 = RegCloseKey(hKey);
    if ( v50 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v50);
      }
    }
  }
  v51 = StringCchPrintfW(v76, 0x7D0u, L"%s\\%s", L"Software\\Microsoft\\Fax", L"Routing Extensions");
  if ( v51 >= 0 )
  {
    v52 = OpenRegistryKey(-2147483646, v76, 0, 131359);
    v53 = (HKEY)v52;
    if ( v52 )
    {
      v54 = DeleteRegistryKey(v52, String1);
      if ( v54
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)&WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
          (_DWORD)String1,
          v54);
      }
      v55 = RegCloseKey(v53);
      if ( v55
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v55);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids,
      (unsigned int)v51);
  }
LABEL_183:
  pMemFree(RoutingInfo);
  v56 = (LPVOID *)lpMem;
  if ( lpMem )
  {
    v57 = 0;
    v58 = v62;
    if ( MethodsReturned != v62 )
    {
      do
        pMemFree(v56[v57++]);
      while ( v57 < MethodsReturned - v58 );
    }
    pMemFree(v56);
  }
  if ( v14 )
    SetLastError(v14);
  return v27;
}

```

## disassembly

```asm
0x180028ef0  push    rbx
0x180028ef2  push    rsi
0x180028ef3  push    rdi
0x180028ef4  push    r12
0x180028ef6  push    r13
0x180028ef8  push    r14
0x180028efa  push    r15
0x180028efc  mov     eax, 1380h
0x180028f01  call    _alloca_probe
0x180028f06  sub     rsp, rax
0x180028f09  mov     rax, cs:__security_cookie
0x180028f10  xor     rax, rsp
0x180028f13  mov     [rsp+13B8h+var_48], rax
0x180028f1b  mov     r13, r9
0x180028f1e  mov     r12, r8
0x180028f21  mov     [rsp+13B8h+String1], rdx
0x180028f26  mov     rbx, rcx
0x180028f29  mov     [rsp+13B8h+var_1340], rcx
0x180028f2e  mov     [rsp+13B8h+var_1330], rdx
0x180028f36  mov     rax, [rsp+13B8h+CallBack]
0x180028f3e  mov     [rsp+13B8h+var_1350], rax
0x180028f43  mov     rcx, [rsp+13B8h+Context]
0x180028f4b  mov     [rsp+13B8h+var_1348], rcx
0x180028f50  xor     edi, edi
0x180028f52  mov     [rsp+13B8h+RoutingInfo], rdi
0x180028f57  mov     [rsp+13B8h+MethodsReturned], edi
0x180028f5b  lea     r15, WPP_GLOBAL_Control
0x180028f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f69  mov     esi, 1000h
0x180028f6e  cmp     rcx, r15
0x180028f71  jz      short loc_180028FA7
0x180028f73  test    [rcx+1Ch], esi
0x180028f76  jz      short loc_180028FA7
0x180028f78  cmp     byte ptr [rcx+19h], 5
0x180028f7c  jb      short loc_180028FA7
0x180028f7e  lea     edx, [rdi+0Ah]
0x180028f81  lea     r14, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028f88  mov     r8, r14
0x180028f8b  mov     rcx, [rcx+10h]
0x180028f8f  call    WPP_SF_
0x180028f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f9b  mov     rax, [rsp+13B8h+var_1350]
0x180028fa0  mov     rdx, [rsp+13B8h+String1]
0x180028fa5  jmp     short loc_180028FAE
0x180028fa7  lea     r14, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028fae  test    rbx, rbx
0x180028fb1  jz      loc_180029B71
0x180028fb7  cmp     [rbx], edi
0x180028fb9  jz      loc_180029B71
0x180028fbf  cmp     [rbx+10h], edi
0x180028fc2  jnz     loc_180029B71
0x180028fc8  test    rdx, rdx
0x180028fcb  jz      loc_180029B36
0x180028fd1  test    r12, r12
0x180028fd4  jz      loc_180029B36
0x180028fda  test    r13, r13
0x180028fdd  jz      loc_180029B36
0x180028fe3  test    rax, rax
0x180028fe6  jz      loc_180029B36
0x180028fec  mov     rcx, rbx; void *
0x180028fef  call    ?IsLocalFaxConnection@@YAHPEAX@Z; IsLocalFaxConnection(void *)
0x180028ff4  test    eax, eax
0x180028ff6  jnz     short loc_180029028
0x180028ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fff  cmp     rcx, r15
0x180029002  jz      short loc_18002901E
0x180029004  test    [rcx+1Ch], esi
0x180029007  jz      short loc_18002901E
0x180029009  cmp     byte ptr [rcx+19h], 2
0x18002900d  jb      short loc_18002901E
0x18002900f  lea     edx, [rax+0Dh]
0x180029012  mov     r8, r14
0x180029015  mov     rcx, [rcx+10h]
0x180029019  call    WPP_SF_
0x18002901e  mov     ecx, 1
0x180029023  jmp     loc_180029B97
0x180029028  lea     rdx, aMicrosoftRouti; "Microsoft Routing Extension"
0x18002902f  mov     rcx, [rsp+13B8h+String1]; String1
0x180029034  call    cs:__imp__wcsicmp
0x18002903b  nop     dword ptr [rax+rax+00h]
0x180029040  test    eax, eax
0x180029042  jz      short loc_18002907D
0x180029044  call    IsServerSku
0x180029049  test    eax, eax
0x18002904b  jnz     short loc_18002907D
0x18002904d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029054  cmp     rcx, r15
0x180029057  jz      short loc_180029073
0x180029059  test    [rcx+1Ch], esi
0x18002905c  jz      short loc_180029073
0x18002905e  cmp     byte ptr [rcx+19h], 2
0x180029062  jb      short loc_180029073
0x180029064  lea     edx, [rax+0Eh]
0x180029067  mov     r8, r14
0x18002906a  mov     rcx, [rcx+10h]
0x18002906e  call    WPP_SF_
0x180029073  mov     ecx, 1B63h
0x180029078  jmp     loc_180029B97
0x18002907d  lea     r8, [rsp+13B8h+MethodsReturned]; MethodsReturned
0x180029082  lea     rdx, [rsp+13B8h+RoutingInfo]; RoutingInfo
0x180029087  mov     rcx, rbx; FaxHandle
0x18002908a  call    FaxEnumGlobalRoutingInfoW
0x18002908f  test    eax, eax
0x180029091  jnz     short loc_1800290E2
0x180029093  mov     rax, cs:WPP_GLOBAL_Control
0x18002909a  cmp     rax, r15
0x18002909d  jz      loc_180029BA3
0x1800290a3  test    [rax+1Ch], esi
0x1800290a6  jz      loc_180029BA3
0x1800290ac  cmp     byte ptr [rax+19h], 2
0x1800290b0  jb      loc_180029BA3
0x1800290b6  call    cs:__imp_GetLastError
0x1800290bd  nop     dword ptr [rax+rax+00h]
0x1800290c2  mov     edx, 0Fh
0x1800290c7  mov     r9d, eax
0x1800290ca  mov     r8, r14
0x1800290cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290d4  mov     rcx, [rcx+10h]
0x1800290d8  call    WPP_SF_d
0x1800290dd  jmp     loc_180029BA3
0x1800290e2  mov     eax, [rsp+13B8h+MethodsReturned]
0x1800290e6  mov     [rsp+13B8h+var_1374], eax
0x1800290ea  mov     [rsp+13B8h+lpMem], rdi
0x1800290ef  mov     rax, [rsp+13B8h+String1]
0x1800290f4  mov     qword ptr [rsp+13B8h+var_1390], rax
0x1800290f9  lea     rax, aRoutingExtensi; "Routing Extensions"
0x180029100  mov     [rsp+13B8h+var_1398], rax; int
0x180029105  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Fax"
0x18002910c  lea     r8, aSSS; "%s\\%s\\%s"
0x180029113  mov     edx, 7D0h; unsigned __int64
0x180029118  lea     rcx, [rsp+13B8h+var_FE8]; unsigned __int16 *
0x180029120  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029125  mov     ebx, eax
0x180029127  test    eax, eax
0x180029129  jns     short loc_180029170
0x18002912b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029132  cmp     rcx, r15
0x180029135  jz      short loc_180029156
0x180029137  test    [rcx+1Ch], esi
0x18002913a  jz      short loc_180029156
0x18002913c  cmp     byte ptr [rcx+19h], 2
0x180029140  jb      short loc_180029156
0x180029142  mov     edx, 10h
0x180029147  mov     r9d, eax
0x18002914a  mov     r8, r14
0x18002914d  mov     rcx, [rcx+10h]
0x180029151  call    WPP_SF_d
0x180029156  mov     eax, ebx
0x180029158  and     eax, 1FFF0000h
0x18002915d  cmp     eax, 70000h
0x180029162  jnz     loc_180029ADA
0x180029168  movzx   ebx, bx
0x18002916b  jmp     loc_180029ADA
0x180029170  mov     ebx, 2011Fh
0x180029175  mov     r9d, ebx
0x180029178  xor     r8d, r8d
0x18002917b  lea     rdx, [rsp+13B8h+var_FE8]
0x180029183  mov     rcx, 0FFFFFFFF80000002h
0x18002918a  call    OpenRegistryKey
0x18002918f  test    rax, rax
0x180029192  jnz     loc_180029A96
0x180029198  mov     r9d, ebx
0x18002919b  lea     r8d, [rax+1]
0x18002919f  lea     rdx, [rsp+13B8h+var_FE8]
0x1800291a7  mov     rcx, 0FFFFFFFF80000002h
0x1800291ae  call    OpenRegistryKey
0x1800291b3  mov     rbx, rax
0x1800291b6  mov     [rsp+13B8h+hKey], rax
0x1800291bb  test    rax, rax
0x1800291be  jnz     short loc_180029213
0x1800291c0  call    cs:__imp_GetLastError
0x1800291c7  nop     dword ptr [rax+rax+00h]
0x1800291cc  mov     ebx, eax
0x1800291ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291d5  cmp     rcx, r15
0x1800291d8  jz      loc_180029ADA
0x1800291de  test    [rcx+1Ch], esi
0x1800291e1  jz      loc_180029ADA
0x1800291e7  cmp     byte ptr [rcx+19h], 2
0x1800291eb  jb      loc_180029ADA
0x1800291f1  mov     edx, 11h
0x1800291f6  mov     dword ptr [rsp+13B8h+var_1398], eax
0x1800291fa  lea     r9, [rsp+13B8h+var_FE8]
0x180029202  mov     r8, r14
0x180029205  mov     rcx, [rcx+10h]
0x180029209  call    WPP_SF_Sd
0x18002920e  jmp     loc_180029ADA
0x180029213  mov     r9, r12; unsigned __int16 *
0x180029216  lea     r8, aFriendlyname; "FriendlyName"
0x18002921d  mov     edx, 1; unsigned int
0x180029222  mov     rcx, rbx; HKEY
0x180029225  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18002922a  test    eax, eax
0x18002922c  jz      loc_1800298FB
0x180029232  mov     r9, r13; unsigned __int16 *
0x180029235  lea     r8, aImagename; "ImageName"
0x18002923c  mov     edx, 2; unsigned int
0x180029241  mov     rcx, rbx; HKEY
0x180029244  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x180029249  test    eax, eax
0x18002924b  jz      loc_1800298FB
0x180029251  mov     rcx, rbx; hKey
0x180029254  call    cs:__imp_RegCloseKey
0x18002925b  nop     dword ptr [rax+rax+00h]
0x180029260  test    eax, eax
0x180029262  jz      short loc_18002928F
0x180029264  mov     rcx, cs:WPP_GLOBAL_Control
0x18002926b  cmp     rcx, r15
0x18002926e  jz      short loc_180029296
0x180029270  test    [rcx+1Ch], esi
0x180029273  jz      short loc_180029296
0x180029275  cmp     byte ptr [rcx+19h], 2
0x180029279  jb      short loc_180029296
0x18002927b  mov     edx, 14h
0x180029280  mov     r9d, eax
0x180029283  mov     r8, r14
0x180029286  mov     rcx, [rcx+10h]
0x18002928a  call    WPP_SF_d
0x18002928f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029296  lea     rdx, [rsp+13B8h+var_FE8]
0x18002929e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800292a2  inc     rax
0x1800292a5  cmp     [rdx+rax*2], di
0x1800292a9  jnz     short loc_1800292A2
0x1800292ab  add     rax, 10h
0x1800292af  cmp     rax, 7D0h
0x1800292b5  jb      short loc_1800292EA
0x1800292b7  cmp     rcx, r15
0x1800292ba  jz      short loc_1800292E0
0x1800292bc  test    [rcx+1Ch], esi
0x1800292bf  jz      short loc_1800292E0
0x1800292c1  cmp     byte ptr [rcx+19h], 2
0x1800292c5  jb      short loc_1800292E0
0x1800292c7  mov     edx, 15h
0x1800292cc  lea     r9, [rsp+13B8h+var_FE8]
0x1800292d4  mov     r8, r14
0x1800292d7  mov     rcx, [rcx+10h]
0x1800292db  call    WPP_SF_S
0x1800292e0  mov     ebx, 57h ; 'W'
0x1800292e5  jmp     loc_180029934
0x1800292ea  lea     r8, SubBlock; "\\"
0x1800292f1  mov     edx, 7D0h; unsigned __int64
0x1800292f6  lea     rcx, [rsp+13B8h+var_FE8]; unsigned __int16 *
0x1800292fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029303  mov     ebx, eax
0x180029305  test    eax, eax
0x180029307  jns     short loc_180029355
0x180029309  mov     rcx, cs:WPP_GLOBAL_Control
0x180029310  cmp     rcx, r15
0x180029313  jz      short loc_180029334
0x180029315  test    [rcx+1Ch], esi
0x180029318  jz      short loc_180029334
0x18002931a  cmp     byte ptr [rcx+19h], 2
0x18002931e  jb      short loc_180029334
0x180029320  mov     edx, 16h
0x180029325  mov     r9d, ebx
0x180029328  mov     r8, r14
0x18002932b  mov     rcx, [rcx+10h]
0x18002932f  call    WPP_SF_d
0x180029334  mov     eax, ebx
0x180029336  and     eax, 1FFF0000h
0x18002933b  lea     r13, aRoutingExtensi; "Routing Extensions"
0x180029342  cmp     eax, 70000h
0x180029347  jnz     loc_18002993B
0x18002934d  movzx   ebx, bx
0x180029350  jmp     loc_18002993B
0x180029355  lea     r8, aRoutingMethods; "Routing Methods"
0x18002935c  mov     edx, 7D0h; unsigned __int64
0x180029361  lea     rcx, [rsp+13B8h+var_FE8]; unsigned __int16 *
0x180029369  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002936e  mov     ebx, eax
0x180029370  test    eax, eax
0x180029372  jns     short loc_180029392
0x180029374  mov     rcx, cs:WPP_GLOBAL_Control
0x18002937b  cmp     rcx, r15
0x18002937e  jz      short loc_180029334
0x180029380  test    [rcx+1Ch], esi
0x180029383  jz      short loc_180029334
0x180029385  cmp     byte ptr [rcx+19h], 2
0x180029389  jb      short loc_180029334
0x18002938b  mov     edx, 17h
0x180029390  jmp     short loc_180029325
0x180029392  mov     r9d, 2011Fh
0x180029398  mov     r8d, 1
0x18002939e  lea     rdx, [rsp+13B8h+var_FE8]
0x1800293a6  mov     rcx, 0FFFFFFFF80000002h
0x1800293ad  call    OpenRegistryKey
0x1800293b2  mov     r12, rax
0x1800293b5  mov     [rsp+13B8h+hKey], rax
0x1800293ba  mov     [rsp+13B8h+var_1338], rax
0x1800293c2  test    rax, rax
0x1800293c5  jnz     short loc_18002941A
0x1800293c7  call    cs:__imp_GetLastError
0x1800293ce  nop     dword ptr [rax+rax+00h]
0x1800293d3  mov     ebx, eax
0x1800293d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293dc  cmp     rcx, r15
0x1800293df  jz      loc_180029934
0x1800293e5  test    [rcx+1Ch], esi
0x1800293e8  jz      loc_180029934
  ... truncated ...
```
