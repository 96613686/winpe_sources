# CDeploymentSessionWrapper::PostDownload(ushort const *,ushort const *,ushort const *)

- ea: `0x18019da38`
- end: `0x18019e33a`
- name: `?PostDownload@CDeploymentSessionWrapper@@QEAAJPEBG00@Z`
- size: `2306`
- prototype: `int(CDeploymentSessionWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18019e340`
- `0x18019e430`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x180068c4c`
- `0x18006fab0`
- `0x1801961c4`
- `0x180197644`
- `0x180198e84`
- `0x18019bb68`
- `0x18019cb24`
- `0x18019da38`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019df5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019dfdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019df5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019dfdc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18019dfc8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18019dfc8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18019e2a6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18019e2a6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18019df49`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18019df49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019de78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019dea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019e2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019e301`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019de78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019dea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019e2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019e301`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019de63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019de90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e2b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e2ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019de63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019de90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e2b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e2ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019db1c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019dbd4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019debf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019db1c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019dbd4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019debf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019dc6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019dc6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019dcd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019dcd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019dcbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019dcbd`

## string_xrefs

- `0x18019dd7d`: `UpdateAgent.dll`
- `0x18019df30`: `DeploymentSessionWrapper: Loading Update Agent from [%s]`
- `0x18019dfbe`: `CreateOfflineDeploymentSession`
- `0x18019dcb6`: `AlternateServiceStackDLLPath`
- `0x18019dc5d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18019e09b`: `DeploymentSessionWrapper: Sandbox path [%s]`
- `0x18019e1a1`: `DeploymentSessionWrapper: This version of UpdateAgent doesn't support Recovery on UUP.`

## pseudocode

```c
__int64 __fastcall CDeploymentSessionWrapper::PostDownload(
        CDeploymentSessionWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v7; // r15
  HMODULE v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // esi
  int v12; // eax
  __int64 v13; // rcx
  DWORD FileAttributesW; // edi
  int v15; // edi
  int v16; // eax
  __int64 v17; // rdi
  DWORD v18; // edi
  int v19; // edi
  LSTATUS v20; // edi
  int StringCch; // eax
  int Internal; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  int FinalPath; // eax
  __int64 v29; // rdi
  __int64 v30; // rcx
  int v31; // eax
  int v32; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v34; // rax
  DWORD v35; // eax
  BOOL v36; // edi
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rdi
  signed int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rsi
  int v43; // eax
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  int v47; // eax
  HANDLE v48; // rax
  WCHAR *v49; // rbx
  HANDLE v50; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  GUID v56; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int128 v58; // [rsp+78h] [rbp-88h]
  __int128 v59; // [rsp+88h] [rbp-78h]
  __int128 v60; // [rsp+98h] [rbp-68h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpLibFileName; // [rsp+B0h] [rbp-50h] BYREF
  DWORD Type; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-38h]
  DWORD cbData[4]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[1024]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&v56.Data1 = a3;
  lpFileName = 0;
  lpLibFileName = 0;
  v65 = 0;
  v64 = 0;
  v61 = 0;
  v7 = 0;
  v8 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  if ( !a2 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024809;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 282;
LABEL_4:
      v13 = v9;
      goto LABEL_101;
    }
    goto LABEL_103;
  }
  if ( !a4 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024809;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 283;
      goto LABEL_4;
    }
LABEL_103:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
    goto LABEL_104;
  }
  FileAttributesW = GetFileAttributesW(a4);
  if ( FileAttributesW == -1 )
    v15 = 0;
  else
    v15 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v15 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024893;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942403LL);
      LODWORD(lpcbData) = -2147024893;
      LODWORD(phkResult) = 288;
      goto LABEL_4;
    }
    goto LABEL_103;
  }
  v16 = CMiscHelpersT<CEmptyType>::CombinePath(a4, L"metadata", 0, &lpFileName);
  v11 = v16;
  if ( v16 < 0 )
  {
    v17 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, (unsigned int)v16);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 292;
    goto LABEL_100;
  }
  v18 = GetFileAttributesW(lpFileName);
  if ( v18 == -1 )
    v19 = 0;
  else
    v19 = (v18 >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v19 )
  {
    v9 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024893;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, 2147942403LL);
      LODWORD(lpcbData) = -2147024893;
      LODWORD(phkResult) = 294;
      goto LABEL_4;
    }
    goto LABEL_103;
  }
  if ( *(_QWORD *)&v56.Data1 )
    goto LABEL_36;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_36;
  }
  Type = 0;
  memset_0(Data, 0, sizeof(Data));
  cbData[0] = 1024;
  v20 = RegQueryValueExW(hKey, L"AlternateServiceStackDLLPath", 0, &Type, Data, cbData);
  RegCloseKey(hKey);
  if ( v20 || Type != 1 )
    goto LABEL_36;
  v54 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Data, &v54);
  v11 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Data);
    v11 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v7 = lpLibFileName;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( (v11 & 0x80000000) != 0 )
  {
    v17 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, v11);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 315;
    goto LABEL_100;
  }
  if ( !v7 )
  {
LABEL_36:
    v23 = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"UpdateAgent.dll", 0, &lpLibFileName);
    v11 = v23;
    if ( v23 < 0 )
    {
      v24 = *(_QWORD *)this;
      v25 = 0;
      if ( *(_QWORD *)this )
      {
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v24 + 32LL))(*(_QWORD *)this, (unsigned int)v23);
        LODWORD(lpcbData) = v11;
        LODWORD(phkResult) = 324;
        v27 = CFCLogLiteT<CEmptyType>::LogFormat(
                v24,
                4 - (unsigned int)(v26 != 0),
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSessionWrapper::PostDownload",
                phkResult,
                lpcbData);
        v25 = (unsigned int)v27;
        if ( v27 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v27);
      }
      goto LABEL_40;
    }
    v7 = lpLibFileName;
  }
  lpLibFileName = 0;
  FinalPath = CMiscHelpersT<CEmptyType>::GetFinalPath(v7);
  v11 = FinalPath;
  if ( FinalPath < 0 )
  {
    v29 = *(_QWORD *)this;
    v30 = 0;
    if ( *(_QWORD *)this )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v29 + 32LL))(
              *(_QWORD *)this,
              (unsigned int)FinalPath);
      LODWORD(lpcbData) = v11;
      LODWORD(phkResult) = 331;
      v32 = CFCLogLiteT<CEmptyType>::LogFormat(
              v29,
              4 - (unsigned int)(v31 != 0),
              L"%s(%d): Result = 0x%X",
              L"CDeploymentSessionWrapper::PostDownload",
              phkResult,
              lpcbData);
      v30 = (unsigned int)v32;
      if ( v32 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v30);
    if ( !v7 )
      goto LABEL_41;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
    v25 = 0;
LABEL_40:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v25);
LABEL_41:
    v7 = lpLibFileName;
    goto LABEL_104;
  }
  if ( v7 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v7 = lpLibFileName;
  v35 = GetFileAttributesW(lpLibFileName);
  v36 = v35 != -1 && (v35 & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v36 )
  {
    v17 = *(_QWORD *)this;
    v10 = 0;
    v11 = -2147024894;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, 2147942402LL);
    LODWORD(lpcbData) = -2147024894;
    LODWORD(phkResult) = 334;
    goto LABEL_100;
  }
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(
      *(_QWORD *)this,
      2,
      L"DeploymentSessionWrapper: Loading Update Agent from [%s]",
      v7);
  Library = LoadLibraryExW(v7, 0, 0);
  v8 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v10 = 0;
      if ( (v11 & 0x80000000) == 0 )
        goto LABEL_103;
    }
    else
    {
      v11 = -2147467259;
      v10 = 0;
    }
    v17 = *(_QWORD *)this;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, v11);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 338;
LABEL_100:
    v13 = v17;
LABEL_101:
    v47 = CFCLogLiteT<CEmptyType>::LogFormat(
            v13,
            4 - (unsigned int)(v12 != 0),
            L"%s(%d): Result = 0x%X",
            L"CDeploymentSessionWrapper::PostDownload",
            phkResult,
            lpcbData);
    v10 = (unsigned int)v47;
    if ( v47 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v47);
    goto LABEL_103;
  }
  ProcAddress = GetProcAddress(Library, "CreateOfflineDeploymentSession");
  if ( !ProcAddress )
  {
    v40 = GetLastError();
    v11 = v40;
    if ( v40 )
    {
      if ( v40 > 0 )
        v11 = (unsigned __int16)v40 | 0x80070000;
      v10 = 0;
      if ( (v11 & 0x80000000) == 0 )
        goto LABEL_103;
    }
    else
    {
      v11 = -2147467259;
      v10 = 0;
    }
    v17 = *(_QWORD *)this;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, v11);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 341;
    goto LABEL_100;
  }
  v41 = *(_QWORD *)this;
  v61 = 0;
  v58 = (unsigned __int64)a2;
  v59 = 0;
  v60 = 0;
  if ( v41 )
    CFCLogLiteT<CEmptyType>::LogFormat(v41, 2, L"DeploymentSessionWrapper: Creating Deployment Session object");
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Session Version [%d]", 1);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Sandbox path [%s]", a4);
  v42 = *(_QWORD *)&v56.Data1;
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(
      *(_QWORD *)this,
      2,
      L"DeploymentSessionWrapper: Offline windir [%s]",
      *(_QWORD *)&v56.Data1);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Info2version [%d]", 2);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Session data [%s]", (_QWORD)v58);
  phkResult = (PHKEY)&v56;
  v56 = GUID_NULL;
  v43 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, __int64))ProcAddress)(1, a4, v42);
  v11 = v43;
  if ( v43 < 0 )
  {
    v17 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, (unsigned int)v43);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 362;
    goto LABEL_100;
  }
  v44 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v65)(
          v65,
          &GUID_36fb071a_6dc5_48bf_a6f3_d4f6751d39dc,
          &v64);
  v45 = *(_QWORD *)this;
  v11 = v44;
  if ( v44 < 0 )
  {
    if ( v45 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        v45,
        4,
        L"DeploymentSessionWrapper: This version of UpdateAgent doesn't support Recovery on UUP.");
    v17 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, v11);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 369;
    goto LABEL_100;
  }
  if ( v45 )
    CFCLogLiteT<CEmptyType>::LogFormat(
      v45,
      2,
      L"DeploymentSessionWrapper: Calling PostDownload on Deployment Session object, to perform expand.");
  v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 88LL))(v64);
  v11 = v46;
  if ( v46 < 0 )
  {
    v17 = *(_QWORD *)this;
    v10 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_103;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v17 + 32LL))(*(_QWORD *)this, (unsigned int)v46);
    LODWORD(lpcbData) = v11;
    LODWORD(phkResult) = 372;
    goto LABEL_100;
  }
LABEL_104:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v8 )
    FreeLibrary(v8);
  if ( v7 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpFileName )
  {
    v49 = (WCHAR *)(lpFileName - 2);
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v11;
}

```

## disassembly

```asm
0x18019da38  push    rbp
0x18019da3a  push    rbx
0x18019da3b  push    rsi
0x18019da3c  push    rdi
0x18019da3d  push    r12
0x18019da3f  push    r13
0x18019da41  push    r14
0x18019da43  push    r15
0x18019da45  lea     rbp, [rsp-3F8h]
0x18019da4d  sub     rsp, 4F8h
0x18019da54  mov     rax, cs:__security_cookie
0x18019da5b  xor     rax, rsp
0x18019da5e  mov     [rbp+430h+var_50], rax
0x18019da65  xor     esi, esi
0x18019da67  mov     qword ptr [rsp+530h+var_4D0], r8
0x18019da6c  xorps   xmm0, xmm0
0x18019da6f  mov     [rsp+530h+lpFileName], rsi
0x18019da74  xor     eax, eax
0x18019da76  mov     [rbp+430h+lpLibFileName], rsi
0x18019da7a  mov     [rbp+430h+var_468], rsi
0x18019da7e  mov     r12, r9
0x18019da81  mov     [rbp+430h+var_470], rsi
0x18019da85  mov     r13, rdx
0x18019da88  mov     [rbp+430h+var_488], rax
0x18019da8c  mov     r14, rcx
0x18019da8f  mov     r15d, esi
0x18019da92  mov     ebx, esi
0x18019da94  movups  [rsp+530h+var_4B8], xmm0
0x18019da99  movups  [rbp+430h+var_4A8], xmm0
0x18019da9d  movups  [rbp+430h+var_498], xmm0
0x18019daa1  test    rdx, rdx
0x18019daa4  jnz     short loc_18019DAE0
0x18019daa6  mov     r14, [r14]
0x18019daa9  xor     ecx, ecx
0x18019daab  mov     edi, 80070057h
0x18019dab0  mov     esi, edi
0x18019dab2  test    r14, r14
0x18019dab5  jz      loc_18019E258
0x18019dabb  mov     rax, [r14]
0x18019dabe  mov     edx, edi
0x18019dac0  mov     rcx, r14
0x18019dac3  mov     rax, [rax+20h]
0x18019dac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dacc  mov     dword ptr [rsp+530h+lpcbData], edi
0x18019dad0  mov     dword ptr [rsp+530h+phkResult], 11Ah
0x18019dad8  mov     rcx, r14
0x18019dadb  jmp     loc_18019E233
0x18019dae0  test    r12, r12
0x18019dae3  jnz     short loc_18019DB19
0x18019dae5  mov     r14, [r14]
0x18019dae8  xor     ecx, ecx
0x18019daea  mov     edi, 80070057h
0x18019daef  mov     esi, edi
0x18019daf1  test    r14, r14
0x18019daf4  jz      loc_18019E258
0x18019dafa  mov     rax, [r14]
0x18019dafd  mov     edx, edi
0x18019daff  mov     rcx, r14
0x18019db02  mov     rax, [rax+20h]
0x18019db06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019db0b  mov     dword ptr [rsp+530h+lpcbData], edi
0x18019db0f  mov     dword ptr [rsp+530h+phkResult], 11Bh
0x18019db17  jmp     short loc_18019DAD8
0x18019db19  mov     rcx, r12; lpFileName
0x18019db1c  call    cs:__imp_GetFileAttributesW
0x18019db23  nop     dword ptr [rax+rax+00h]
0x18019db28  mov     edi, eax
0x18019db2a  cmp     eax, 0FFFFFFFFh
0x18019db2d  jz      short loc_18019DB37
0x18019db2f  shr     edi, 4
0x18019db32  and     edi, 1
0x18019db35  jmp     short loc_18019DB39
0x18019db37  mov     edi, esi
0x18019db39  xor     ecx, ecx
0x18019db3b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019db40  xor     ecx, ecx
0x18019db42  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019db47  test    edi, edi
0x18019db49  jnz     short loc_18019DB82
0x18019db4b  mov     r14, [r14]
0x18019db4e  xor     ecx, ecx
0x18019db50  mov     edi, 80070003h
0x18019db55  mov     esi, edi
0x18019db57  test    r14, r14
0x18019db5a  jz      loc_18019E258
0x18019db60  mov     rax, [r14]
0x18019db63  mov     edx, edi
0x18019db65  mov     rcx, r14
0x18019db68  mov     rax, [rax+20h]
0x18019db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019db71  mov     dword ptr [rsp+530h+lpcbData], edi
0x18019db75  mov     dword ptr [rsp+530h+phkResult], 120h
0x18019db7d  jmp     loc_18019DAD8
0x18019db82  lea     r9, [rsp+530h+lpFileName]
0x18019db87  xor     r8d, r8d
0x18019db8a  lea     rdx, aMetadata_1; "metadata"
0x18019db91  mov     rcx, r12
0x18019db94  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18019db99  mov     esi, eax
0x18019db9b  test    eax, eax
0x18019db9d  jns     short loc_18019DBCF
0x18019db9f  mov     rdi, [r14]
0x18019dba2  xor     ecx, ecx
0x18019dba4  test    rdi, rdi
0x18019dba7  jz      loc_18019E258
0x18019dbad  mov     rcx, [rdi]
0x18019dbb0  mov     edx, esi
0x18019dbb2  mov     rax, [rcx+20h]
0x18019dbb6  mov     rcx, rdi
0x18019dbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dbbe  mov     dword ptr [rsp+530h+lpcbData], esi
0x18019dbc2  mov     dword ptr [rsp+530h+phkResult], 124h
0x18019dbca  jmp     loc_18019E230
0x18019dbcf  mov     rcx, [rsp+530h+lpFileName]; lpFileName
0x18019dbd4  call    cs:__imp_GetFileAttributesW
0x18019dbdb  nop     dword ptr [rax+rax+00h]
0x18019dbe0  mov     edi, eax
0x18019dbe2  cmp     eax, 0FFFFFFFFh
0x18019dbe5  jz      short loc_18019DBEF
0x18019dbe7  shr     edi, 4
0x18019dbea  and     edi, 1
0x18019dbed  jmp     short loc_18019DBF1
0x18019dbef  xor     edi, edi
0x18019dbf1  xor     ecx, ecx
0x18019dbf3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019dbf8  xor     ecx, ecx
0x18019dbfa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019dbff  test    edi, edi
0x18019dc01  jnz     short loc_18019DC3A
0x18019dc03  mov     r14, [r14]
0x18019dc06  xor     ecx, ecx
0x18019dc08  mov     edi, 80070003h
0x18019dc0d  mov     esi, edi
0x18019dc0f  test    r14, r14
0x18019dc12  jz      loc_18019E258
0x18019dc18  mov     rax, [r14]
0x18019dc1b  mov     edx, edi
0x18019dc1d  mov     rcx, r14
0x18019dc20  mov     rax, [rax+20h]
0x18019dc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dc29  mov     dword ptr [rsp+530h+lpcbData], edi
0x18019dc2d  mov     dword ptr [rsp+530h+phkResult], 126h
0x18019dc35  jmp     loc_18019DAD8
0x18019dc3a  cmp     qword ptr [rsp+530h+var_4D0], rbx
0x18019dc3f  jnz     loc_18019DD71
0x18019dc45  lea     rax, [rsp+530h+hKey]
0x18019dc4a  mov     [rsp+530h+hKey], rbx
0x18019dc4f  mov     r9d, 20019h; samDesired
0x18019dc55  mov     [rsp+530h+phkResult], rax; phkResult
0x18019dc5a  xor     r8d, r8d; ulOptions
0x18019dc5d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18019dc64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019dc6b  call    cs:__imp_RegOpenKeyExW
0x18019dc72  nop     dword ptr [rax+rax+00h]
0x18019dc77  test    eax, eax
0x18019dc79  jnz     loc_18019DD71
0x18019dc7f  mov     edi, 400h
0x18019dc84  mov     [rbp+430h+Type], ebx
0x18019dc87  mov     r8d, edi; Size
0x18019dc8a  lea     rcx, [rbp+430h+Data]; void *
0x18019dc8e  xor     edx, edx; Val
0x18019dc90  call    memset_0
0x18019dc95  mov     rcx, [rsp+530h+hKey]; hKey
0x18019dc9a  lea     rax, [rbp+430h+cbData]
0x18019dc9e  mov     [rsp+530h+lpcbData], rax; lpcbData
0x18019dca3  lea     r9, [rbp+430h+Type]; lpType
0x18019dca7  lea     rax, [rbp+430h+Data]
0x18019dcab  mov     [rbp+430h+cbData], edi
0x18019dcae  xor     r8d, r8d; lpReserved
0x18019dcb1  mov     [rsp+530h+phkResult], rax; lpData
0x18019dcb6  lea     rdx, aAlternateservi; "AlternateServiceStackDLLPath"
0x18019dcbd  call    cs:__imp_RegQueryValueExW
0x18019dcc4  nop     dword ptr [rax+rax+00h]
0x18019dcc9  mov     rcx, [rsp+530h+hKey]; hKey
0x18019dcce  mov     edi, eax
0x18019dcd0  call    cs:__imp_RegCloseKey
0x18019dcd7  nop     dword ptr [rax+rax+00h]
0x18019dcdc  test    edi, edi
0x18019dcde  jnz     loc_18019DD71
0x18019dce4  cmp     [rbp+430h+Type], 1
0x18019dce8  jnz     loc_18019DD71
0x18019dcee  lea     rdx, [rsp+530h+var_4E0]
0x18019dcf3  mov     [rsp+530h+var_4E0], ebx
0x18019dcf7  lea     rcx, [rbp+430h+Data]
0x18019dcfb  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18019dd00  mov     esi, eax
0x18019dd02  test    eax, eax
0x18019dd04  jns     short loc_18019DD0F
0x18019dd06  mov     ecx, eax
0x18019dd08  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019dd0d  jmp     short loc_18019DD31
0x18019dd0f  mov     edx, [rsp+530h+var_4E0]
0x18019dd13  lea     r8, [rbp+430h+lpLibFileName]
0x18019dd17  lea     rcx, [rbp+430h+Data]; Src
0x18019dd1b  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18019dd20  mov     esi, eax
0x18019dd22  test    eax, eax
0x18019dd24  jns     short loc_18019DD2D
0x18019dd26  mov     ecx, eax
0x18019dd28  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019dd2d  mov     r15, [rbp+430h+lpLibFileName]
0x18019dd31  mov     ecx, esi
0x18019dd33  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019dd38  test    esi, esi
0x18019dd3a  jns     short loc_18019DD6C
0x18019dd3c  mov     rdi, [r14]
0x18019dd3f  xor     ecx, ecx
0x18019dd41  test    rdi, rdi
0x18019dd44  jz      loc_18019E258
0x18019dd4a  mov     rax, [rdi]
0x18019dd4d  mov     edx, esi
0x18019dd4f  mov     rcx, rdi
0x18019dd52  mov     rax, [rax+20h]
0x18019dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dd5b  mov     dword ptr [rsp+530h+lpcbData], esi
0x18019dd5f  mov     dword ptr [rsp+530h+phkResult], 13Bh
0x18019dd67  jmp     loc_18019E230
0x18019dd6c  test    r15, r15
0x18019dd6f  jnz     short loc_18019DDF0
0x18019dd71  mov     rcx, [rsp+530h+lpFileName]
0x18019dd76  lea     r9, [rbp+430h+lpLibFileName]
0x18019dd7a  xor     r8d, r8d
0x18019dd7d  lea     rdx, aUpdateagentDll; "UpdateAgent.dll"
0x18019dd84  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18019dd89  mov     esi, eax
0x18019dd8b  test    eax, eax
0x18019dd8d  jns     short loc_18019DDEC
0x18019dd8f  mov     rdi, [r14]
0x18019dd92  xor     ecx, ecx
0x18019dd94  test    rdi, rdi
0x18019dd97  jz      short loc_18019DDDE
0x18019dd99  mov     rax, [rdi]
0x18019dd9c  mov     edx, esi
0x18019dd9e  mov     rcx, rdi
0x18019dda1  mov     rax, [rax+20h]
0x18019dda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ddaa  neg     eax
0x18019ddac  mov     dword ptr [rsp+530h+lpcbData], esi
0x18019ddb0  lea     r9, aCdeploymentses_0; "CDeploymentSessionWrapper::PostDownload"
0x18019ddb7  mov     dword ptr [rsp+530h+phkResult], 144h
0x18019ddbf  sbb     edx, edx
0x18019ddc1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18019ddc8  add     edx, 4
0x18019ddcb  mov     rcx, rdi
0x18019ddce  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019ddd3  mov     ecx, eax
0x18019ddd5  test    eax, eax
0x18019ddd7  jns     short loc_18019DDDE
0x18019ddd9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019ddde  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019dde3  mov     r15, [rbp+430h+lpLibFileName]
0x18019dde7  jmp     loc_18019E25D
0x18019ddec  mov     r15, [rbp+430h+lpLibFileName]
0x18019ddf0  lea     r8, [rbp+430h+lpLibFileName]
0x18019ddf4  mov     [rbp+430h+lpLibFileName], rbx
0x18019ddf8  mov     rcx, r15; lpFileName
0x18019ddfb  call    ?GetFinalPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGKPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetFinalPath(ushort const *,ulong,ushort * *)
0x18019de00  mov     esi, eax
0x18019de02  test    eax, eax
0x18019de04  jns     loc_18019DE8B
0x18019de0a  mov     rdi, [r14]
0x18019de0d  xor     ecx, ecx
0x18019de0f  test    rdi, rdi
0x18019de12  jz      short loc_18019DE59
0x18019de14  mov     rax, [rdi]
0x18019de17  mov     edx, esi
0x18019de19  mov     rcx, rdi
0x18019de1c  mov     rax, [rax+20h]
0x18019de20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de25  neg     eax
0x18019de27  mov     dword ptr [rsp+530h+lpcbData], esi
0x18019de2b  lea     r9, aCdeploymentses_0; "CDeploymentSessionWrapper::PostDownload"
0x18019de32  mov     dword ptr [rsp+530h+phkResult], 14Bh
0x18019de3a  sbb     edx, edx
0x18019de3c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18019de43  add     edx, 4
0x18019de46  mov     rcx, rdi
0x18019de49  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019de4e  mov     ecx, eax
0x18019de50  test    eax, eax
0x18019de52  jns     short loc_18019DE59
0x18019de54  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019de59  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019de5e  test    r15, r15
0x18019de61  jz      short loc_18019DDE3
0x18019de63  call    cs:__imp_GetProcessHeap
0x18019de6a  nop     dword ptr [rax+rax+00h]
0x18019de6f  lea     r8, [r15-4]; lpMem
0x18019de73  xor     edx, edx; dwFlags
0x18019de75  mov     rcx, rax; hHeap
0x18019de78  call    cs:__imp_HeapFree
0x18019de7f  nop     dword ptr [rax+rax+00h]
0x18019de84  xor     ecx, ecx
0x18019de86  jmp     loc_18019DDDE
0x18019de8b  test    r15, r15
0x18019de8e  jz      short loc_18019DEB8
0x18019de90  call    cs:__imp_GetProcessHeap
0x18019de97  nop     dword ptr [rax+rax+00h]
0x18019de9c  lea     r8, [r15-4]; lpMem
0x18019dea0  xor     edx, edx; dwFlags
  ... truncated ...
```
