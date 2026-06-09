# DetectManagedStatus(int *)

- ea: `0x18000bf00`
- end: `0x18000ca12`
- name: `?DetectManagedStatus@@YAJPEAH@Z`
- size: `2834`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001eca0`

## callees

- `0x180009e04`
- `0x18000ba68`
- `0x18000bf00`
- `0x180011358`
- `0x180021140`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c1b0`
- `msvcrt!_wcsicmp` at `0x18000c1c8`
- `msvcrt!_wcsicmp` at `0x18000c1e0`
- `msvcrt!_wcsicmp` at `0x18000c1f8`
- `msvcrt!_wcsicmp` at `0x18000c210`
- `msvcrt!_wcsicmp` at `0x18000c1b0`
- `msvcrt!_wcsicmp` at `0x18000c1c8`
- `msvcrt!_wcsicmp` at `0x18000c1e0`
- `msvcrt!_wcsicmp` at `0x18000c1f8`
- `msvcrt!_wcsicmp` at `0x18000c210`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c534`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c534`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c431`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bf6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c032`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bf6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c113`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c113`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c074`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c074`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c96e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c96e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c97c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c97c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c11b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c11b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c12e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c39c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c62e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c12e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c39c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c62e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c995`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c318`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c318`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c414`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c414`
- `WDSCORE!CurrentIP` at `0x18000bf9d`
- `WDSCORE!CurrentIP` at `0x18000c136`
- `WDSCORE!CurrentIP` at `0x18000c226`
- `WDSCORE!CurrentIP` at `0x18000c299`
- `WDSCORE!CurrentIP` at `0x18000c32b`
- `WDSCORE!CurrentIP` at `0x18000c3a4`
- `WDSCORE!CurrentIP` at `0x18000c45d`
- `WDSCORE!CurrentIP` at `0x18000c4cf`
- `WDSCORE!CurrentIP` at `0x18000c55f`
- `WDSCORE!CurrentIP` at `0x18000c5cd`
- `WDSCORE!CurrentIP` at `0x18000c636`
- `WDSCORE!CurrentIP` at `0x18000c695`
- `WDSCORE!CurrentIP` at `0x18000c714`
- `WDSCORE!CurrentIP` at `0x18000c78c`
- `WDSCORE!CurrentIP` at `0x18000c818`
- `WDSCORE!CurrentIP` at `0x18000c86b`
- `WDSCORE!CurrentIP` at `0x18000c8c5`
- `WDSCORE!CurrentIP` at `0x18000c915`
- `WDSCORE!CurrentIP` at `0x18000c98c`
- `WDSCORE!CurrentIP` at `0x18000bf9d`
- `WDSCORE!CurrentIP` at `0x18000c136`
- `WDSCORE!CurrentIP` at `0x18000c226`
- `WDSCORE!CurrentIP` at `0x18000c299`
- `WDSCORE!CurrentIP` at `0x18000c32b`
- `WDSCORE!CurrentIP` at `0x18000c3a4`
- `WDSCORE!CurrentIP` at `0x18000c45d`
- `WDSCORE!CurrentIP` at `0x18000c4cf`
- `WDSCORE!CurrentIP` at `0x18000c55f`
- `WDSCORE!CurrentIP` at `0x18000c5cd`
- `WDSCORE!CurrentIP` at `0x18000c636`
- `WDSCORE!CurrentIP` at `0x18000c695`
- `WDSCORE!CurrentIP` at `0x18000c714`
- `WDSCORE!CurrentIP` at `0x18000c78c`
- `WDSCORE!CurrentIP` at `0x18000c818`
- `WDSCORE!CurrentIP` at `0x18000c86b`
- `WDSCORE!CurrentIP` at `0x18000c8c5`
- `WDSCORE!CurrentIP` at `0x18000c915`
- `WDSCORE!CurrentIP` at `0x18000c98c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bff8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c197`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c270`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c2fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c37f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c3f8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c52a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c5ba`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c621`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c687`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c706`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c77e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c7f6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c95f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c9df`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bff8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c197`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c270`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c2fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c37f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c3f8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c52a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c5ba`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c621`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c687`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c706`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c77e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c7f6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c95f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c9df`

## string_xrefs

- `0x18000bfc7`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000c157`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000c2a9`: `%hs: Failed to initialize COM. Error: 0x%08X`
- `0x18000c40d`: `MDMRegistration.dll`
- `0x18000c4d8`: `Failed to get function pointer from MDMRegistration.dll. Error: 0x%08X`
- `0x18000c568`: `Failed to load MDMRegistration.dll. Error: 0x%08X`
- `0x18000c91b`: `DetectManagedStatus: Home edition detected, consider this is an unmanaged device`
- `0x18000c871`: `DetectManagedStatus: Consider this is a managed device based on detected management signals`
- `0x18000c81e`: `DetectManagedStatus: No management signal detected, consider this is an unmanaged device`
- `0x18000c8ce`: `DetectManagedStatus: Edition [%s] detected , consider this is a managed device by default`

## pseudocode

```c
__int64 __fastcall DetectManagedStatus(int *a1)
{
  signed int v1; // r14d
  LSTATUS v2; // eax
  signed int v3; // ebx
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  LSTATUS v7; // eax
  BYTE *v8; // r15
  DWORD v9; // ebx
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v12; // rax
  HANDLE v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  int v20; // r14d
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  int v27; // r14d
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  signed int v36; // eax
  DWORD v37; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  signed int v40; // eax
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // edi
  const wchar_t *v51; // rsi
  __int64 v52; // rbx
  const wchar_t *v53; // r8
  struct tagLOG_PARTIAL_MSG *v54; // rax
  DWORD v55; // edi
  __int64 v56; // rbx
  const wchar_t *v57; // r8
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  struct tagLOG_PARTIAL_MSG *v61; // rax
  DWORD v62; // edi
  __int64 v63; // rbx
  struct tagLOG_PARTIAL_MSG *v64; // rax
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  struct tagLOG_PARTIAL_MSG *v70; // rax
  DWORD v71; // edi
  __int64 v72; // rbx
  struct tagLOG_PARTIAL_MSG *v73; // rax
  HANDLE v74; // rax
  DWORD v75; // edi
  __int64 v76; // rbx
  DWORD v77; // eax
  struct tagLOG_PARTIAL_MSG *v78; // rax
  int v80; // [rsp+60h] [rbp-29h] BYREF
  BOOL v81; // [rsp+64h] [rbp-25h]
  int v82; // [rsp+68h] [rbp-21h]
  DWORD cbData; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD Type; // [rsp+70h] [rbp-19h] BYREF
  HMODULE hLibModule; // [rsp+78h] [rbp-11h] BYREF
  int *v86; // [rsp+80h] [rbp-9h]
  HKEY hKey; // [rsp+88h] [rbp-1h] BYREF
  int v88; // [rsp+90h] [rbp+7h] BYREF

  v86 = a1;
  LODWORD(hLibModule) = 0;
  v88 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 8u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 >= 0 )
  {
    LastError = GetLastError();
    v5 = CurrentIP();
    v6 = ConstructPartialMsgW(
           50331648,
           "DetectManagedStatus: WinRE environment detected, not expect to perfor managed status detection in WinRE");
    WdsSetupLogMessageW(
      v6,
      0,
      L"D",
      0,
      1283,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectManagedStatus",
      v5,
      LastError,
      0,
      0);
    return (unsigned int)-2147024846;
  }
  hKey = 0;
  cbData = 0;
  Type = 0;
  v1 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  v82 = 1;
  if ( !v7 && hKey )
  {
    v8 = 0;
    v9 = RegQueryValueExW(hKey, L"EditionID", 0, &Type, 0, &cbData);
    if ( !v9 )
    {
      if ( Type - 1 <= 1 )
      {
        v10 = cbData;
        ProcessHeap = GetProcessHeap();
        v12 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v10);
        v8 = v12;
        if ( !v12 )
        {
          v9 = GetLastError();
          goto LABEL_20;
        }
        *(_WORD *)v12 = 0;
        v9 = RegQueryValueExW(hKey, L"EditionID", 0, 0, v12, &cbData);
        if ( !v9 )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_20;
          v9 = 13;
        }
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v8);
        v8 = 0;
        goto LABEL_20;
      }
      v9 = 13;
    }
LABEL_20:
    RegCloseKey(hKey);
    SetLastError(v9);
    goto LABEL_22;
  }
  SetLastError(v7);
  v8 = 0;
LABEL_22:
  v14 = GetLastError();
  v15 = CurrentIP();
  v16 = ConstructPartialMsgW(0x4000000, "DetectManagedStatus: OS Edition: %s", (const char *)v8);
  WdsSetupLogMessageW(
    v16,
    0,
    L"D",
    0,
    1290,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"DetectManagedStatus",
    v15,
    v14,
    0,
    0);
  if ( v8 )
  {
    if ( _wcsicmp((const wchar_t *)v8, L"Core")
      && _wcsicmp((const wchar_t *)v8, L"CoreN")
      && _wcsicmp((const wchar_t *)v8, L"CoreCountrySpecific")
      && _wcsicmp((const wchar_t *)v8, L"CoreSingleLanguage") )
    {
      if ( _wcsicmp((const wchar_t *)v8, L"Professional") )
      {
        v82 = 1;
        v68 = GetLastError();
        v69 = CurrentIP();
        v70 = ConstructPartialMsgW(
                0x4000000,
                "DetectManagedStatus: Edition [%s] detected , consider this is a managed device by default",
                (const char *)v8);
        WdsSetupLogMessageW(
          v70,
          0,
          L"D",
          0,
          1350,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v69,
          v68,
          0,
          0);
      }
      else
      {
        v17 = GetLastError();
        v18 = CurrentIP();
        v19 = ConstructPartialMsgW(
                0x4000000,
                "DetectManagedStatus: Professional edition detected, need to further check managed status");
        WdsSetupLogMessageW(
          v19,
          0,
          L"D",
          0,
          1305,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v18,
          v17,
          0,
          0);
        v80 = 0;
        v20 = pInitializeCOM(&v80);
        if ( v20 >= 0 )
        {
          v81 = IsEnterprisePolicyConfigured() != 0;
        }
        else
        {
          v81 = 0;
          v21 = GetLastError();
          v22 = CurrentIP();
          v23 = ConstructPartialMsgW(0x2000000, "%hs: Failed to initialize COM. Error: 0x%08X", "DetectWUPolicy", v20);
          WdsSetupLogMessageW(
            v23,
            0,
            L"D",
            0,
            1071,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectWUPolicy",
            v22,
            v21,
            0,
            0);
        }
        if ( v80 )
          CoUninitialize();
        if ( v20 < 0 )
        {
          v24 = GetLastError();
          v25 = CurrentIP();
          v26 = ConstructPartialMsgW(0x2000000, "DetectManagedStatus: Failed to detect WU policy. Error: 0x%08x", v20);
          WdsSetupLogMessageW(
            v26,
            0,
            L"D",
            0,
            1309,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectManagedStatus",
            v25,
            v24,
            0,
            0);
          v81 = 0;
        }
        v27 = DetectDomainJoinStatus((int *)&hLibModule);
        if ( v27 >= 0 )
        {
          v80 = (int)hLibModule;
        }
        else
        {
          v28 = GetLastError();
          v29 = CurrentIP();
          v30 = ConstructPartialMsgW(
                  0x2000000,
                  "DetectManagedStatus: Failed to detect domain join status. Error: 0x%08x",
                  v27);
          WdsSetupLogMessageW(
            v30,
            0,
            L"D",
            0,
            1317,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectManagedStatus",
            v29,
            v28,
            0,
            0);
          v80 = 0;
        }
        LibraryW = LoadLibraryW(L"MDMRegistration.dll");
        hLibModule = LibraryW;
        if ( LibraryW )
        {
          ProcAddress = GetProcAddress(LibraryW, "IsDeviceRegisteredWithManagement");
          if ( ProcAddress )
          {
            v1 = ((__int64 (__fastcall *)(int *, _QWORD, _QWORD))ProcAddress)(&v88, 0, 0);
            if ( v1 < 0 )
            {
              v33 = GetLastError();
              v34 = CurrentIP();
              v35 = ConstructPartialMsgW(50331648, "Failed to detect MDM managed statu. Error: 0x%08x", v1);
              WdsSetupLogMessageW(
                v35,
                0,
                L"D",
                0,
                1223,
                L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                L"DetectMDMManagedStatus",
                v34,
                v33,
                0,
                0);
            }
          }
          else
          {
            v36 = GetLastError();
            v1 = v36;
            if ( v36 > 0 )
              v1 = (unsigned __int16)v36 | 0x80070000;
            v37 = GetLastError();
            v38 = CurrentIP();
            v39 = ConstructPartialMsgW(
                    0x2000000,
                    "Failed to get function pointer from MDMRegistration.dll. Error: 0x%08X",
                    v1);
            WdsSetupLogMessageW(
              v39,
              0,
              L"D",
              0,
              1230,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"DetectMDMManagedStatus",
              v38,
              v37,
              0,
              0);
          }
          FreeLibrary(hLibModule);
        }
        else
        {
          v40 = GetLastError();
          v1 = v40;
          if ( v40 > 0 )
            v1 = (unsigned __int16)v40 | 0x80070000;
          v41 = GetLastError();
          v42 = CurrentIP();
          v43 = ConstructPartialMsgW(0x2000000, "Failed to load MDMRegistration.dll. Error: 0x%08X", v1);
          WdsSetupLogMessageW(
            v43,
            0,
            L"D",
            0,
            1237,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectMDMManagedStatus",
            v42,
            v41,
            0,
            0);
        }
        if ( v1 < 0 )
        {
          v44 = GetLastError();
          v45 = CurrentIP();
          v46 = ConstructPartialMsgW(
                  0x2000000,
                  "DetectManagedStatus: Failed to detect MDM managed status. Error: 0x%08x",
                  v1);
          WdsSetupLogMessageW(
            v46,
            0,
            L"D",
            0,
            1325,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectManagedStatus",
            v45,
            v44,
            0,
            0);
          v1 = 0;
          v88 = 0;
        }
        v47 = GetLastError();
        v48 = CurrentIP();
        v49 = ConstructPartialMsgW(0x4000000, "DetectManagedStatus: Detected device management statuses:");
        WdsSetupLogMessageW(
          v49,
          0,
          L"D",
          0,
          1331,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v48,
          v47,
          0,
          0);
        v50 = GetLastError();
        v51 = L"true";
        v52 = CurrentIP();
        v53 = L"true";
        if ( !v81 )
          v53 = L"false";
        v54 = ConstructPartialMsgW(0x4000000, "DetectManagedStatus:    WU Managed: %s", v53);
        WdsSetupLogMessageW(
          v54,
          0,
          L"D",
          0,
          1332,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v52,
          v50,
          0,
          0);
        v55 = GetLastError();
        v56 = CurrentIP();
        v57 = L"true";
        if ( !v80 )
          v57 = L"false";
        v58 = ConstructPartialMsgW(0x4000000, "DetectManagedStatus:    Domain Joined: %s", v57);
        WdsSetupLogMessageW(
          v58,
          0,
          L"D",
          0,
          1333,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v56,
          v55,
          0,
          0);
        v59 = GetLastError();
        v60 = CurrentIP();
        if ( !v88 )
          v51 = L"false";
        v61 = ConstructPartialMsgW(0x4000000, "DetectManagedStatus:    MDM Enrolled: %s", v51);
        WdsSetupLogMessageW(
          v61,
          0,
          L"D",
          0,
          1334,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"DetectManagedStatus",
          v60,
          v59,
          0,
          0);
        if ( v81 || v80 || v88 )
        {
          v65 = GetLastError();
          v66 = CurrentIP();
          v67 = ConstructPartialMsgW(
                  0x4000000,
                  "DetectManagedStatus: Consider this is a managed device based on detected management signals");
          WdsSetupLogMessageW(
            v67,
            0,
            L"D",
            0,
            1339,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectManagedStatus",
            v66,
            v65,
            0,
            0);
        }
        else
        {
          v82 = 0;
          v62 = GetLastError();
          v63 = CurrentIP();
          v64 = ConstructPartialMsgW(
                  0x4000000,
                  "DetectManagedStatus: No management signal detected, consider this is an unmanaged device");
          WdsSetupLogMessageW(
            v64,
            0,
            L"D",
            0,
            1344,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"DetectManagedStatus",
            v63,
            v62,
            0,
            0);
        }
      }
    }
    else
    {
      v82 = 0;
      v71 = GetLastError();
      v72 = CurrentIP();
      v73 = ConstructPartialMsgW(
              0x4000000,
              "DetectManagedStatus: Home edition detected, consider this is an unmanaged device");
      WdsSetupLogMessageW(
        v73,
        0,
        L"D",
        0,
        1300,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"DetectManagedStatus",
        v72,
        v71,
        0,
        0);
    }
    *v86 = v82;
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v8);
  }
  else
  {
    v75 = GetLastError();
    v76 = CurrentIP();
    v77 = GetLastError();
    v78 = ConstructPartialMsgW(50331648, "DetectManagedStatus: Failed to detect OS edition, error: 0x%08X", v77);
    WdsSetupLogMessageW(
      v78,
      0,
      L"D",
      0,
      1356,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"DetectManagedStatus",
      v76,
      v75,
      0,
      0);
    *v86 = 1;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000bf00  push    rbp
0x18000bf02  push    rbx
0x18000bf03  push    rsi
0x18000bf04  push    rdi
0x18000bf05  push    r12
0x18000bf07  push    r13
0x18000bf09  push    r14
0x18000bf0b  push    r15
0x18000bf0d  lea     rbp, [rsp-1Fh]
0x18000bf12  sub     rsp, 0A8h
0x18000bf19  mov     rax, cs:__security_cookie
0x18000bf20  xor     rax, rsp
0x18000bf23  mov     [rbp+57h+var_48], rax
0x18000bf27  xor     esi, esi
0x18000bf29  mov     [rbp+57h+var_60], rcx
0x18000bf2d  mov     dword ptr [rbp+57h+hLibModule], esi
0x18000bf30  mov     [rbp+57h+var_50], esi
0x18000bf33  test    rcx, rcx
0x18000bf36  jnz     short loc_18000BF43
0x18000bf38  mov     r14d, 80070057h
0x18000bf3e  jmp     loc_18000C9EF
0x18000bf43  lea     rax, [rbp+57h+hKey]
0x18000bf47  mov     [rbp+57h+hKey], rsi
0x18000bf4b  mov     r12d, 8
0x18000bf51  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000bf56  mov     rdi, 0FFFFFFFF80000002h
0x18000bf5d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18000bf64  mov     r9d, r12d; samDesired
0x18000bf67  mov     rcx, rdi; hKey
0x18000bf6a  xor     r8d, r8d; ulOptions
0x18000bf6d  call    cs:__imp_RegOpenKeyExW
0x18000bf73  mov     ebx, eax
0x18000bf75  test    eax, eax
0x18000bf77  jle     short loc_18000BF82
0x18000bf79  movzx   ebx, ax
0x18000bf7c  or      ebx, 80070000h
0x18000bf82  mov     rcx, [rbp+57h+hKey]; hKey
0x18000bf86  test    rcx, rcx
0x18000bf89  jz      short loc_18000BF91
0x18000bf8b  call    cs:__imp_RegCloseKey
0x18000bf91  test    ebx, ebx
0x18000bf93  js      short loc_18000C009
0x18000bf95  call    cs:__imp_GetLastError
0x18000bf9b  mov     edi, eax
0x18000bf9d  call    cs:__imp_CurrentIP
0x18000bfa3  lea     rdx, aDetectmanageds_2; "DetectManagedStatus: WinRE environment "...
0x18000bfaa  mov     ecx, 3000000h; unsigned int
0x18000bfaf  mov     rbx, rax
0x18000bfb2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bfb7  mov     [rsp+0E0h+var_90], esi
0x18000bfbb  lea     rcx, aDetectmanageds_14; "DetectManagedStatus"
0x18000bfc2  mov     [rsp+0E0h+var_98], rsi
0x18000bfc7  lea     r13, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000bfce  mov     [rsp+0E0h+var_A0], edi
0x18000bfd2  lea     r8, aD; "D"
0x18000bfd9  mov     [rsp+0E0h+var_A8], rbx
0x18000bfde  xor     r9d, r9d
0x18000bfe1  mov     [rsp+0E0h+var_B0], rcx
0x18000bfe6  xor     edx, edx
0x18000bfe8  mov     [rsp+0E0h+lpcbData], r13
0x18000bfed  mov     rcx, rax
0x18000bff0  mov     dword ptr [rsp+0E0h+phkResult], 503h
0x18000bff8  call    cs:__imp_WdsSetupLogMessageW
0x18000bffe  mov     r14d, 80070032h
0x18000c004  jmp     loc_18000C9EF
0x18000c009  lea     rax, [rbp+57h+hKey]
0x18000c00d  mov     [rbp+57h+hKey], rsi
0x18000c011  mov     r9d, 20019h; samDesired
0x18000c017  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000c01c  xor     r8d, r8d; ulOptions
0x18000c01f  mov     [rbp+57h+cbData], esi
0x18000c022  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000c029  mov     [rbp+57h+Type], esi
0x18000c02c  mov     rcx, rdi; hKey
0x18000c02f  mov     r14d, esi
0x18000c032  call    cs:__imp_RegOpenKeyExW
0x18000c038  mov     edi, 1
0x18000c03d  mov     [rbp+57h+var_78], edi
0x18000c040  test    eax, eax
0x18000c042  jnz     loc_18000C123
0x18000c048  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c04c  test    rcx, rcx
0x18000c04f  jz      loc_18000C123
0x18000c055  lea     rax, [rbp+57h+cbData]
0x18000c059  xor     r8d, r8d; lpReserved
0x18000c05c  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18000c061  lea     r9, [rbp+57h+Type]; lpType
0x18000c065  lea     rdx, ValueName; "EditionID"
0x18000c06c  mov     [rsp+0E0h+phkResult], rsi; lpData
0x18000c071  mov     r15, rsi
0x18000c074  call    cs:__imp_RegQueryValueExW
0x18000c07a  mov     ebx, eax
0x18000c07c  test    eax, eax
0x18000c07e  jnz     loc_18000C10F
0x18000c084  mov     eax, [rbp+57h+Type]
0x18000c087  dec     eax
0x18000c089  cmp     eax, edi
0x18000c08b  jbe     short loc_18000C092
0x18000c08d  lea     ebx, [rdi+0Ch]
0x18000c090  jmp     short loc_18000C10F
0x18000c092  mov     ebx, [rbp+57h+cbData]
0x18000c095  call    cs:__imp_GetProcessHeap
0x18000c09b  mov     r8d, ebx; dwBytes
0x18000c09e  mov     edx, r12d; dwFlags
0x18000c0a1  mov     rcx, rax; hHeap
0x18000c0a4  call    cs:__imp_HeapAlloc
0x18000c0aa  mov     r15, rax
0x18000c0ad  test    rax, rax
0x18000c0b0  jz      short loc_18000C107
0x18000c0b2  mov     [rax], si
0x18000c0b5  lea     rdx, ValueName; "EditionID"
0x18000c0bc  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c0c0  lea     rax, [rbp+57h+cbData]
0x18000c0c4  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18000c0c9  xor     r9d, r9d; lpType
0x18000c0cc  xor     r8d, r8d; lpReserved
0x18000c0cf  mov     [rsp+0E0h+phkResult], r15; lpData
0x18000c0d4  call    cs:__imp_RegQueryValueExW
0x18000c0da  mov     ebx, eax
0x18000c0dc  test    eax, eax
0x18000c0de  jnz     short loc_18000C0EE
0x18000c0e0  mov     eax, [rbp+57h+Type]
0x18000c0e3  dec     eax
0x18000c0e5  cmp     eax, edi
0x18000c0e7  jbe     short loc_18000C10F
0x18000c0e9  mov     ebx, 0Dh
0x18000c0ee  call    cs:__imp_GetProcessHeap
0x18000c0f4  mov     r8, r15; lpMem
0x18000c0f7  xor     edx, edx; dwFlags
0x18000c0f9  mov     rcx, rax; hHeap
0x18000c0fc  call    cs:__imp_HeapFree
0x18000c102  mov     r15, rsi
0x18000c105  jmp     short loc_18000C10F
0x18000c107  call    cs:__imp_GetLastError
0x18000c10d  mov     ebx, eax
0x18000c10f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c113  call    cs:__imp_RegCloseKey
0x18000c119  mov     ecx, ebx; dwErrCode
0x18000c11b  call    cs:__imp_SetLastError
0x18000c121  jmp     short loc_18000C12E
0x18000c123  mov     ecx, eax; dwErrCode
0x18000c125  call    cs:__imp_SetLastError
0x18000c12b  mov     r15, rsi
0x18000c12e  call    cs:__imp_GetLastError
0x18000c134  mov     edi, eax
0x18000c136  call    cs:__imp_CurrentIP
0x18000c13c  mov     r8, r15
0x18000c13f  lea     rdx, aDetectmanageds_0; "DetectManagedStatus: OS Edition: %s"
0x18000c146  mov     ecx, 4000000h; unsigned int
0x18000c14b  mov     rbx, rax
0x18000c14e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c153  mov     [rsp+0E0h+var_90], esi
0x18000c157  lea     r13, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000c15e  mov     [rsp+0E0h+var_98], rsi
0x18000c163  lea     r12, aD; "D"
0x18000c16a  mov     [rsp+0E0h+var_A0], edi
0x18000c16e  lea     rsi, aDetectmanageds_14; "DetectManagedStatus"
0x18000c175  mov     [rsp+0E0h+var_A8], rbx
0x18000c17a  xor     r9d, r9d
0x18000c17d  mov     [rsp+0E0h+var_B0], rsi
0x18000c182  mov     r8, r12
0x18000c185  mov     [rsp+0E0h+lpcbData], r13
0x18000c18a  xor     edx, edx
0x18000c18c  mov     rcx, rax
0x18000c18f  mov     dword ptr [rsp+0E0h+phkResult], 50Ah
0x18000c197  call    cs:__imp_WdsSetupLogMessageW
0x18000c19d  test    r15, r15
0x18000c1a0  jz      loc_18000C984
0x18000c1a6  lea     rdx, aCore; "Core"
0x18000c1ad  mov     rcx, r15; String1
0x18000c1b0  call    cs:__imp__wcsicmp
0x18000c1b6  test    eax, eax
0x18000c1b8  jz      loc_18000C909
0x18000c1be  lea     rdx, aCoren; "CoreN"
0x18000c1c5  mov     rcx, r15; String1
0x18000c1c8  call    cs:__imp__wcsicmp
0x18000c1ce  test    eax, eax
0x18000c1d0  jz      loc_18000C909
0x18000c1d6  lea     rdx, aCorecountryspe; "CoreCountrySpecific"
0x18000c1dd  mov     rcx, r15; String1
0x18000c1e0  call    cs:__imp__wcsicmp
0x18000c1e6  test    eax, eax
0x18000c1e8  jz      loc_18000C909
0x18000c1ee  lea     rdx, aCoresinglelang; "CoreSingleLanguage"
0x18000c1f5  mov     rcx, r15; String1
0x18000c1f8  call    cs:__imp__wcsicmp
0x18000c1fe  test    eax, eax
0x18000c200  jz      loc_18000C909
0x18000c206  lea     rdx, aProfessional; "Professional"
0x18000c20d  mov     rcx, r15; String1
0x18000c210  call    cs:__imp__wcsicmp
0x18000c216  test    eax, eax
0x18000c218  jnz     loc_18000C8B6
0x18000c21e  call    cs:__imp_GetLastError
0x18000c224  mov     edi, eax
0x18000c226  call    cs:__imp_CurrentIP
0x18000c22c  lea     rdx, aDetectmanageds_8; "DetectManagedStatus: Professional editi"...
0x18000c233  mov     ecx, 4000000h; unsigned int
0x18000c238  mov     rbx, rax
0x18000c23b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c240  mov     [rsp+0E0h+var_90], r14d
0x18000c245  xor     r9d, r9d
0x18000c248  mov     [rsp+0E0h+var_98], r14
0x18000c24d  mov     r8, r12
0x18000c250  mov     [rsp+0E0h+var_A0], edi
0x18000c254  xor     edx, edx
0x18000c256  mov     [rsp+0E0h+var_A8], rbx
0x18000c25b  mov     rcx, rax
0x18000c25e  mov     [rsp+0E0h+var_B0], rsi
0x18000c263  mov     [rsp+0E0h+lpcbData], r13
0x18000c268  mov     dword ptr [rsp+0E0h+phkResult], 519h
0x18000c270  call    cs:__imp_WdsSetupLogMessageW
0x18000c276  lea     rcx, [rbp+57h+var_80]; int *
0x18000c27a  mov     [rbp+57h+var_80], r14d
0x18000c27e  call    ?pInitializeCOM@@YAJAEAH@Z; pInitializeCOM(int &)
0x18000c283  mov     r14d, eax
0x18000c286  test    eax, eax
0x18000c288  jns     short loc_18000C303
0x18000c28a  mov     [rbp+57h+var_7C], 0
0x18000c291  call    cs:__imp_GetLastError
0x18000c297  mov     edi, eax
0x18000c299  call    cs:__imp_CurrentIP
0x18000c29f  mov     r9d, r14d
0x18000c2a2  lea     r8, aDetectwupolicy_0; "DetectWUPolicy"
0x18000c2a9  lea     rdx, aHsFailedToInit; "%hs: Failed to initialize COM. Error: 0"...
0x18000c2b0  mov     ecx, 2000000h; unsigned int
0x18000c2b5  mov     rbx, rax
0x18000c2b8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c2bd  mov     [rsp+0E0h+var_90], 0
0x18000c2c5  lea     rcx, aDetectwupolicy; "DetectWUPolicy"
0x18000c2cc  mov     [rsp+0E0h+var_98], 0
0x18000c2d5  xor     r9d, r9d
0x18000c2d8  mov     [rsp+0E0h+var_A0], edi
0x18000c2dc  mov     r8, r12
0x18000c2df  mov     [rsp+0E0h+var_A8], rbx
0x18000c2e4  xor     edx, edx
0x18000c2e6  mov     [rsp+0E0h+var_B0], rcx
0x18000c2eb  mov     rcx, rax
0x18000c2ee  mov     [rsp+0E0h+lpcbData], r13
0x18000c2f3  mov     dword ptr [rsp+0E0h+phkResult], 42Fh
0x18000c2fb  call    cs:__imp_WdsSetupLogMessageW
0x18000c301  jmp     short loc_18000C312
0x18000c303  call    IsEnterprisePolicyConfigured
0x18000c308  xor     ebx, ebx
0x18000c30a  test    eax, eax
0x18000c30c  setnz   bl
0x18000c30f  mov     [rbp+57h+var_7C], ebx
0x18000c312  cmp     [rbp+57h+var_80], 0
0x18000c316  jz      short loc_18000C31E
0x18000c318  call    cs:__imp_CoUninitialize
0x18000c31e  test    r14d, r14d
0x18000c321  jns     short loc_18000C38C
0x18000c323  call    cs:__imp_GetLastError
0x18000c329  mov     edi, eax
0x18000c32b  call    cs:__imp_CurrentIP
0x18000c331  mov     r8d, r14d
0x18000c334  lea     rdx, aDetectmanageds_10; "DetectManagedStatus: Failed to detect W"...
0x18000c33b  mov     ecx, 2000000h; unsigned int
0x18000c340  mov     rbx, rax
0x18000c343  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c348  mov     [rsp+0E0h+var_90], 0
0x18000c350  xor     r9d, r9d
0x18000c353  mov     [rsp+0E0h+var_98], 0
0x18000c35c  mov     r8, r12
0x18000c35f  mov     [rsp+0E0h+var_A0], edi
0x18000c363  xor     edx, edx
0x18000c365  mov     [rsp+0E0h+var_A8], rbx
0x18000c36a  mov     rcx, rax
0x18000c36d  mov     [rsp+0E0h+var_B0], rsi
0x18000c372  mov     [rsp+0E0h+lpcbData], r13
0x18000c377  mov     dword ptr [rsp+0E0h+phkResult], 51Dh
0x18000c37f  call    cs:__imp_WdsSetupLogMessageW
0x18000c385  mov     [rbp+57h+var_7C], 0
0x18000c38c  lea     rcx, [rbp+57h+hLibModule]; int *
0x18000c390  call    ?DetectDomainJoinStatus@@YAJPEAH@Z; DetectDomainJoinStatus(int *)
0x18000c395  mov     r14d, eax
0x18000c398  test    eax, eax
0x18000c39a  jns     short loc_18000C407
0x18000c39c  call    cs:__imp_GetLastError
0x18000c3a2  mov     edi, eax
0x18000c3a4  call    cs:__imp_CurrentIP
0x18000c3aa  mov     r8d, r14d
0x18000c3ad  lea     rdx, aDetectmanageds_6; "DetectManagedStatus: Failed to detect d"...
0x18000c3b4  mov     ecx, 2000000h; unsigned int
0x18000c3b9  mov     rbx, rax
0x18000c3bc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c3c1  mov     [rsp+0E0h+var_90], 0
0x18000c3c9  xor     r9d, r9d
0x18000c3cc  mov     [rsp+0E0h+var_98], 0
0x18000c3d5  mov     r8, r12
0x18000c3d8  mov     [rsp+0E0h+var_A0], edi
0x18000c3dc  xor     edx, edx
0x18000c3de  mov     [rsp+0E0h+var_A8], rbx
0x18000c3e3  mov     rcx, rax
0x18000c3e6  mov     [rsp+0E0h+var_B0], rsi
0x18000c3eb  mov     [rsp+0E0h+lpcbData], r13
0x18000c3f0  mov     dword ptr [rsp+0E0h+phkResult], 525h
0x18000c3f8  call    cs:__imp_WdsSetupLogMessageW
0x18000c3fe  mov     [rbp+57h+var_80], 0
0x18000c405  jmp     short loc_18000C40D
  ... truncated ...
```
