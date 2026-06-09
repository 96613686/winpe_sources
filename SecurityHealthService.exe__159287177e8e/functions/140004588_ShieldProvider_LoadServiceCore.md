# ShieldProvider::LoadServiceCore

- ea: `0x140004588`
- end: `0x140004e7d`
- name: `ShieldProvider::LoadServiceCore`
- size: `2293`
- prototype: `__int64(unsigned int, __int64, char, ...)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004588`
- `0x140005110`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140003a94`
- `0x140003db4`
- `0x140003e58`
- `0x140004588`
- `0x14000536c`
- `0x1400053f4`
- `0x140005e1c`
- `0x1400071c0`
- `0x140007384`
- `0x14000e990`
- `0x14000ec7c`
- `0x14000efc4`
- `0x1400100bc`
- `0x14001088c`
- `0x140013010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14000492a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14000492a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140004886`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140004886`
- `KERNEL32!EnterCriticalSection` at `0x140004bc9`
- `KERNEL32!EnterCriticalSection` at `0x140004c19`
- `KERNEL32!EnterCriticalSection` at `0x140004bc9`
- `KERNEL32!EnterCriticalSection` at `0x140004c19`
- `KERNEL32!LeaveCriticalSection` at `0x140004bda`
- `KERNEL32!LeaveCriticalSection` at `0x140004c2b`
- `KERNEL32!LeaveCriticalSection` at `0x140004bda`
- `KERNEL32!LeaveCriticalSection` at `0x140004c2b`
- `KERNEL32!FreeLibrary` at `0x140004ab1`
- `KERNEL32!FreeLibrary` at `0x140004c6e`
- `KERNEL32!FreeLibrary` at `0x140004ab1`
- `KERNEL32!FreeLibrary` at `0x140004c6e`
- `KERNEL32!Sleep` at `0x1400045c7`
- `KERNEL32!Sleep` at `0x1400045c7`
- `KERNEL32!GetTickCount64` at `0x140004c74`
- `KERNEL32!GetTickCount64` at `0x140004c74`
- `KERNEL32!CloseHandle` at `0x14000476f`
- `KERNEL32!CloseHandle` at `0x1400047e0`
- `KERNEL32!CloseHandle` at `0x14000485f`
- `KERNEL32!CloseHandle` at `0x1400048de`
- `KERNEL32!CloseHandle` at `0x1400049d4`
- `KERNEL32!CloseHandle` at `0x140004af5`
- `KERNEL32!CloseHandle` at `0x140004d19`
- `KERNEL32!CloseHandle` at `0x140004dd0`
- `KERNEL32!CloseHandle` at `0x14000476f`
- `KERNEL32!CloseHandle` at `0x1400047e0`
- `KERNEL32!CloseHandle` at `0x14000485f`
- `KERNEL32!CloseHandle` at `0x1400048de`
- `KERNEL32!CloseHandle` at `0x1400049d4`
- `KERNEL32!CloseHandle` at `0x140004af5`
- `KERNEL32!CloseHandle` at `0x140004d19`
- `KERNEL32!CloseHandle` at `0x140004dd0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004674`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046e4`
- `ole32!CoFreeUnusedLibrariesEx` at `0x1400045bf`
- `ole32!CoFreeUnusedLibrariesEx` at `0x1400045d1`
- `ole32!CoFreeUnusedLibrariesEx` at `0x1400045bf`
- `ole32!CoFreeUnusedLibrariesEx` at `0x1400045d1`

## string_xrefs

- `0x140004652`: `SOFTWARE\Microsoft\Windows Security Health\Platform`

## pseudocode

```c
__int64 ShieldProvider::LoadServiceCore(unsigned int a1, __int64 a2, char a3, ...)
{
  int ServiceCorePath; // eax
  unsigned __int64 v5; // r8
  unsigned int v6; // r9d
  unsigned int v7; // ebx
  _UNKNOWN **v8; // rdx
  int v10; // eax
  HKEY v11; // rbx
  LSTATUS v12; // eax
  _QWORD *v13; // rcx
  void **v14; // rbx
  int File; // eax
  unsigned __int64 v16; // rdx
  void *v17; // r8
  unsigned int v18; // r9d
  unsigned int v19; // edi
  HANDLE v20; // rdi
  int FileNameFromFileHandle; // eax
  unsigned __int64 v22; // rdx
  const unsigned __int16 *v23; // r8
  unsigned int v24; // esi
  HKEY v25; // rsi
  int v26; // eax
  unsigned __int64 v27; // rdx
  unsigned int v28; // r12d
  HANDLE v29; // r12
  wchar_t *v30; // rax
  unsigned __int64 v31; // rdx
  unsigned int v32; // r8d
  void *v33; // r9
  int NormalizedPath; // eax
  unsigned __int64 v35; // rdx
  HKEY v36; // r14
  char v37; // al
  char *v38; // rcx
  char *v39; // r14
  int v40; // eax
  unsigned __int64 v41; // rdx
  unsigned int v42; // r14d
  int v43; // eax
  char *v44; // rcx
  int Library; // eax
  _UNKNOWN **v46; // rdx
  const char *v47; // r9
  HKEY v48; // rcx
  char *v49; // rcx
  __int64 (**v50)(void); // r15
  int ProcAddress; // eax
  const char *v52; // r9
  _QWORD *v53; // rcx
  __int64 v54; // rdx
  HKEY v55; // r12
  int v56; // r13d
  ULONGLONG TickCount64; // rax
  unsigned __int64 v58; // rdx
  __int64 v59; // r8
  unsigned int v60; // eax
  char *v61; // rcx
  int v62; // r15d
  _QWORD *v63; // rcx
  __int64 v64; // rdx
  char *v65; // rcx
  unsigned int v66; // [rsp+20h] [rbp-48h]
  bool v67; // [rsp+20h] [rbp-48h]
  bool v68; // [rsp+20h] [rbp-48h]
  unsigned int v69; // [rsp+30h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *v70; // [rsp+38h] [rbp-30h]
  void *v71; // [rsp+40h] [rbp-28h]
  bool v72; // [rsp+40h] [rbp-28h]
  unsigned __int8 v73; // [rsp+40h] [rbp-28h]
  HANDLE hObject; // [rsp+48h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  __int64 (__fastcall *v76[2])(_QWORD, __int64); // [rsp+58h] [rbp-10h] BYREF
  char v79; // [rsp+C0h] [rbp+58h] BYREF
  char *v80; // [rsp+C8h] [rbp+60h] BYREF
  va_list va; // [rsp+C8h] [rbp+60h]
  va_list va1; // [rsp+D0h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v80 = va_arg(va1, char *);
  *v80 = 0;
  if ( a3 )
  {
    CoFreeUnusedLibrariesEx(0x3E8u, 0);
    Sleep(0x3E8u);
    CoFreeUnusedLibrariesEx(0x3E8u, 0);
  }
  hObject = 0;
  ServiceCorePath = ShieldProvider::GetServiceCorePath(&hObject, a1);
  v7 = ServiceCorePath;
  if ( ServiceCorePath < 0 )
  {
    v8 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)ServiceCorePath);
    if ( hObject )
      operator delete(hObject, (unsigned __int64)v8);
    return v7;
  }
  if ( a1 != 2 )
    goto LABEL_22;
  hKey = 0;
  v10 = ShieldProvider::ShieldUtilRegOpenKey(
          (ShieldProvider *)&hKey,
          (HKEY *)L"SOFTWARE\\Microsoft\\Windows Security Health\\Platform",
          (const unsigned __int16 *)0x20006,
          v6);
  v11 = hKey;
  if ( v10 < 0 )
    goto LABEL_19;
  v12 = RegDeleteValueW(hKey, L"NewLocation");
  v5 = (unsigned int)v12;
  if ( v12 > 0 )
    v5 = (unsigned __int16)v12 | 0x80070000;
  if ( (int)(v5 + 0x80000000) < 0 || (_DWORD)v5 == -2147024894 )
    goto LABEL_19;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_473dbbf2212f33a3d422106396b3062c_Traceguids,
      (unsigned int)L"NewLocation",
      v5);
LABEL_19:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    RegCloseKey(v11);
LABEL_22:
    v13 = WPP_GLOBAL_Control;
  }
  v14 = (void **)hObject;
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
    WPP_SF_dS(v13[2], 22, (unsigned int)WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, a1, (__int64)hObject);
  hObject = (HANDLE)-1LL;
  File = CommonUtil::UtilCreateFile(
           (CommonUtil *)&hObject,
           v14,
           (const unsigned __int16 *)v5,
           v6,
           v66,
           0,
           v69,
           v70,
           v71);
  v19 = File;
  if ( File < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)File);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v14 )
      operator delete(v14, v16);
    return v19;
  }
  v20 = hObject;
  hKey = 0;
  FileNameFromFileHandle = ShieldProvider::GetFileNameFromFileHandle(
                             (ShieldProvider *)&hKey,
                             (unsigned __int16 **)hObject,
                             v17,
                             v18);
  v24 = FileNameFromFileHandle;
  if ( FileNameFromFileHandle < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)FileNameFromFileHandle);
    if ( hKey )
      operator delete(hKey, v22);
    if ( v20 != (HANDLE)-1LL )
      CloseHandle(v20);
    if ( v14 )
      operator delete(v14, v22);
    return v24;
  }
  v25 = hKey;
  hObject = 0;
  v26 = CommonUtil::HrDuplicateStringW((CommonUtil *)&hObject, (unsigned __int16 **)hKey, v23);
  v28 = v26;
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)v26);
    if ( hObject )
      operator delete(hObject, v27);
    if ( v25 )
      operator delete(v25, v27);
    if ( v20 != (HANDLE)-1LL )
      CloseHandle(v20);
    if ( v14 )
      operator delete(v14, v27);
    return v28;
  }
  v29 = hObject;
  v30 = wcsrchr((const wchar_t *)hObject, 0x5Cu);
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, 2147942523LL);
    if ( v29 )
      operator delete(v29, v31);
    if ( v25 )
      operator delete(v25, v31);
    if ( v20 != (HANDLE)-1LL )
      CloseHandle(v20);
    if ( v14 )
      operator delete(v14, v31);
    return 2147942523LL;
  }
  *v30 = 0;
  if ( !a1 )
    goto LABEL_79;
  v72 = 0;
  hKey = 0;
  NormalizedPath = ShieldProvider::GetNormalizedPath((unsigned __int16 *)v29);
  v36 = hKey;
  if ( NormalizedPath >= 0 )
    v72 = _wcsicmp(String1, (const wchar_t *)hKey) == 0;
  if ( v36 )
    operator delete(v36, v35);
  if ( v72 )
LABEL_79:
    v37 = 1;
  else
    v37 = 0;
  v38 = v80;
  v39 = 0;
  v73 = v37;
  v80 = 0;
  *v38 = v37;
  if ( !v37 )
  {
    v40 = CommonUtil::MpUtilMicrosoftCertCheck(
            (void **)v25,
            (const unsigned __int16 *)(ShieldProvider::g_fDevMode ? 36 : 4),
            v32,
            v33);
    v42 = v40;
    if ( v40 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
          (unsigned int)v40);
LABEL_85:
      if ( v29 )
        operator delete(v29, v41);
      if ( v25 )
        operator delete(v25, v41);
      if ( v20 != (HANDLE)-1LL )
        CloseHandle(v20);
      if ( v14 )
        operator delete(v14, v41);
      return v42;
    }
    v43 = CommonUtil::NewRefInstance<ShieldProvider::PathAdder,unsigned short *>((char **)va, &hObject);
    v42 = v43;
    if ( v43 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
          (unsigned int)v43);
      if ( v80 )
      {
        v44 = &v80[*(int *)(*(_QWORD *)v80 + 4LL)];
        (*(void (__fastcall **)(char *))(*(_QWORD *)v44 + 8LL))(v44);
      }
      goto LABEL_85;
    }
    v39 = v80;
  }
  hKey = 0;
  Library = CommonUtil::UtilLoadLibraryEx(
              (CommonUtil *)&hKey,
              (HINSTANCE *)v25,
              (const unsigned __int16 *)0x1000,
              (unsigned int)v33);
  LODWORD(v80) = Library;
  if ( Library < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)Library);
    v48 = hKey;
    if ( !hKey )
      goto LABEL_107;
    goto LABEL_106;
  }
  v50 = (__int64 (**)(void))hKey;
  v76[0] = 0;
  ProcAddress = CommonUtil::UtilRawGetProcAddress(
                  (CommonUtil *)v76,
                  (__int64 (**)(void))hKey,
                  (HINSTANCE)&stru_1400155A8,
                  v47,
                  v67);
  LODWORD(v80) = ProcAddress;
  if ( ProcAddress < 0 )
  {
    v53 = WPP_GLOBAL_Control;
    v46 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_123;
    v54 = 30;
LABEL_122:
    WPP_SF_d(v53[2], v54, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)ProcAddress);
LABEL_123:
    if ( !v50 )
      goto LABEL_107;
    v48 = (HKEY)v50;
LABEL_106:
    FreeLibrary((HMODULE)v48);
LABEL_107:
    if ( v39 )
    {
      v49 = &v39[*(int *)(*(_QWORD *)v39 + 4LL)];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v49 + 8LL))(v49);
    }
    if ( v29 )
      operator delete(v29, (unsigned __int64)v46);
    if ( v25 )
      operator delete(v25, (unsigned __int64)v46);
    if ( v20 != (HANDLE)-1LL )
      CloseHandle(v20);
    if ( v14 )
      operator delete(v14, (unsigned __int64)v46);
    return (unsigned int)v80;
  }
  hKey = 0;
  ProcAddress = CommonUtil::UtilRawGetProcAddress((CommonUtil *)&hKey, v50, (HINSTANCE)&stru_1400155B8, v52, v68);
  LODWORD(v80) = ProcAddress;
  if ( ProcAddress < 0 )
  {
    v53 = WPP_GLOBAL_Control;
    v46 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_123;
    v54 = 31;
    goto LABEL_122;
  }
  v55 = hKey;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  *(_QWORD *)(a2 + 88) = v55;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  *(_DWORD *)(a2 + 96) = ShieldProvider::g_fDevMode | (2 * v73);
  LODWORD(v80) = v76[0](0, a2);
  *(_DWORD *)(a2 + 96) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  *(_QWORD *)(a2 + 88) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  v56 = (int)v80;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
      (unsigned int)v80);
  if ( v50 )
    FreeLibrary((HMODULE)v50);
  TickCount64 = GetTickCount64();
  if ( TickCount64 - qword_14001B960 <= 0xEA60 )
  {
    v60 = dword_14001B95C + 1;
  }
  else
  {
    qword_14001B960 = TickCount64;
    v60 = 0;
  }
  dword_14001B95C = v60;
  v79 = 0;
  if ( v60 > 5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids);
    goto LABEL_141;
  }
  if ( v56 != 4 )
  {
    if ( v56 == 3 )
    {
      LOBYTE(v59) = 1;
      v62 = ShieldProvider::LoadServiceCore(1, a2, v59, &v79);
      if ( v62 < 0 )
      {
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_158;
        v64 = 35;
        goto LABEL_157;
      }
    }
    else if ( v56 == 2 )
    {
      LOBYTE(v59) = 1;
      v62 = ShieldProvider::LoadServiceCore(0, a2, v59, &v79);
      if ( v62 < 0 )
      {
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_158;
        v64 = 36;
        goto LABEL_157;
      }
    }
LABEL_141:
    if ( v39 )
    {
      v61 = &v39[*(int *)(*(_QWORD *)v39 + 4LL)];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v61 + 8LL))(v61);
    }
    if ( hObject )
      operator delete(hObject, v58);
    if ( v25 )
      operator delete(v25, v58);
    if ( v20 != (HANDLE)-1LL )
      CloseHandle(v20);
    if ( v14 )
      operator delete(v14, v58);
    return 0;
  }
  LOBYTE(v59) = 1;
  v62 = ShieldProvider::LoadServiceCore(2, a2, v59, &v79);
  if ( v62 >= 0 )
    goto LABEL_141;
  v63 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_158;
  v64 = 34;
LABEL_157:
  WPP_SF_d(v63[2], v64, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)v62);
LABEL_158:
  if ( v39 )
  {
    v65 = &v39[*(int *)(*(_QWORD *)v39 + 4LL)];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v65 + 8LL))(v65);
  }
  if ( hObject )
    operator delete(hObject, v58);
  if ( v25 )
    operator delete(v25, v58);
  if ( v20 != (HANDLE)-1LL )
    CloseHandle(v20);
  if ( v14 )
    operator delete(v14, v58);
  return (unsigned int)v62;
}

```

## disassembly

```asm
0x140004588  mov     [rsp-40h+arg_18], r9
0x14000458d  mov     [rsp-40h+arg_8], rdx
0x140004592  mov     [rsp-40h+arg_0], ecx
0x140004596  push    rbp
0x140004597  push    rbx
0x140004598  push    rsi
0x140004599  push    rdi
0x14000459a  push    r12
0x14000459c  push    r13
0x14000459e  push    r14
0x1400045a0  push    r15
0x1400045a2  mov     rbp, rsp
0x1400045a5  sub     rsp, 68h
0x1400045a9  xor     r12d, r12d
0x1400045ac  mov     edi, ecx
0x1400045ae  mov     [r9], r12b
0x1400045b1  test    r8b, r8b
0x1400045b4  jz      short loc_1400045D7
0x1400045b6  mov     ebx, 3E8h
0x1400045bb  xor     edx, edx; dwReserved
0x1400045bd  mov     ecx, ebx; dwUnloadDelay
0x1400045bf  call    cs:__imp_CoFreeUnusedLibrariesEx
0x1400045c5  mov     ecx, ebx; dwMilliseconds
0x1400045c7  call    cs:__imp_Sleep
0x1400045cd  xor     edx, edx; dwReserved
0x1400045cf  mov     ecx, ebx; dwUnloadDelay
0x1400045d1  call    cs:__imp_CoFreeUnusedLibrariesEx
0x1400045d7  mov     edx, edi
0x1400045d9  mov     [rbp+hObject], r12
0x1400045dd  lea     rcx, [rbp+hObject]
0x1400045e1  call    ShieldProvider__GetServiceCorePath
0x1400045e6  mov     ebx, eax
0x1400045e8  test    eax, eax
0x1400045ea  jns     short loc_140004632
0x1400045ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045f3  lea     rdx, WPP_GLOBAL_Control
0x1400045fa  cmp     rcx, rdx
0x1400045fd  jz      short loc_14000461D
0x1400045ff  test    byte ptr [rcx+1Ch], 1
0x140004603  jz      short loc_14000461D
0x140004605  mov     rcx, [rcx+10h]
0x140004609  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004610  mov     edx, 15h
0x140004615  mov     r9d, eax
0x140004618  call    WPP_SF_d
0x14000461d  mov     rcx, [rbp+hObject]; void *
0x140004621  test    rcx, rcx
0x140004624  jz      short loc_14000462B
0x140004626  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000462b  mov     eax, ebx
0x14000462d  jmp     loc_140004D2E
0x140004632  lea     r15, WPP_GLOBAL_Control
0x140004639  mov     r13d, 1
0x14000463f  cmp     edi, 2
0x140004642  jnz     loc_1400046EA
0x140004648  mov     r8d, 20006h; unsigned __int16 *
0x14000464e  mov     [rbp+hKey], r12
0x140004652  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Security H"...
0x140004659  lea     rcx, [rbp+hKey]; this
0x14000465d  call    ?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)
0x140004662  mov     rbx, [rbp+hKey]
0x140004666  test    eax, eax
0x140004668  js      short loc_1400046D5
0x14000466a  lea     rdx, ValueName; "NewLocation"
0x140004671  mov     rcx, rbx; hKey
0x140004674  call    cs:__imp_RegDeleteValueW
0x14000467a  mov     r8d, eax
0x14000467d  test    eax, eax
0x14000467f  jle     short loc_14000468C
0x140004681  movzx   r8d, ax
0x140004685  or      r8d, 80070000h
0x14000468c  mov     ecx, 80000000h
0x140004691  lea     eax, [r8+rcx]
0x140004695  test    ecx, eax
0x140004697  jnz     short loc_1400046D5
0x140004699  cmp     r8d, 80070002h
0x1400046a0  jz      short loc_1400046D5
0x1400046a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046a9  cmp     rcx, r15
0x1400046ac  jz      short loc_1400046DC
0x1400046ae  test    [rcx+1Ch], r13b
0x1400046b2  jz      short loc_1400046DC
0x1400046b4  mov     rcx, [rcx+10h]
0x1400046b8  lea     r9, ValueName; "NewLocation"
0x1400046bf  mov     dword ptr [rsp+68h+var_48], r8d
0x1400046c4  mov     edx, 1Dh
0x1400046c9  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x1400046d0  call    WPP_SF_Sd
0x1400046d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046dc  test    rbx, rbx
0x1400046df  jz      short loc_1400046F1
0x1400046e1  mov     rcx, rbx; hKey
0x1400046e4  call    cs:__imp_RegCloseKey
0x1400046ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046f1  mov     rbx, [rbp+hObject]
0x1400046f5  lea     r14, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x1400046fc  cmp     rcx, r15
0x1400046ff  jz      short loc_140004720
0x140004701  test    byte ptr [rcx+1Ch], 4
0x140004705  jz      short loc_140004720
0x140004707  mov     rcx, [rcx+10h]
0x14000470b  mov     edx, 16h
0x140004710  mov     r9d, edi
0x140004713  mov     qword ptr [rsp+68h+var_48], rbx; bool
0x140004718  mov     r8, r14
0x14000471b  call    WPP_SF_dS
0x140004720  mov     rdx, rbx; void **
0x140004723  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x14000472b  lea     rcx, [rbp+hObject]; this
0x14000472f  mov     [rsp+68h+var_40], r12d; unsigned int
0x140004734  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x140004739  mov     edi, eax
0x14000473b  test    eax, eax
0x14000473d  jns     short loc_140004789
0x14000473f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004746  cmp     rcx, r15
0x140004749  jz      short loc_140004765
0x14000474b  test    [rcx+1Ch], r13b
0x14000474f  jz      short loc_140004765
0x140004751  mov     rcx, [rcx+10h]
0x140004755  mov     edx, 17h
0x14000475a  mov     r9d, eax
0x14000475d  mov     r8, r14
0x140004760  call    WPP_SF_d
0x140004765  mov     rcx, [rbp+hObject]; hObject
0x140004769  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000476d  jz      short loc_140004775
0x14000476f  call    cs:__imp_CloseHandle
0x140004775  test    rbx, rbx
0x140004778  jz      short loc_140004782
0x14000477a  mov     rcx, rbx; void *
0x14000477d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004782  mov     eax, edi
0x140004784  jmp     loc_140004D2E
0x140004789  mov     rdi, [rbp+hObject]
0x14000478d  lea     rcx, [rbp+hKey]; this
0x140004791  mov     rdx, rdi; unsigned __int16 **
0x140004794  mov     [rbp+hKey], r12
0x140004798  call    ?GetFileNameFromFileHandle@ShieldProvider@@YAJPEAPEAGPEAXK@Z; ShieldProvider::GetFileNameFromFileHandle(ushort * *,void *,ulong)
0x14000479d  mov     esi, eax
0x14000479f  test    eax, eax
0x1400047a1  jns     short loc_1400047FA
0x1400047a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047aa  cmp     rcx, r15
0x1400047ad  jz      short loc_1400047C9
0x1400047af  test    [rcx+1Ch], r13b
0x1400047b3  jz      short loc_1400047C9
0x1400047b5  mov     rcx, [rcx+10h]
0x1400047b9  mov     edx, 18h
0x1400047be  mov     r9d, eax
0x1400047c1  mov     r8, r14
0x1400047c4  call    WPP_SF_d
0x1400047c9  mov     rcx, [rbp+hKey]; void *
0x1400047cd  test    rcx, rcx
0x1400047d0  jz      short loc_1400047D7
0x1400047d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400047d7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400047db  jz      short loc_1400047E6
0x1400047dd  mov     rcx, rdi; hObject
0x1400047e0  call    cs:__imp_CloseHandle
0x1400047e6  test    rbx, rbx
0x1400047e9  jz      short loc_1400047F3
0x1400047eb  mov     rcx, rbx; void *
0x1400047ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400047f3  mov     eax, esi
0x1400047f5  jmp     loc_140004D2E
0x1400047fa  mov     rsi, [rbp+hKey]
0x1400047fe  lea     rcx, [rbp+hObject]; this
0x140004802  mov     rdx, rsi; unsigned __int16 **
0x140004805  mov     [rbp+hObject], r12
0x140004809  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x14000480e  mov     r12d, eax
0x140004811  test    eax, eax
0x140004813  jns     short loc_14000487A
0x140004815  mov     rcx, cs:WPP_GLOBAL_Control
0x14000481c  cmp     rcx, r15
0x14000481f  jz      short loc_14000483B
0x140004821  test    [rcx+1Ch], r13b
0x140004825  jz      short loc_14000483B
0x140004827  mov     rcx, [rcx+10h]
0x14000482b  mov     edx, 19h
0x140004830  mov     r9d, eax
0x140004833  mov     r8, r14
0x140004836  call    WPP_SF_d
0x14000483b  mov     rcx, [rbp+hObject]; void *
0x14000483f  test    rcx, rcx
0x140004842  jz      short loc_140004849
0x140004844  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004849  test    rsi, rsi
0x14000484c  jz      short loc_140004856
0x14000484e  mov     rcx, rsi; void *
0x140004851  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004856  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000485a  jz      short loc_140004865
0x14000485c  mov     rcx, rdi; hObject
0x14000485f  call    cs:__imp_CloseHandle
0x140004865  test    rbx, rbx
0x140004868  jz      short loc_140004872
0x14000486a  mov     rcx, rbx; void *
0x14000486d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004872  mov     eax, r12d
0x140004875  jmp     loc_140004D2E
0x14000487a  mov     r12, [rbp+hObject]
0x14000487e  mov     edx, 5Ch ; '\'; Ch
0x140004883  mov     rcx, r12; Str
0x140004886  call    cs:__imp_wcsrchr
0x14000488c  mov     rcx, rax
0x14000488f  test    rax, rax
0x140004892  jnz     short loc_1400048FB
0x140004894  mov     rcx, cs:WPP_GLOBAL_Control
0x14000489b  cmp     rcx, r15
0x14000489e  jz      short loc_1400048BB
0x1400048a0  test    [rcx+1Ch], r13b
0x1400048a4  jz      short loc_1400048BB
0x1400048a6  mov     rcx, [rcx+10h]
0x1400048aa  lea     edx, [rax+1Ah]
0x1400048ad  mov     r9d, 8007007Bh
0x1400048b3  mov     r8, r14
0x1400048b6  call    WPP_SF_d
0x1400048bb  test    r12, r12
0x1400048be  jz      short loc_1400048C8
0x1400048c0  mov     rcx, r12; void *
0x1400048c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400048c8  test    rsi, rsi
0x1400048cb  jz      short loc_1400048D5
0x1400048cd  mov     rcx, rsi; void *
0x1400048d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400048d5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400048d9  jz      short loc_1400048E4
0x1400048db  mov     rcx, rdi; hObject
0x1400048de  call    cs:__imp_CloseHandle
0x1400048e4  test    rbx, rbx
0x1400048e7  jz      short loc_1400048F1
0x1400048e9  mov     rcx, rbx; void *
0x1400048ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400048f1  mov     eax, 8007007Bh
0x1400048f6  jmp     loc_140004D2E
0x1400048fb  xor     eax, eax
0x1400048fd  mov     [rcx], ax
0x140004900  cmp     [rbp+arg_0], eax
0x140004903  jz      short loc_14000494D
0x140004905  lea     rdx, [rbp+hKey]
0x140004909  mov     byte ptr [rbp+var_28], al
0x14000490c  mov     rcx, r12; unsigned __int16 *
0x14000490f  mov     [rbp+hKey], rax
0x140004913  call    ShieldProvider__GetNormalizedPath
0x140004918  mov     r14, [rbp+hKey]
0x14000491c  test    eax, eax
0x14000491e  js      short loc_140004936
0x140004920  mov     rcx, cs:String1; String1
0x140004927  mov     rdx, r14; String2
0x14000492a  call    cs:__imp__wcsicmp
0x140004930  test    eax, eax
0x140004932  setz    byte ptr [rbp+var_28]
0x140004936  test    r14, r14
0x140004939  jz      short loc_140004943
0x14000493b  mov     rcx, r14; void *
0x14000493e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004943  cmp     byte ptr [rbp+var_28], 0
0x140004947  jnz     short loc_14000494D
0x140004949  xor     al, al
0x14000494b  jmp     short loc_140004950
0x14000494d  mov     al, r13b
0x140004950  mov     rcx, [rbp+arg_18]
0x140004954  xor     r14d, r14d
0x140004957  mov     byte ptr [rbp+var_28], al
0x14000495a  mov     [rbp+arg_18], r14
0x14000495e  mov     [rcx], al
0x140004960  test    al, al
0x140004962  jnz     loc_140004A59
0x140004968  mov     al, cs:?g_fDevMode@ShieldProvider@@3_NA; bool ShieldProvider::g_fDevMode
0x14000496e  mov     rcx, rsi; this
0x140004971  neg     al
0x140004973  sbb     edx, edx
0x140004975  and     edx, 20h
0x140004978  add     edx, 4; unsigned __int16 *
0x14000497b  call    ?MpUtilMicrosoftCertCheck@CommonUtil@@YAJPEBGKPEAX@Z; CommonUtil::MpUtilMicrosoftCertCheck(ushort const *,ulong,void *)
0x140004980  mov     r14d, eax
0x140004983  test    eax, eax
0x140004985  jns     short loc_1400049EF
0x140004987  mov     rcx, cs:WPP_GLOBAL_Control
0x14000498e  cmp     rcx, r15
0x140004991  jz      short loc_1400049B1
0x140004993  test    [rcx+1Ch], r13b
0x140004997  jz      short loc_1400049B1
0x140004999  mov     rcx, [rcx+10h]
0x14000499d  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x1400049a4  mov     edx, 1Bh
0x1400049a9  mov     r9d, eax
0x1400049ac  call    WPP_SF_d
0x1400049b1  test    r12, r12
0x1400049b4  jz      short loc_1400049BE
0x1400049b6  mov     rcx, r12; void *
0x1400049b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400049be  test    rsi, rsi
0x1400049c1  jz      short loc_1400049CB
0x1400049c3  mov     rcx, rsi; void *
0x1400049c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400049cb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400049cf  jz      short loc_1400049DA
  ... truncated ...
```
