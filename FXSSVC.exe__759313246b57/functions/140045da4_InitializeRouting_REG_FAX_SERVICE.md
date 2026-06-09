# InitializeRouting(_REG_FAX_SERVICE *)

- ea: `0x140045da4`
- end: `0x140046eb4`
- name: `?InitializeRouting@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `4368`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140049f40`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140004f64`
- `0x1400259bc`
- `0x140045da4`
- `0x14004716c`
- `0x140047920`
- `0x1400698ec`
- `0x14006998c`
- `0x1400699d0`
- `0x140069f50`
- `0x14006af2c`
- `0x14006b000`
- `0x14007566c`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140046d83`
- `KERNEL32!FreeLibrary` at `0x140046d83`
- `KERNEL32!GetLastError` at `0x140046303`
- `KERNEL32!GetLastError` at `0x140046528`
- `KERNEL32!GetLastError` at `0x1400466d2`
- `KERNEL32!GetLastError` at `0x14004697e`
- `KERNEL32!GetLastError` at `0x1400469d5`
- `KERNEL32!GetLastError` at `0x140046a7f`
- `KERNEL32!GetLastError` at `0x140046ae5`
- `KERNEL32!GetLastError` at `0x140046b2c`
- `KERNEL32!GetLastError` at `0x140046bca`
- `KERNEL32!GetLastError` at `0x140046c2a`
- `KERNEL32!GetLastError` at `0x140046303`
- `KERNEL32!GetLastError` at `0x140046528`
- `KERNEL32!GetLastError` at `0x1400466d2`
- `KERNEL32!GetLastError` at `0x14004697e`
- `KERNEL32!GetLastError` at `0x1400469d5`
- `KERNEL32!GetLastError` at `0x140046a7f`
- `KERNEL32!GetLastError` at `0x140046ae5`
- `KERNEL32!GetLastError` at `0x140046b2c`
- `KERNEL32!GetLastError` at `0x140046bca`
- `KERNEL32!GetLastError` at `0x140046c2a`
- `KERNEL32!LoadLibraryW` at `0x1400462ed`
- `KERNEL32!LoadLibraryW` at `0x1400462ed`
- `KERNEL32!GetProcessHeap` at `0x1400464f2`
- `KERNEL32!GetProcessHeap` at `0x1400464f2`
- `KERNEL32!HeapCreate` at `0x14004650d`
- `KERNEL32!HeapCreate` at `0x14004650d`
- `KERNEL32!GetProcAddress` at `0x1400463c9`
- `KERNEL32!GetProcAddress` at `0x1400463e4`
- `KERNEL32!GetProcAddress` at `0x140046403`
- `KERNEL32!GetProcAddress` at `0x140046422`
- `KERNEL32!GetProcAddress` at `0x140046441`
- `KERNEL32!GetProcAddress` at `0x1400464a6`
- `KERNEL32!GetProcAddress` at `0x1400468b8`
- `KERNEL32!GetProcAddress` at `0x1400463c9`
- `KERNEL32!GetProcAddress` at `0x1400463e4`
- `KERNEL32!GetProcAddress` at `0x140046403`
- `KERNEL32!GetProcAddress` at `0x140046422`
- `KERNEL32!GetProcAddress` at `0x140046441`
- `KERNEL32!GetProcAddress` at `0x1400464a6`
- `KERNEL32!GetProcAddress` at `0x1400468b8`
- `KERNEL32!HeapDestroy` at `0x140046da7`
- `KERNEL32!HeapDestroy` at `0x140046da7`
- `msvcrt!_wcsicmp` at `0x140046256`
- `msvcrt!_wcsicmp` at `0x140046275`
- `msvcrt!_wcsicmp` at `0x14004674a`
- `msvcrt!_wcsicmp` at `0x140046256`
- `msvcrt!_wcsicmp` at `0x140046275`
- `msvcrt!_wcsicmp` at `0x14004674a`
- `msvcrt!_wsplitpath_s` at `0x14004619a`
- `msvcrt!_wsplitpath_s` at `0x14004619a`
- `ole32!IIDFromString` at `0x140046880`
- `ole32!IIDFromString` at `0x140046880`

## string_xrefs

- `0x14004649a`: `FaxExtInitializeConfig`

## pseudocode

```c
__int64 __fastcall InitializeRouting(struct _REG_FAX_SERVICE *a1)
{
  struct _REG_FAX_SERVICE *v1; // r14
  unsigned int v2; // ebx
  _DWORD *v3; // rax
  __int64 v4; // rsi
  __int64 *v5; // r14
  unsigned int v6; // r12d
  __int64 v7; // r15
  const WCHAR *v8; // r8
  WCHAR *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  WCHAR v12; // r9
  signed int v13; // ebx
  WCHAR *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // r8
  WCHAR v19; // r9
  WCHAR *v20; // rax
  const WCHAR *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  WCHAR *v24; // r8
  WCHAR v25; // r9
  WCHAR *v26; // rax
  CMapDeviceId *v27; // rcx
  _DWORD *v28; // r12
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  int FileVersion; // eax
  unsigned int (__fastcall **v32)(_QWORD, int *); // rbx
  FARPROC ProcAddress; // rax
  FARPROC v34; // rax
  HANDLE ProcessHeap; // rax
  DWORD v36; // eax
  __int64 (__fastcall *v37)(DWORD (__stdcall *)(DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE *, LPDWORD), DWORD (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE, DWORD), HANDLE (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, PFAX_EXT_CONFIG_CHANGE), DWORD (__stdcall *)(HANDLE), void (__stdcall *)(void *)); // rax
  int *v38; // rdx
  DWORD v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r13
  __int64 v42; // rax
  __int64 v43; // r12
  GUID *v44; // rax
  GUID *v45; // r15
  __int64 v46; // rcx
  unsigned __int16 *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  unsigned __int16 *v50; // rax
  __int64 v51; // rax
  LPVOID *Data4; // rbx
  __int64 v53; // rcx
  unsigned __int16 *v54; // rax
  __int64 v55; // rax
  DWORD v56; // r13d
  const CHAR *v57; // rax
  CHAR *v58; // r13
  FARPROC v59; // rax
  GUID **v60; // rax
  _QWORD *v61; // r8
  __int64 v62; // r9
  unsigned int v63; // r10d
  _QWORD *v64; // rdx
  _QWORD *v65; // rcx
  int v66; // edx
  int v67; // r8d
  CHAR *v68; // r12
  CMapDeviceId *v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // r9
  DWORD v72; // eax
  int v73; // eax
  unsigned __int16 *v74; // r8
  HMODULE v75; // rcx
  void *v76; // rcx
  LPVOID *v77; // r14
  LPVOID *v78; // r15
  LPVOID *v79; // rbx
  __int64 *v80; // rax
  unsigned int v82; // [rsp+50h] [rbp-5B8h]
  const CHAR *lpMem; // [rsp+58h] [rbp-5B0h]
  HMODULE hModule; // [rsp+68h] [rbp-5A0h]
  __int64 v85; // [rsp+70h] [rbp-598h]
  __int64 v86; // [rsp+78h] [rbp-590h]
  int v87; // [rsp+78h] [rbp-590h]
  unsigned int v88; // [rsp+80h] [rbp-588h]
  _QWORD *v90; // [rsp+A8h] [rbp-560h]
  _DWORD *v91; // [rsp+B0h] [rbp-558h]
  _QWORD *v93; // [rsp+E0h] [rbp-528h]
  __int128 v94; // [rsp+E8h] [rbp-520h] BYREF
  __int128 v95; // [rsp+F8h] [rbp-510h]
  __int128 v96; // [rsp+108h] [rbp-500h]
  int v97; // [rsp+120h] [rbp-4E8h] BYREF
  int (*v98)(unsigned int, const unsigned __int16 *, struct _GUID *); // [rsp+128h] [rbp-4E0h]
  int (*v99)(unsigned int, const unsigned __int16 *); // [rsp+130h] [rbp-4D8h]
  int (*v100)(unsigned int, unsigned int, unsigned __int16 *, unsigned int *); // [rsp+138h] [rbp-4D0h]
  __int64 (__fastcall *v101)(unsigned int, struct _GUID *, int (*)(unsigned int, struct _GUID *, struct _GUID *, const unsigned __int16 *, void *), void *); // [rsp+140h] [rbp-4C8h]
  int (*v102)(unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int); // [rsp+148h] [rbp-4C0h]
  __int64 (__fastcall *v103)(); // [rsp+150h] [rbp-4B8h]
  __int64 (__fastcall *v104)(LPVOID); // [rsp+158h] [rbp-4B0h]
  __int64 v105; // [rsp+160h] [rbp-4A8h]
  int v106; // [rsp+170h] [rbp-498h]
  unsigned __int16 v107[14]; // [rsp+174h] [rbp-494h] BYREF
  int v108; // [rsp+190h] [rbp-478h]
  unsigned __int16 v109[14]; // [rsp+194h] [rbp-474h] BYREF
  int v110; // [rsp+1B0h] [rbp-458h]
  unsigned __int16 v111[14]; // [rsp+1B4h] [rbp-454h] BYREF
  wchar_t String1[256]; // [rsp+1D0h] [rbp-438h] BYREF
  wchar_t Ext[256]; // [rsp+3D0h] [rbp-238h] BYREF

  v1 = a1;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  memset_0(&v97, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  LODWORD(v94) = 48;
  *((_QWORD *)&v94 + 1) = FaxRouteAddFile;
  *(_QWORD *)&v95 = FaxRouteDeleteFile;
  *((_QWORD *)&v95 + 1) = FaxRouteGetFile;
  *(_QWORD *)&v96 = FaxRouteEnumFiles;
  *((_QWORD *)&v96 + 1) = FaxRouteModifyRoutingData;
  v97 = 72;
  v98 = FaxRouteAddFile;
  v99 = FaxRouteDeleteFile;
  v100 = FaxRouteGetFile;
  v101 = FaxRouteEnumFiles;
  v102 = FaxRouteModifyRoutingData;
  v103 = GetReceiptsConfiguration;
  v104 = FreeReceiptsConfiguration;
  v105 = *((_QWORD *)g_pFaxConfig + 12);
  v2 = 0;
  while ( 1 )
  {
    v88 = v2;
    if ( v2 >= *((_DWORD *)v1 + 6) )
      break;
    memset_0(String1, 0, sizeof(String1));
    memset_0(Ext, 0, sizeof(Ext));
    v3 = (_DWORD *)pMemAlloc(0x6A0u);
    v91 = v3;
    v4 = (__int64)v3;
    if ( !v3 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*((_QWORD *)v1 + 2) + 40LL * v2 + 8));
      }
      v5 = (__int64 *)((char *)a1 + 16);
      v6 = v2;
      goto LABEL_182;
    }
    v6 = v2;
    v82 = v2;
    memset_0(v3, 0, 0x690u);
    v90 = (_QWORD *)(v4 + 1680);
    v93 = (_QWORD *)(v4 + 1680);
    *(_QWORD *)(v4 + 1688) = v4 + 1680;
    *(_QWORD *)(v4 + 1680) = v4 + 1680;
    v7 = 40LL * v2;
    v85 = v7;
    v5 = (__int64 *)((char *)v1 + 16);
    v8 = &Class;
    if ( *(_QWORD *)(v7 + *v5) )
      v8 = *(const WCHAR **)(v7 + *v5);
    v9 = (WCHAR *)(v4 + 52);
    v86 = v4 + 52;
    v10 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v10 )
        break;
      v12 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v9++ = v12;
      --v10;
      --v11;
    }
    while ( v11 );
    v13 = v11 == 0 ? 0x8007007A : 0;
    v14 = v9 - 1;
    if ( v11 )
      v14 = v9;
    *v14 = 0;
    if ( !v11 )
      goto LABEL_47;
    v15 = &Class;
    if ( *(_QWORD *)(*v5 + v7 + 8) )
      v15 = *(const WCHAR **)(*v5 + v7 + 8);
    v16 = 2147483646;
    v17 = 260;
    v18 = (WCHAR *)(v4 + 572);
    do
    {
      if ( !v16 )
        break;
      v19 = *v15;
      if ( !*v15 )
        break;
      ++v15;
      *v18++ = v19;
      --v16;
      --v17;
    }
    while ( v17 );
    v13 = v17 == 0 ? 0x8007007A : 0;
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    *v20 = 0;
    if ( v17 )
    {
      v21 = &Class;
      if ( *(_QWORD *)(*v5 + v7 + 16) )
        v21 = *(const WCHAR **)(*v5 + v7 + 16);
      v22 = 2147483646;
      v23 = 260;
      v24 = (WCHAR *)(v4 + 1092);
      do
      {
        if ( !v22 )
          break;
        v25 = *v21;
        if ( !*v21 )
          break;
        ++v21;
        *v24++ = v25;
        --v22;
        --v23;
      }
      while ( v23 );
      v26 = v24 - 1;
      if ( v23 )
        v26 = v24;
      *v26 = 0;
      v13 = v23 == 0 ? 0x8007007A : 0;
      if ( v23 && _wsplitpath_s((const wchar_t *)(v4 + 572), 0, 0, 0, 0, String1, 0x100u, Ext, 0x100u) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
          v27 = WPP_GLOBAL_Control;
        }
        v13 = -2147467259;
      }
      else
      {
        v27 = WPP_GLOBAL_Control;
      }
    }
    else
    {
LABEL_47:
      v27 = WPP_GLOBAL_Control;
    }
    if ( v13 < 0 )
    {
      if ( v27 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 && *((_BYTE *)v27 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v27 + 2), 15, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, (unsigned int)v13);
      *(_DWORD *)(v4 + 24) = 6;
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        v13 = (unsigned __int16)v13;
      goto LABEL_181;
    }
    if ( !_wcsicmp(String1, L"FXSROUTE") && !_wcsicmp(Ext, L".DLL") )
      *(_DWORD *)(v4 + 1624) = 1;
    v28 = (_DWORD *)(v4 + 1624);
    if ( *(_DWORD *)(v4 + 1624) && !v105 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7 + 8));
      }
LABEL_64:
      v6 = v82;
      goto LABEL_182;
    }
    LibraryW = LoadLibraryW(*(LPCWSTR *)(*v5 + v7 + 8));
    hModule = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7 + 8),
          LastError);
      }
      *(_DWORD *)(v4 + 24) = 4;
      goto LABEL_180;
    }
    *(_QWORD *)(v4 + 16) = LibraryW;
    *(_DWORD *)(v4 + 32) = 20;
    FileVersion = GetFileVersion(*(LPCWSTR *)(*v5 + v7 + 8));
    if ( FileVersion
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
        *(_QWORD *)(*v5 + v7 + 8),
        FileVersion);
    }
    v32 = (unsigned int (__fastcall **)(_QWORD, int *))(v4 + 1632);
    *(_QWORD *)(v4 + 1632) = GetProcAddress(hModule, "FaxRouteInitialize");
    *(_QWORD *)(v4 + 1640) = GetProcAddress(hModule, "FaxRouteGetRoutingInfo");
    *(_QWORD *)(v4 + 1648) = GetProcAddress(hModule, "FaxRouteSetRoutingInfo");
    *(_QWORD *)(v4 + 1656) = GetProcAddress(hModule, "FaxRouteDeviceEnable");
    ProcAddress = GetProcAddress(hModule, "FaxRouteDeviceChangeNotification");
    *(_QWORD *)(v4 + 1664) = ProcAddress;
    if ( !*(_QWORD *)(v4 + 1632)
      || !*(_QWORD *)(v4 + 1640)
      || !*(_QWORD *)(v4 + 1648)
      || !ProcAddress
      || !*(_QWORD *)(v4 + 1656) )
    {
      v72 = GetLastError();
      v13 = v72;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
          *(_QWORD *)(*v5 + v7),
          v72);
      }
      *(_DWORD *)(v4 + 24) = 5;
      goto LABEL_180;
    }
    v34 = GetProcAddress(hModule, "FaxExtInitializeConfig");
    *(_QWORD *)(v4 + 1672) = v34;
    if ( !v34
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v86);
    }
    if ( *v28 )
      ProcessHeap = GetProcessHeap();
    else
      ProcessHeap = HeapCreate(0, 0x19000u, 0x200000u);
    *(_QWORD *)(v4 + 1616) = ProcessHeap;
    if ( !ProcessHeap )
    {
      v36 = GetLastError();
      v13 = v36;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v36);
      }
      goto LABEL_94;
    }
    v37 = *(__int64 (__fastcall **)(DWORD (__stdcall *)(DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE *, LPDWORD), DWORD (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, LPBYTE, DWORD), HANDLE (__stdcall *)(HINSTANCE, DWORD, FAX_ENUM_DEVICE_ID_SOURCE, LPCWSTR, PFAX_EXT_CONFIG_CHANGE), DWORD (__stdcall *)(HANDLE), void (__stdcall *)(void *)))(v4 + 1672);
    if ( v37 )
    {
      v13 = v37(FaxExtGetData, FaxExtSetData, FaxExtRegisterForEvents, FaxExtUnregisterForEvents, MIDL_user_free);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
            v13,
            v86);
        }
        *(_DWORD *)(v4 + 24) = 6;
        goto LABEL_180;
      }
      v32 = (unsigned int (__fastcall **)(_QWORD, int *))(v4 + 1632);
    }
    v38 = &v97;
    if ( !*v28 )
      v38 = (int *)&v94;
    v6 = v82;
    if ( !(*v32)(*(_QWORD *)(v4 + 1616), v38) )
    {
      v39 = GetLastError();
      v13 = v39;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v39);
      }
      *(_DWORD *)(v4 + 24) = 6;
      goto LABEL_181;
    }
    v40 = *v5;
    v41 = v7;
    if ( *(_DWORD *)(*v5 + v7 + 24) )
    {
      v42 = 0;
      v87 = 0;
      do
      {
        v43 = 5 * v42;
        if ( _wcsicmp(
               *(const wchar_t **)(*(_QWORD *)(v40 + v41 + 32) + 40 * v42 + 16),
               L"{6bbf7bfe-9af2-11d0-abf7-00c04fd91a4e}")
          || (unsigned int)IsServerSku() )
        {
          v44 = (GUID *)pMemAlloc(0x60u);
          v45 = v44;
          if ( !v44 )
          {
            v13 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 8));
            }
LABEL_94:
            *(_DWORD *)(v4 + 24) = 1;
LABEL_180:
            v6 = v82;
LABEL_181:
            *(_DWORD *)(v4 + 28) = v13;
LABEL_182:
            if ( v4 )
            {
              v106 = *(_DWORD *)(v4 + 28);
              v107[0] = 0;
              StringCchPrintfW(v107, 0xCu, L"%ld");
            }
            else
            {
              v108 = 14;
              v109[0] = 0;
              StringCchPrintfW(v109, 0xCu, L"%ld", 14);
            }
            if ( v4 )
            {
              v110 = *(_DWORD *)(v4 + 24);
              v111[0] = 0;
              v73 = StringCchPrintfW(v111, 0xCu, L"%ld");
              v74 = v111;
              if ( v73 < 0 )
                v74 = 0;
            }
            else
            {
              v74 = 0;
            }
            FaxLog(1, 1, 4, 3221257508LL, *(_QWORD *)(*v5 + 40LL * v6), *(_QWORD *)(*v5 + 40LL * v6 + 8), v74);
            if ( v4 )
            {
              v75 = *(HMODULE *)(v4 + 16);
              if ( v75 )
              {
                FreeLibrary(v75);
                *(_QWORD *)(v4 + 16) = 0;
              }
              v76 = *(void **)(v4 + 1616);
              if ( v76 && !*(_DWORD *)(v4 + 1624) )
              {
                HeapDestroy(v76);
                *(_QWORD *)(v4 + 1616) = 0;
              }
              v77 = (LPVOID *)(v4 + 1680);
              v78 = *(LPVOID **)(v4 + 1680);
              while ( v78 != v77 )
              {
                v79 = v78;
                v78 = (LPVOID *)*v78;
                pMemFree(v79[8]);
                pMemFree(v79[7]);
                pMemFree(v79[9]);
                pMemFree(v79);
              }
              *(_QWORD *)(v4 + 1688) = v77;
              *v77 = v77;
              goto LABEL_200;
            }
            goto LABEL_202;
          }
          memset_0(v44, 0, 0x58u);
          *(_QWORD *)v45[5].Data4 = v4;
          v45[3].Data1 = *(_DWORD *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 32);
          v46 = *(_QWORD *)(*v5 + v41 + 32);
          v47 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v46 + 8 * v43) )
            v47 = *(unsigned __int16 **)(v46 + 8 * v43);
          v48 = StringDup(v47);
          *(_QWORD *)&v45[4].Data1 = v48;
          if ( !v48 )
          {
            v56 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v85 + 32) + 8 * v43 + 8));
            }
            Data4 = (LPVOID *)v45[3].Data4;
LABEL_168:
            v68 = 0;
LABEL_169:
            *(_DWORD *)(v4 + 24) = 1;
LABEL_170:
            v91[7] = v56;
            pMemFree(*(LPVOID *)&v45[4].Data1);
            pMemFree(*Data4);
            pMemFree(*(LPVOID *)v45[4].Data4);
            pMemFree(v45);
            pMemFree(v68);
            goto LABEL_64;
          }
          v49 = *(_QWORD *)(*v5 + v41 + 32);
          v50 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v49 + 8 * v43 + 8) )
            v50 = *(unsigned __int16 **)(v49 + 8 * v43 + 8);
          v51 = StringDup(v50);
          Data4 = (LPVOID *)v45[3].Data4;
          *(_QWORD *)v45[3].Data4 = v51;
          if ( !v51 )
          {
            v56 = GetLastError();
            v69 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_168;
            }
            v70 = 27;
            v71 = *(_QWORD *)(*(_QWORD *)(*v5 + v85 + 32) + 8 * v43 + 8);
LABEL_158:
            WPP_SF_S(*((_QWORD *)v69 + 2), v70, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v71);
            goto LABEL_168;
          }
          v53 = *(_QWORD *)(*v5 + v41 + 32);
          v54 = (unsigned __int16 *)&Class;
          if ( *(_QWORD *)(v53 + 8 * v43 + 24) )
            v54 = *(unsigned __int16 **)(v53 + 8 * v43 + 24);
          v55 = StringDup(v54);
          *(_QWORD *)v45[4].Data4 = v55;
          if ( !v55 )
          {
            v56 = GetLastError();
            v69 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_168;
            }
            v70 = 28;
            v71 = *(_QWORD *)(*(_QWORD *)(*v5 + v85 + 32) + 8 * v43 + 24);
            goto LABEL_158;
          }
          v56 = IIDFromString(*(LPCOLESTR *)(*(_QWORD *)(*v5 + v41 + 32) + 8 * v43 + 16), v45 + 2);
          if ( v56 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                (unsigned int)&WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*v5 + v85 + 32) + 8 * v43 + 16),
                v56);
            }
            *(_DWORD *)(v4 + 24) = 2;
            v68 = 0;
            goto LABEL_170;
          }
          v57 = (const CHAR *)UnicodeStringToAnsiString((LPCWCH)*Data4);
          v58 = (CHAR *)v57;
          lpMem = v57;
          if ( !v57 )
          {
            v56 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids,
                *Data4);
            }
            v68 = 0;
            goto LABEL_169;
          }
          v59 = GetProcAddress(hModule, v57);
          *(_QWORD *)&v45[5].Data1 = v59;
          if ( !v59 )
          {
            v56 = GetLastError();
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
              v68 = (CHAR *)lpMem;
            }
            else
            {
              v68 = (CHAR *)lpMem;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_sl(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, v67, (_DWORD)lpMem, v56);
            }
            *(_DWORD *)(v4 + 24) = 5;
            goto LABEL_170;
          }
          pMemFree(v58);
          v60 = *(GUID ***)(v4 + 1688);
          *(_QWORD *)&v45->Data1 = v90;
          *(_QWORD *)v45->Data4 = v60;
          *v60 = v45;
          *(_QWORD *)(v4 + 1688) = v45;
          v41 = v85;
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
        }
        v42 = (unsigned int)(v87 + 1);
        v87 = v42;
        v40 = *v5;
      }
      while ( (unsigned int)v42 < *(_DWORD *)(*v5 + v41 + 24) );
    }
    *(_QWORD *)(v4 + 24) = 0;
    v61 = (_QWORD *)*v90;
    if ( (_QWORD *)*v90 != v93 )
    {
      v62 = qword_1400A7588;
      v63 = g_dwCountRoutingMethods;
      do
      {
        v64 = v61;
        v61 = (_QWORD *)*v61;
        v65 = (_QWORD *)v62;
        v62 = (__int64)(v64 + 2);
        v64[2] = &g_lstRoutingMethods;
        v64[3] = v65;
        *v65 = v64 + 2;
        qword_1400A7588 = (__int64)(v64 + 2);
        ++v63;
      }
      while ( v61 != v93 );
      g_dwCountRoutingMethods = v63;
    }
LABEL_200:
    if ( v4 )
    {
      v80 = (__int64 *)qword_1400A7550;
      *(_QWORD *)v91 = &g_lstRoutingExtensions;
      *((_QWORD *)v91 + 1) = v80;
      *v80 = v4;
      qword_1400A7550 = v4;
    }
LABEL_202:
    v2 = v88 + 1;
    v1 = a1;
  }
  SortMethodPriorities();
  if ( !g_dwCountRoutingMethods
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x140045da4  mov     [rsp+arg_8], rbx
0x140045da9  mov     [rsp+arg_10], rsi
0x140045dae  push    rdi
0x140045daf  push    r12
0x140045db1  push    r13
0x140045db3  push    r14
0x140045db5  push    r15
0x140045db7  sub     rsp, 5E0h
0x140045dbe  mov     rax, cs:__security_cookie
0x140045dc5  xor     rax, rsp
0x140045dc8  mov     [rsp+608h+var_38], rax
0x140045dd0  mov     r14, rcx
0x140045dd3  mov     [rsp+608h+var_580], rcx
0x140045ddb  mov     [rsp+608h+var_568], rcx
0x140045de3  mov     [rsp+608h+var_550], rcx
0x140045deb  xor     edi, edi
0x140045ded  mov     [rsp+608h+var_5A4], edi
0x140045df1  xorps   xmm0, xmm0
0x140045df4  movups  [rsp+608h+var_520], xmm0
0x140045dfc  movups  [rsp+608h+var_510], xmm0
0x140045e04  movups  [rsp+608h+var_500], xmm0
0x140045e0c  lea     ebx, [rdi+48h]
0x140045e0f  mov     r8d, ebx; Size
0x140045e12  xor     edx, edx; Val
0x140045e14  lea     rcx, [rsp+608h+var_4E8]; void *
0x140045e1c  call    memset_0
0x140045e21  lea     r13, WPP_GLOBAL_Control
0x140045e28  mov     rcx, cs:WPP_GLOBAL_Control
0x140045e2f  cmp     rcx, r13
0x140045e32  jz      short loc_140045E53
0x140045e34  test    byte ptr [rcx+1Ch], 4
0x140045e38  jz      short loc_140045E53
0x140045e3a  cmp     byte ptr [rcx+19h], 5
0x140045e3e  jb      short loc_140045E53
0x140045e40  lea     edx, [rdi+0Ch]
0x140045e43  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140045e4a  mov     rcx, [rcx+10h]
0x140045e4e  call    WPP_SF_
0x140045e53  mov     dword ptr [rsp+608h+var_520], 30h ; '0'
0x140045e5e  lea     r9, ?FaxRouteAddFile@@YAJKPEBGPEAU_GUID@@@Z; FaxRouteAddFile(ulong,ushort const *,_GUID *)
0x140045e65  mov     qword ptr [rsp+608h+var_520+8], r9
0x140045e6d  lea     r8, ?FaxRouteDeleteFile@@YAJKPEBG@Z; FaxRouteDeleteFile(ulong,ushort const *)
0x140045e74  mov     qword ptr [rsp+608h+var_510], r8
0x140045e7c  lea     rdx, ?FaxRouteGetFile@@YAHKKPEAGPEAK@Z; FaxRouteGetFile(ulong,ulong,ushort *,ulong *)
0x140045e83  mov     qword ptr [rsp+608h+var_510+8], rdx
0x140045e8b  lea     rcx, ?FaxRouteEnumFiles@@YAHKPEAU_GUID@@P6AHK00PEBGPEAX@Z2@Z; FaxRouteEnumFiles(ulong,_GUID *,int (*)(ulong,_GUID *,_GUID *,ushort const *,void *),void *)
0x140045e92  mov     qword ptr [rsp+608h+var_500], rcx
0x140045e9a  lea     rax, ?FaxRouteModifyRoutingData@@YAHKPEBGPEAEK@Z; FaxRouteModifyRoutingData(ulong,ushort const *,uchar *,ulong)
0x140045ea1  mov     qword ptr [rsp+608h+var_500+8], rax
0x140045ea9  mov     [rsp+608h+var_4E8], ebx
0x140045eb0  mov     [rsp+608h+var_4E0], r9
0x140045eb8  mov     [rsp+608h+var_4D8], r8
0x140045ec0  mov     [rsp+608h+var_4D0], rdx
0x140045ec8  mov     [rsp+608h+var_4C8], rcx
0x140045ed0  mov     [rsp+608h+var_4C0], rax
0x140045ed8  lea     rax, GetReceiptsConfiguration
0x140045edf  mov     [rsp+608h+var_4B8], rax
0x140045ee7  lea     rax, FreeReceiptsConfiguration
0x140045eee  mov     [rsp+608h+var_4B0], rax
0x140045ef6  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140045efd  mov     rcx, [rax+60h]
0x140045f01  mov     [rsp+608h+var_4A8], rcx
0x140045f09  mov     ebx, edi
0x140045f0b  mov     [rsp+608h+var_588], ebx
0x140045f12  cmp     ebx, [r14+18h]
0x140045f16  jnb     loc_140046E47
0x140045f1c  xor     edx, edx; Val
0x140045f1e  mov     r8d, 200h; Size
0x140045f24  lea     rcx, [rsp+608h+String1]; void *
0x140045f2c  call    memset_0
0x140045f31  xor     edx, edx; Val
0x140045f33  mov     r8d, 200h; Size
0x140045f39  lea     rcx, [rsp+608h+var_238]; void *
0x140045f41  call    memset_0
0x140045f46  mov     ecx, 6A0h; dwBytes
0x140045f4b  call    pMemAlloc
0x140045f50  mov     [rsp+608h+var_558], rax
0x140045f58  mov     rsi, rax
0x140045f5b  mov     [rsp+608h+lpMem], rax
0x140045f60  test    rax, rax
0x140045f63  jnz     short loc_140045FB3
0x140045f65  mov     rcx, cs:WPP_GLOBAL_Control
0x140045f6c  cmp     rcx, r13
0x140045f6f  jz      short loc_140045F9F
0x140045f71  test    byte ptr [rcx+1Ch], 4
0x140045f75  jz      short loc_140045F9F
0x140045f77  cmp     byte ptr [rcx+19h], 2
0x140045f7b  jb      short loc_140045F9F
0x140045f7d  mov     eax, ebx
0x140045f7f  lea     r8, [rax+rax*4]
0x140045f83  mov     r9, [r14+10h]
0x140045f87  lea     edx, [rsi+0Dh]
0x140045f8a  mov     r9, [r9+r8*8+8]
0x140045f8f  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140045f96  mov     rcx, [rcx+10h]
0x140045f9a  call    WPP_SF_S
0x140045f9f  mov     r14, [rsp+608h+var_550]
0x140045fa7  add     r14, 10h
0x140045fab  mov     r12d, ebx
0x140045fae  jmp     loc_140046C7F
0x140045fb3  mov     r12d, ebx
0x140045fb6  mov     [rsp+608h+var_5B8], ebx
0x140045fba  xor     edx, edx; Val
0x140045fbc  mov     r8d, 690h; Size
0x140045fc2  mov     rcx, rax; void *
0x140045fc5  call    memset_0
0x140045fca  lea     rax, [rsi+690h]
0x140045fd1  mov     [rsp+608h+var_560], rax
0x140045fd9  mov     [rsp+608h+var_528], rax
0x140045fe1  mov     [rsi+698h], rax
0x140045fe8  mov     [rax], rax
0x140045feb  mov     eax, ebx
0x140045fed  lea     rcx, [rax+rax*4]
0x140045ff1  lea     r15, ds:0[rcx*8]
0x140045ff9  mov     [rsp+608h+var_598], r15
0x140045ffe  add     r14, 10h
0x140046002  mov     [rsp+608h+var_570], r14
0x14004600a  mov     rax, [r14]
0x14004600d  lea     r8, Class
0x140046014  cmp     [r15+rax], rdi
0x140046018  cmovnz  r8, [r15+rax]
0x14004601d  lea     rdx, [rsi+34h]
0x140046021  mov     [rsp+608h+var_590], rdx
0x140046026  mov     eax, 7FFFFFFEh
0x14004602b  mov     ecx, 104h
0x140046030  test    rax, rax
0x140046033  jz      short loc_140046054
0x140046035  movzx   r9d, word ptr [r8]
0x140046039  test    r9w, r9w
0x14004603d  jz      short loc_140046054
0x14004603f  add     r8, 2
0x140046043  mov     [rdx], r9w
0x140046047  add     rdx, 2
0x14004604b  dec     rax
0x14004604e  sub     rcx, 1
0x140046052  jnz     short loc_140046030
0x140046054  mov     rax, rcx
0x140046057  neg     rax
0x14004605a  sbb     ebx, ebx
0x14004605c  not     ebx
0x14004605e  and     ebx, 8007007Ah
0x140046064  lea     rax, [rdx-2]
0x140046068  test    rcx, rcx
0x14004606b  cmovnz  rax, rdx
0x14004606f  mov     [rax], di
0x140046072  jz      loc_1400461EE
0x140046078  mov     rax, [r14]
0x14004607b  lea     rdx, Class
0x140046082  cmp     [rax+r15+8], rdi
0x140046087  cmovnz  rdx, [rax+r15+8]
0x14004608d  lea     r10, [rsi+23Ch]
0x140046094  mov     eax, 7FFFFFFEh
0x140046099  mov     ecx, 104h
0x14004609e  mov     r8, r10
0x1400460a1  test    rax, rax
0x1400460a4  jz      short loc_1400460C5
0x1400460a6  movzx   r9d, word ptr [rdx]
0x1400460aa  test    r9w, r9w
0x1400460ae  jz      short loc_1400460C5
0x1400460b0  add     rdx, 2
0x1400460b4  mov     [r8], r9w
0x1400460b8  add     r8, 2
0x1400460bc  dec     rax
0x1400460bf  sub     rcx, 1
0x1400460c3  jnz     short loc_1400460A1
0x1400460c5  mov     rax, rcx
0x1400460c8  neg     rax
0x1400460cb  sbb     ebx, ebx
0x1400460cd  not     ebx
0x1400460cf  and     ebx, 8007007Ah
0x1400460d5  lea     rax, [r8-2]
0x1400460d9  test    rcx, rcx
0x1400460dc  cmovnz  rax, r8
0x1400460e0  mov     [rax], di
0x1400460e3  jz      loc_1400461EE
0x1400460e9  mov     rax, [r14]
0x1400460ec  lea     rcx, Class
0x1400460f3  cmp     [rax+r15+10h], rdi
0x1400460f8  cmovnz  rcx, [rax+r15+10h]
0x1400460fe  mov     eax, 7FFFFFFEh
0x140046103  mov     edx, 104h
0x140046108  lea     r8, [rsi+444h]
0x14004610f  test    rax, rax
0x140046112  jz      short loc_140046133
0x140046114  movzx   r9d, word ptr [rcx]
0x140046118  test    r9w, r9w
0x14004611c  jz      short loc_140046133
0x14004611e  add     rcx, 2
0x140046122  mov     [r8], r9w
0x140046126  add     r8, 2
0x14004612a  dec     rax
0x14004612d  sub     rdx, 1
0x140046131  jnz     short loc_14004610F
0x140046133  lea     rax, [r8-2]
0x140046137  test    rdx, rdx
0x14004613a  cmovnz  rax, r8
0x14004613e  mov     [rax], di
0x140046141  mov     rax, rdx
0x140046144  neg     rax
0x140046147  sbb     ebx, ebx
0x140046149  not     ebx
0x14004614b  and     ebx, 8007007Ah
0x140046151  mov     [rsp+608h+var_5A8], ebx
0x140046155  test    rdx, rdx
0x140046158  jz      loc_1400461E5
0x14004615e  mov     [rsp+608h+ExtCount], 100h; ExtCount
0x140046167  lea     rax, [rsp+608h+var_238]
0x14004616f  mov     [rsp+608h+Ext], rax; Ext
0x140046174  mov     [rsp+608h+FilenameCount], 100h; FilenameCount
0x14004617d  lea     rax, [rsp+608h+String1]
0x140046185  mov     [rsp+608h+Filename], rax; Filename
0x14004618a  mov     [rsp+608h+DirCount], rdi; DirCount
0x14004618f  xor     r9d, r9d; Dir
0x140046192  xor     r8d, r8d; DriveCount
0x140046195  xor     edx, edx; Drive
0x140046197  mov     rcx, r10; FullPath
0x14004619a  call    cs:__imp__wsplitpath_s
0x1400461a1  nop     dword ptr [rax+rax+00h]
0x1400461a6  test    eax, eax
0x1400461a8  jz      short loc_1400461E5
0x1400461aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461b1  cmp     rcx, r13
0x1400461b4  jz      short loc_1400461DE
0x1400461b6  test    byte ptr [rcx+1Ch], 4
0x1400461ba  jz      short loc_1400461DE
0x1400461bc  cmp     byte ptr [rcx+19h], 2
0x1400461c0  jb      short loc_1400461DE
0x1400461c2  mov     edx, 0Eh
0x1400461c7  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400461ce  mov     rcx, [rcx+10h]
0x1400461d2  call    WPP_SF_
0x1400461d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461de  mov     ebx, 80004005h
0x1400461e3  jmp     short loc_1400461F5
0x1400461e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461ec  jmp     short loc_1400461F9
0x1400461ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461f5  mov     [rsp+608h+var_5A8], ebx
0x1400461f9  test    ebx, ebx
0x1400461fb  jns     short loc_140046247
0x1400461fd  cmp     rcx, r13
0x140046200  jz      short loc_140046226
0x140046202  test    byte ptr [rcx+1Ch], 4
0x140046206  jz      short loc_140046226
0x140046208  cmp     byte ptr [rcx+19h], 2
0x14004620c  jb      short loc_140046226
0x14004620e  mov     edx, 0Fh
0x140046213  mov     r9d, ebx
0x140046216  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x14004621d  mov     rcx, [rcx+10h]
0x140046221  call    WPP_SF_d
0x140046226  mov     dword ptr [rsi+18h], 6
0x14004622d  mov     eax, ebx
0x14004622f  and     eax, 1FFF0000h
0x140046234  cmp     eax, 70000h
0x140046239  jnz     loc_140046C7C
0x14004623f  movzx   ebx, bx
0x140046242  jmp     loc_140046C7C
0x140046247  lea     rdx, aFxsroute; "FXSROUTE"
0x14004624e  lea     rcx, [rsp+608h+String1]; String1
0x140046256  call    cs:__imp__wcsicmp
0x14004625d  nop     dword ptr [rax+rax+00h]
0x140046262  test    eax, eax
0x140046264  jnz     short loc_14004628F
0x140046266  lea     rdx, aDll; ".DLL"
0x14004626d  lea     rcx, [rsp+608h+var_238]; String1
0x140046275  call    cs:__imp__wcsicmp
0x14004627c  nop     dword ptr [rax+rax+00h]
0x140046281  test    eax, eax
0x140046283  jnz     short loc_14004628F
0x140046285  mov     dword ptr [rsi+658h], 1
0x14004628f  lea     r12, [rsi+658h]
0x140046296  cmp     [r12], edi
0x14004629a  jz      short loc_1400462E5
0x14004629c  cmp     [rsp+608h+var_4A8], rdi
0x1400462a4  jnz     short loc_1400462E5
0x1400462a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400462ad  cmp     rcx, r13
0x1400462b0  jz      short loc_1400462DB
0x1400462b2  test    byte ptr [rcx+1Ch], 4
0x1400462b6  jz      short loc_1400462DB
0x1400462b8  cmp     byte ptr [rcx+19h], 2
0x1400462bc  jb      short loc_1400462DB
0x1400462be  mov     r9, [r14]
0x1400462c1  mov     edx, 10h
0x1400462c6  mov     r9, [r9+r15+8]
0x1400462cb  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400462d2  mov     rcx, [rcx+10h]
0x1400462d6  call    WPP_SF_S
0x1400462db  mov     r12d, [rsp+608h+var_5B8]
0x1400462e0  jmp     loc_140046C7F
0x1400462e5  mov     rcx, [r14]
0x1400462e8  mov     rcx, [rcx+r15+8]; lpLibFileName
0x1400462ed  call    cs:__imp_LoadLibraryW
0x1400462f4  nop     dword ptr [rax+rax+00h]
0x1400462f9  mov     [rsp+608h+hModule], rax
0x1400462fe  test    rax, rax
0x140046301  jnz     short loc_140046356
0x140046303  call    cs:__imp_GetLastError
0x14004630a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
