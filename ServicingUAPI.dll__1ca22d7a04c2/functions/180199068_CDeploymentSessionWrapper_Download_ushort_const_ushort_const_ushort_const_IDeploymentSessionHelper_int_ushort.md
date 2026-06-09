# CDeploymentSessionWrapper::Download(ushort const *,ushort const *,ushort const *,IDeploymentSessionHelper *,int,ushort * *)

- ea: `0x180199068`
- end: `0x180199df0`
- name: `?Download@CDeploymentSessionWrapper@@QEAAJPEBG00PEAVIDeploymentSessionHelper@@HPEAPEAG@Z`
- size: `3464`
- prototype: `__int64 __usercall@<rax>(CDeploymentSessionWrapper *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct IDeploymentSessionHelper *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180199e00`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x180068c4c`
- `0x18006fab0`
- `0x180071994`
- `0x1801961c4`
- `0x180197644`
- `0x180198e84`
- `0x180199068`
- `0x18019bb68`
- `0x18019cb24`
- `0x18019e940`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019930f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801997c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019930f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801997c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199846`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180199832`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180199832`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180199d5c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180199d5c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801997b3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801997b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019963e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019966b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801999fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199cea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199db7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019963e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019966b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801999fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199cea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180199db7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199629`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801999e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199cd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199da3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199629`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801999e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199cd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199da3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180199212`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801992cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180199685`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180199212`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801992cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180199685`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801992ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801992ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180199433`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180199433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180199496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180199496`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180199484`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180199484`

## string_xrefs

- `0x180199543`: `UpdateAgent.dll`
- `0x180199a20`: `ActionList.xml`
- `0x18019979c`: `DeploymentSessionWrapper: Loading Update Agent from [%s]`
- `0x180199745`: `DeploymentSessionWrapper: UpdateAgent.dll signature is not trusted.`
- `0x180199828`: `CreateOfflineDeploymentSession`
- `0x18019947d`: `AlternateServiceStackDLLPath`
- `0x180199425`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180199a4e`: `DeploymentSessionWrapper: ActionList path: [%s]`
- `0x180199903`: `DeploymentSessionWrapper: Sandbox path [%s]`

## pseudocode

```c
__int64 __fastcall CDeploymentSessionWrapper::Download(
        CDeploymentSessionWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IDeploymentSessionHelper *a5,
        int a6,
        unsigned __int16 **a7)
{
  unsigned __int64 v9; // rcx
  const WCHAR *v11; // r13
  HMODULE v12; // rbx
  __int64 v13; // r14
  signed int v14; // esi
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  DWORD FileAttributesW; // edi
  int v19; // edi
  __int64 v20; // rdi
  int v21; // eax
  const WCHAR *v22; // rsi
  DWORD v23; // edi
  int v24; // edi
  signed int LastError; // eax
  struct IDeploymentSessionHelper *v26; // rdi
  int v27; // eax
  int v28; // eax
  LSTATUS v29; // edi
  int StringCch; // eax
  int Internal; // eax
  int v32; // eax
  __int64 v33; // rdi
  __int64 v34; // rcx
  int v35; // eax
  int v36; // eax
  int FinalPath; // eax
  __int64 v38; // rdi
  __int64 v39; // rcx
  int v40; // eax
  int v41; // eax
  HANDLE v42; // rax
  HANDLE ProcessHeap; // rax
  DWORD v44; // eax
  BOOL v45; // edi
  int v46; // eax
  HMODULE Library; // rax
  signed int v48; // eax
  FARPROC ProcAddress; // rdi
  signed int v50; // eax
  __int64 v51; // rcx
  const unsigned __int16 *v52; // rsi
  int v53; // eax
  unsigned __int16 *v54; // rdi
  HANDLE v55; // rax
  int v56; // eax
  __int64 v57; // rcx
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  unsigned __int16 *v62; // rdx
  __int64 v63; // rdi
  __int64 v64; // rcx
  int v65; // eax
  int v66; // eax
  unsigned __int16 *v67; // rdi
  HANDLE v68; // rax
  HANDLE v69; // rax
  WCHAR *v70; // rbx
  HANDLE v71; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  int v75; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v77; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v79; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v80; // [rsp+70h] [rbp-90h]
  struct IDeploymentSessionHelper *v81; // [rsp+78h] [rbp-88h]
  GUID v82; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 **v83; // [rsp+90h] [rbp-70h]
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  __int128 v85; // [rsp+A0h] [rbp-60h]
  __int128 v86; // [rsp+B0h] [rbp-50h]
  __int128 v87; // [rsp+C0h] [rbp-40h]
  __int64 v88; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpLibFileName; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v90; // [rsp+E0h] [rbp-20h] BYREF
  struct IDeploymentDownloadRequest *v91; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v92; // [rsp+F0h] [rbp-10h] BYREF
  DWORD Type; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v94; // [rsp+100h] [rbp+0h]
  DWORD cbData; // [rsp+108h] [rbp+8h] BYREF
  BYTE Data[1024]; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)&v82.Data1 = a2;
  v80 = a4;
  lpFileName = 0;
  lpLibFileName = 0;
  v94 = 0;
  v9 = (unsigned __int64)a5;
  v81 = a5;
  v11 = 0;
  v83 = a7;
  v12 = 0;
  v88 = 0;
  v91 = 0;
  v92 = 0;
  v90 = 0;
  v76 = 0;
  v77 = 0;
  v79 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  if ( !a2 )
  {
    v13 = *(_QWORD *)this;
    v9 = 0;
    v14 = -2147024809;
    if ( v13 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 106;
LABEL_4:
      v16 = v13;
LABEL_5:
      v17 = CFCLogLiteT<CEmptyType>::LogFormat(
              v16,
              4 - (unsigned int)(v15 != 0),
              L"%s(%d): Result = 0x%X",
              L"CDeploymentSessionWrapper::Download",
              phkResult,
              lpcbData);
      v9 = (unsigned int)v17;
      if ( v17 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  if ( !a3 )
  {
    v13 = *(_QWORD *)this;
    v9 = 0;
    v14 = -2147024809;
    if ( v13 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 107;
      goto LABEL_4;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    goto LABEL_161;
  }
  if ( !a5 )
  {
    v13 = *(_QWORD *)this;
    v14 = -2147024809;
    if ( v13 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 108;
      goto LABEL_4;
    }
    goto LABEL_7;
  }
  if ( !a7 )
  {
    v13 = *(_QWORD *)this;
    v9 = 0;
    v14 = -2147024809;
    if ( v13 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, 2147942487LL);
      LODWORD(lpcbData) = -2147024809;
      LODWORD(phkResult) = 109;
      goto LABEL_4;
    }
    goto LABEL_7;
  }
  FileAttributesW = GetFileAttributesW(a3);
  if ( FileAttributesW == -1 )
    v19 = 0;
  else
    v19 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v19 )
  {
    v20 = *(_QWORD *)this;
    v9 = 0;
    v14 = -2147024893;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, 2147942403LL);
      LODWORD(lpcbData) = -2147024893;
      LODWORD(phkResult) = 114;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  v21 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"metadata", 0, &lpFileName);
  v14 = v21;
  if ( v21 < 0 )
  {
    v20 = *(_QWORD *)this;
    v9 = 0;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v21);
      LODWORD(lpcbData) = v14;
      LODWORD(phkResult) = 118;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  v22 = lpFileName;
  v23 = GetFileAttributesW(lpFileName);
  if ( v23 == -1 )
    v24 = 0;
  else
    v24 = (v23 >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v24 && !CreateDirectoryW(v22, 0) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      v9 = 0;
      if ( v14 >= 0 )
        goto LABEL_7;
    }
    else
    {
      v14 = -2147467259;
      v9 = 0;
    }
    v20 = *(_QWORD *)this;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v14);
      LODWORD(lpcbData) = v14;
      LODWORD(phkResult) = 122;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  v26 = v81;
  v27 = (**(__int64 (__fastcall ***)(struct IDeploymentSessionHelper *, const WCHAR *))v81)(v81, v22);
  v14 = v27;
  if ( v27 < 0 )
  {
    v20 = *(_QWORD *)this;
    v9 = 0;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v27);
      LODWORD(lpcbData) = v14;
      LODWORD(phkResult) = 127;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  v28 = (*(__int64 (__fastcall **)(struct IDeploymentSessionHelper *, LPCWSTR))(*(_QWORD *)v26 + 8LL))(v26, lpFileName);
  v14 = v28;
  if ( v28 < 0 )
  {
    v20 = *(_QWORD *)this;
    v9 = 0;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v28);
      LODWORD(lpcbData) = v14;
      LODWORD(phkResult) = 129;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  if ( a4 )
    goto LABEL_58;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_58;
  }
  Type = 0;
  memset_0(Data, 0, sizeof(Data));
  cbData = 1024;
  v29 = RegQueryValueExW(hKey, L"AlternateServiceStackDLLPath", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( v29 || Type != 1 )
    goto LABEL_58;
  v75 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Data, &v75);
  v14 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Data);
    v14 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v11 = lpLibFileName;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
  if ( v14 < 0 )
  {
    v20 = *(_QWORD *)this;
    v9 = 0;
    if ( *(_QWORD *)this )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v14);
      LODWORD(lpcbData) = v14;
      LODWORD(phkResult) = 151;
      goto LABEL_23;
    }
    goto LABEL_7;
  }
  if ( !v11 )
  {
LABEL_58:
    v32 = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"UpdateAgent.dll", 0, &lpLibFileName);
    v14 = v32;
    if ( v32 < 0 )
    {
      v33 = *(_QWORD *)this;
      v34 = 0;
      if ( *(_QWORD *)this )
      {
        v35 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v33 + 32LL))(*(_QWORD *)this, (unsigned int)v32);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 160;
        v36 = CFCLogLiteT<CEmptyType>::LogFormat(
                v33,
                4 - (unsigned int)(v35 != 0),
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSessionWrapper::Download",
                phkResult,
                lpcbData);
        v34 = (unsigned int)v36;
        if ( v36 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v36);
      }
      goto LABEL_62;
    }
    v11 = lpLibFileName;
  }
  lpLibFileName = 0;
  FinalPath = CMiscHelpersT<CEmptyType>::GetFinalPath(v11);
  v14 = FinalPath;
  if ( FinalPath >= 0 )
  {
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v11 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    v11 = lpLibFileName;
    v44 = GetFileAttributesW(lpLibFileName);
    v45 = v44 != -1 && (v44 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v45 )
    {
      v20 = *(_QWORD *)this;
      v9 = 0;
      v14 = -2147024894;
      if ( *(_QWORD *)this )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, 2147942402LL);
        LODWORD(lpcbData) = -2147024894;
        LODWORD(phkResult) = 170;
        goto LABEL_23;
      }
      goto LABEL_7;
    }
    if ( !a4 )
    {
      v46 = VerifyFileSignature(v11, &v76);
      v14 = v46;
      if ( v46 < 0 )
      {
        v20 = *(_QWORD *)this;
        v9 = 0;
        if ( *(_QWORD *)this )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v46);
          LODWORD(lpcbData) = v14;
          LODWORD(phkResult) = 176;
          goto LABEL_23;
        }
        goto LABEL_7;
      }
      if ( !v76 )
      {
        if ( *(_QWORD *)this )
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            2,
            L"DeploymentSessionWrapper: UpdateAgent.dll signature is not trusted.");
        v20 = *(_QWORD *)this;
        v9 = 0;
        v14 = -2147024210;
        if ( *(_QWORD *)this )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, 2147943086LL);
          LODWORD(lpcbData) = -2147024210;
          LODWORD(phkResult) = 180;
          goto LABEL_23;
        }
        goto LABEL_7;
      }
    }
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(
        *(_QWORD *)this,
        2,
        L"DeploymentSessionWrapper: Loading Update Agent from [%s]",
        v11);
    Library = LoadLibraryExW(v11, 0, 0);
    v12 = Library;
    if ( !Library )
    {
      v48 = GetLastError();
      v14 = v48;
      if ( v48 )
      {
        if ( v48 > 0 )
          v14 = (unsigned __int16)v48 | 0x80070000;
        v9 = 0;
        if ( v14 >= 0 )
          goto LABEL_7;
      }
      else
      {
        v14 = -2147467259;
        v9 = 0;
      }
      v20 = *(_QWORD *)this;
      if ( *(_QWORD *)this )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v14);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 186;
        goto LABEL_23;
      }
      goto LABEL_7;
    }
    ProcAddress = GetProcAddress(Library, "CreateOfflineDeploymentSession");
    if ( !ProcAddress )
    {
      v50 = GetLastError();
      v14 = v50;
      if ( v50 )
      {
        if ( v50 > 0 )
          v14 = (unsigned __int16)v50 | 0x80070000;
        v9 = 0;
        if ( v14 >= 0 )
          goto LABEL_7;
      }
      else
      {
        v14 = -2147467259;
        v9 = 0;
      }
      v20 = *(_QWORD *)this;
      if ( *(_QWORD *)this )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v14);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 189;
        goto LABEL_23;
      }
      goto LABEL_7;
    }
    v51 = *(_QWORD *)this;
    v88 = 0;
    v85 = *(unsigned __int64 *)&v82.Data1;
    v86 = 0;
    v87 = 0;
    if ( v51 )
      CFCLogLiteT<CEmptyType>::LogFormat(v51, 2, L"DeploymentSessionWrapper: Creating Deployment Session object");
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Session Version [%d]", 1);
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Sandbox path [%s]", a3);
    v52 = v80;
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Offline windir [%s]", v80);
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Info2version [%d]", 2);
    if ( *(_QWORD *)this )
      CFCLogLiteT<CEmptyType>::LogFormat(
        *(_QWORD *)this,
        2,
        L"DeploymentSessionWrapper: Session data [%s]",
        (_QWORD)v85);
    phkResult = (PHKEY)&v82;
    v82 = GUID_NULL;
    v53 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(1, a3, v52);
    v14 = v53;
    if ( v53 < 0 )
    {
      v20 = *(_QWORD *)this;
      v9 = 0;
      if ( *(_QWORD *)this )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v53);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 209;
        goto LABEL_23;
      }
      goto LABEL_7;
    }
    v54 = v77;
    while ( 1 )
    {
      if ( v54 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, v54 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v79 = 0;
      }
      v56 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"ActionList.xml", 0, &v79);
      v14 = v56;
      if ( v56 < 0 )
      {
        v63 = *(_QWORD *)this;
        v64 = 0;
        if ( *(_QWORD *)this )
        {
          v65 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v63 + 32LL))(*(_QWORD *)this, (unsigned int)v56);
          LODWORD(lpcbData) = v14;
          LODWORD(phkResult) = 219;
          v66 = CFCLogLiteT<CEmptyType>::LogFormat(
                  v63,
                  4 - (unsigned int)(v65 != 0),
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSessionWrapper::Download",
                  phkResult,
                  lpcbData);
          v64 = (unsigned int)v66;
          if ( v66 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v66);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v64);
        v62 = v79;
        goto LABEL_160;
      }
      v57 = *(_QWORD *)this;
      v54 = v79;
      v77 = v79;
      if ( v57 )
        CFCLogLiteT<CEmptyType>::LogFormat(v57, 2, L"DeploymentSessionWrapper: ActionList path: [%s]", v79);
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper: Calling GenerateDownloadRequest on Deployment Session object");
      if ( v91 )
      {
        (*(void (__fastcall **)(struct IDeploymentDownloadRequest *))(*(_QWORD *)v91 + 16LL))(v91);
        v91 = 0;
      }
      v58 = (*(__int64 (__fastcall **)(__int64, struct IDeploymentDownloadRequest **))(*(_QWORD *)v94 + 32LL))(
              v94,
              &v91);
      v14 = v58;
      if ( v58 == -1047526399 )
      {
        if ( *(_QWORD *)this )
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            2,
            L"DeploymentSessionWrapper: No packages to be downloaded");
        v14 = 0;
LABEL_155:
        v62 = 0;
        *v83 = v54;
LABEL_160:
        v77 = v62;
        goto LABEL_161;
      }
      if ( v58 < 0 )
        break;
      if ( v92 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        v92 = 0;
      }
      v59 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)v91 + 40LL))(
              v91,
              &v92);
      v14 = v59;
      if ( v59 < 0 )
      {
        v20 = *(_QWORD *)this;
        v9 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_7;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v59);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 235;
        goto LABEL_23;
      }
      v60 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v92 + 24LL))(v92, &v90);
      v14 = v60;
      if ( v60 < 0 )
      {
        v20 = *(_QWORD *)this;
        v9 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_7;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v60);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 236;
        goto LABEL_23;
      }
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper: Download Request File Count = [%lu]",
          v90);
      if ( !v90 )
        goto LABEL_155;
      if ( a6 )
      {
        if ( *(_QWORD *)this )
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            2,
            L"DeploymentSessionWrapper: Skipping the request for payload files");
        goto LABEL_155;
      }
      v61 = CDeploymentSessionWrapper::RequestPayloadFiles(this, v91, v81, a3);
      v14 = v61;
      if ( v61 < 0 )
      {
        v20 = *(_QWORD *)this;
        v9 = 0;
        if ( !*(_QWORD *)this )
          goto LABEL_7;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v61);
        LODWORD(lpcbData) = v14;
        LODWORD(phkResult) = 248;
        goto LABEL_23;
      }
    }
    v20 = *(_QWORD *)this;
    v9 = 0;
    if ( !*(_QWORD *)this )
      goto LABEL_7;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(*(_QWORD *)this, (unsigned int)v58);
    LODWORD(lpcbData) = v14;
    LODWORD(phkResult) = 233;
LABEL_23:
    v16 = v20;
    goto LABEL_5;
  }
  v38 = *(_QWORD *)this;
  v39 = 0;
  if ( *(_QWORD *)this )
  {
    v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v38 + 32LL))(*(_QWORD *)this, (unsigned int)FinalPath);
    LODWORD(lpcbData) = v14;
    LODWORD(phkResult) = 167;
    v41 = CFCLogLiteT<CEmptyType>::LogFormat(
            v38,
            4 - (unsigned int)(v40 != 0),
            L"%s(%d): Result = 0x%X",
            L"CDeploymentSessionWrapper::Download",
            phkResult,
            lpcbData);
    v39 = (unsigned int)v41;
    if ( v41 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v41);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
  if ( v11 )
  {
    v42 = GetProcessHeap();
    HeapFree(v42, 0, (LPVOID)(v11 - 2));
    v34 = 0;
LABEL_62:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v34);
  }
  v11 = lpLibFileName;
LABEL_161:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
  if ( v77 )
  {
    v67 = v77 - 2;
    v68 = GetProcessHeap();
    HeapFree(v68, 0, v67);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v92 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    v92 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(struct IDeploymentDownloadRequest *))(*(_QWORD *)v91 + 16LL))(v91);
    v91 = 0;
  }
  if ( v94 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    v94 = 0;
  }
  if ( v12 )
    FreeLibrary(v12);
  if ( v11 )
  {
    v69 = GetProcessHeap();
    HeapFree(v69, 0, (LPVOID)(v11 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpFileName )
  {
    v70 = (WCHAR *)(lpFileName - 2);
    v71 = GetProcessHeap();
    HeapFree(v71, 0, v70);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180199068  push    rbp
0x18019906a  push    rbx
0x18019906b  push    rsi
0x18019906c  push    rdi
0x18019906d  push    r12
0x18019906f  push    r13
0x180199071  push    r14
0x180199073  push    r15
0x180199075  lea     rbp, [rsp-428h]
0x18019907d  sub     rsp, 528h
0x180199084  mov     rax, cs:__security_cookie
0x18019908b  xor     rax, rsp
0x18019908e  mov     [rbp+460h+var_50], rax
0x180199095  xor     esi, esi
0x180199097  mov     qword ptr [rbp+460h+var_4E0], rdx
0x18019909b  xorps   xmm0, xmm0
0x18019909e  mov     [rsp+560h+var_4F0], r9
0x1801990a3  mov     rax, rdx
0x1801990a6  mov     [rsp+560h+lpFileName], rsi
0x1801990ab  xor     edx, edx
0x1801990ad  mov     [rbp+460h+lpLibFileName], rsi
0x1801990b1  mov     [rbp+460h+var_460], rsi
0x1801990b5  mov     r12, r8
0x1801990b8  mov     r8, [rbp+460h+arg_30]
0x1801990bf  mov     r14, rcx
0x1801990c2  mov     rcx, [rbp+460h+arg_20]
0x1801990c9  mov     r15, r9
0x1801990cc  mov     [rsp+560h+var_4E8], rcx
0x1801990d1  mov     r13d, esi
0x1801990d4  mov     [rbp+460h+var_4D0], r8
0x1801990d8  mov     ebx, esi
0x1801990da  mov     [rbp+460h+var_490], rdx
0x1801990de  mov     [rbp+460h+var_478], rsi
0x1801990e2  mov     [rbp+460h+var_470], rsi
0x1801990e6  mov     [rbp+460h+var_480], esi
0x1801990e9  mov     [rsp+560h+var_50C], esi
0x1801990ed  mov     [rsp+560h+var_508], rdx
0x1801990f2  mov     [rsp+560h+var_4F8], rdx
0x1801990f7  movups  [rbp+460h+var_4C0], xmm0
0x1801990fb  movups  [rbp+460h+var_4B0], xmm0
0x1801990ff  movups  [rbp+460h+var_4A0], xmm0
0x180199103  test    rax, rax
0x180199106  jnz     short loc_180199168
0x180199108  mov     r14, [r14]
0x18019910b  xor     ecx, ecx
0x18019910d  mov     edi, 80070057h
0x180199112  mov     esi, edi
0x180199114  test    r14, r14
0x180199117  jz      short loc_18019915E
0x180199119  mov     rax, [r14]
0x18019911c  mov     edx, edi
0x18019911e  mov     rcx, r14
0x180199121  mov     rax, [rax+20h]
0x180199125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019912a  mov     dword ptr [rsp+560h+lpcbData], edi
0x18019912e  mov     dword ptr [rsp+560h+phkResult], 6Ah ; 'j'
0x180199136  mov     rcx, r14
0x180199139  neg     eax
0x18019913b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180199142  lea     r9, aCdeploymentses; "CDeploymentSessionWrapper::Download"
0x180199149  sbb     edx, edx
0x18019914b  add     edx, 4
0x18019914e  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180199153  mov     ecx, eax
0x180199155  test    eax, eax
0x180199157  jns     short loc_18019915E
0x180199159  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019915e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180199163  jmp     loc_180199CC1
0x180199168  test    r12, r12
0x18019916b  jnz     short loc_18019919D
0x18019916d  mov     r14, [r14]
0x180199170  xor     ecx, ecx
0x180199172  mov     edi, 80070057h
0x180199177  mov     esi, edi
0x180199179  test    r14, r14
0x18019917c  jz      short loc_18019915E
0x18019917e  mov     rax, [r14]
0x180199181  mov     edx, edi
0x180199183  mov     rcx, r14
0x180199186  mov     rax, [rax+20h]
0x18019918a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019918f  mov     dword ptr [rsp+560h+lpcbData], edi
0x180199193  mov     dword ptr [rsp+560h+phkResult], 6Bh ; 'k'
0x18019919b  jmp     short loc_180199136
0x18019919d  test    rcx, rcx
0x1801991a0  jnz     short loc_1801991D3
0x1801991a2  mov     r14, [r14]
0x1801991a5  mov     edi, 80070057h
0x1801991aa  mov     esi, edi
0x1801991ac  test    r14, r14
0x1801991af  jz      short loc_18019915E
0x1801991b1  mov     rax, [r14]
0x1801991b4  mov     edx, edi
0x1801991b6  mov     rcx, r14
0x1801991b9  mov     rax, [rax+20h]
0x1801991bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801991c2  mov     dword ptr [rsp+560h+lpcbData], edi
0x1801991c6  mov     dword ptr [rsp+560h+phkResult], 6Ch ; 'l'
0x1801991ce  jmp     loc_180199136
0x1801991d3  test    r8, r8
0x1801991d6  jnz     short loc_18019920F
0x1801991d8  mov     r14, [r14]
0x1801991db  xor     ecx, ecx
0x1801991dd  mov     edi, 80070057h
0x1801991e2  mov     esi, edi
0x1801991e4  test    r14, r14
0x1801991e7  jz      loc_18019915E
0x1801991ed  mov     rax, [r14]
0x1801991f0  mov     edx, edi
0x1801991f2  mov     rcx, r14
0x1801991f5  mov     rax, [rax+20h]
0x1801991f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801991fe  mov     dword ptr [rsp+560h+lpcbData], edi
0x180199202  mov     dword ptr [rsp+560h+phkResult], 6Dh ; 'm'
0x18019920a  jmp     loc_180199136
0x18019920f  mov     rcx, r12; lpFileName
0x180199212  call    cs:__imp_GetFileAttributesW
0x180199219  nop     dword ptr [rax+rax+00h]
0x18019921e  mov     edi, eax
0x180199220  cmp     eax, 0FFFFFFFFh
0x180199223  jz      short loc_18019922D
0x180199225  shr     edi, 4
0x180199228  and     edi, 1
0x18019922b  jmp     short loc_18019922F
0x18019922d  mov     edi, esi
0x18019922f  xor     ecx, ecx
0x180199231  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180199236  xor     ecx, ecx
0x180199238  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019923d  test    edi, edi
0x18019923f  jnz     short loc_180199279
0x180199241  mov     rdi, [r14]
0x180199244  xor     ecx, ecx
0x180199246  mov     esi, 80070003h
0x18019924b  test    rdi, rdi
0x18019924e  jz      loc_18019915E
0x180199254  mov     rax, [rdi]
0x180199257  mov     edx, esi
0x180199259  mov     rcx, rdi
0x18019925c  mov     rax, [rax+20h]
0x180199260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199265  mov     dword ptr [rsp+560h+lpcbData], esi
0x180199269  mov     dword ptr [rsp+560h+phkResult], 72h ; 'r'
0x180199271  mov     rcx, rdi
0x180199274  jmp     loc_180199139
0x180199279  lea     r9, [rsp+560h+lpFileName]
0x18019927e  xor     r8d, r8d
0x180199281  lea     rdx, aMetadata_1; "metadata"
0x180199288  mov     rcx, r12
0x18019928b  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180199290  mov     esi, eax
0x180199292  test    eax, eax
0x180199294  jns     short loc_1801992C3
0x180199296  mov     rdi, [r14]
0x180199299  xor     ecx, ecx
0x18019929b  test    rdi, rdi
0x18019929e  jz      loc_18019915E
0x1801992a4  mov     rcx, [rdi]
0x1801992a7  mov     edx, esi
0x1801992a9  mov     rax, [rcx+20h]
0x1801992ad  mov     rcx, rdi
0x1801992b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801992b5  mov     dword ptr [rsp+560h+lpcbData], esi
0x1801992b9  mov     dword ptr [rsp+560h+phkResult], 76h ; 'v'
0x1801992c1  jmp     short loc_180199271
0x1801992c3  mov     rsi, [rsp+560h+lpFileName]
0x1801992c8  mov     rcx, rsi; lpFileName
0x1801992cb  call    cs:__imp_GetFileAttributesW
0x1801992d2  nop     dword ptr [rax+rax+00h]
0x1801992d7  mov     edi, eax
0x1801992d9  cmp     eax, 0FFFFFFFFh
0x1801992dc  jz      short loc_1801992E6
0x1801992de  shr     edi, 4
0x1801992e1  and     edi, 1
0x1801992e4  jmp     short loc_1801992E8
0x1801992e6  xor     edi, edi
0x1801992e8  xor     ecx, ecx
0x1801992ea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801992ef  xor     ecx, ecx
0x1801992f1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801992f6  test    edi, edi
0x1801992f8  jnz     short loc_180199370
0x1801992fa  xor     edx, edx; lpSecurityAttributes
0x1801992fc  mov     rcx, rsi; lpPathName
0x1801992ff  call    cs:__imp_CreateDirectoryW
0x180199306  nop     dword ptr [rax+rax+00h]
0x18019930b  test    eax, eax
0x18019930d  jnz     short loc_180199370
0x18019930f  call    cs:__imp_GetLastError
0x180199316  nop     dword ptr [rax+rax+00h]
0x18019931b  mov     esi, eax
0x18019931d  test    eax, eax
0x18019931f  jnz     short loc_18019932A
0x180199321  mov     esi, 80004005h
0x180199326  xor     ecx, ecx
0x180199328  jmp     short loc_18019933F
0x18019932a  jle     short loc_180199335
0x18019932c  movzx   esi, ax
0x18019932f  or      esi, 80070000h
0x180199335  xor     ecx, ecx
0x180199337  test    esi, esi
0x180199339  jns     loc_18019915E
0x18019933f  mov     rdi, [r14]
0x180199342  mov     r15d, esi
0x180199345  test    rdi, rdi
0x180199348  jz      loc_18019915E
0x18019934e  mov     rax, [rdi]
0x180199351  mov     edx, esi
0x180199353  mov     rcx, rdi
0x180199356  mov     rax, [rax+20h]
0x18019935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019935f  mov     dword ptr [rsp+560h+lpcbData], esi
0x180199363  mov     dword ptr [rsp+560h+phkResult], 7Ah ; 'z'
0x18019936b  jmp     loc_180199271
0x180199370  mov     rdi, [rsp+560h+var_4E8]
0x180199375  mov     rdx, rsi
0x180199378  mov     rcx, rdi
0x18019937b  mov     rax, [rdi]
0x18019937e  mov     rax, [rax]
0x180199381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199386  mov     esi, eax
0x180199388  test    eax, eax
0x18019938a  jns     short loc_1801993BC
0x18019938c  mov     rdi, [r14]
0x18019938f  xor     ecx, ecx
0x180199391  test    rdi, rdi
0x180199394  jz      loc_18019915E
0x18019939a  mov     rax, [rdi]
0x18019939d  mov     edx, esi
0x18019939f  mov     rcx, rdi
0x1801993a2  mov     rax, [rax+20h]
0x1801993a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801993ab  mov     dword ptr [rsp+560h+lpcbData], esi
0x1801993af  mov     dword ptr [rsp+560h+phkResult], 7Fh
0x1801993b7  jmp     loc_180199271
0x1801993bc  mov     rax, [rdi]
0x1801993bf  mov     rcx, rdi
0x1801993c2  mov     rdx, [rsp+560h+lpFileName]
0x1801993c7  mov     rax, [rax+8]
0x1801993cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801993d0  mov     esi, eax
0x1801993d2  test    eax, eax
0x1801993d4  jns     short loc_180199406
0x1801993d6  mov     rdi, [r14]
0x1801993d9  xor     ecx, ecx
0x1801993db  test    rdi, rdi
0x1801993de  jz      loc_18019915E
0x1801993e4  mov     rax, [rdi]
0x1801993e7  mov     edx, esi
0x1801993e9  mov     rcx, rdi
0x1801993ec  mov     rax, [rax+20h]
0x1801993f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801993f5  mov     dword ptr [rsp+560h+lpcbData], esi
0x1801993f9  mov     dword ptr [rsp+560h+phkResult], 81h
0x180199401  jmp     loc_180199271
0x180199406  test    r15, r15
0x180199409  jnz     loc_180199537
0x18019940f  lea     rax, [rbp+460h+hKey]
0x180199413  mov     [rbp+460h+hKey], rbx
0x180199417  mov     r9d, 20019h; samDesired
0x18019941d  mov     [rsp+560h+phkResult], rax; phkResult
0x180199422  xor     r8d, r8d; ulOptions
0x180199425  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18019942c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180199433  call    cs:__imp_RegOpenKeyExW
0x18019943a  nop     dword ptr [rax+rax+00h]
0x18019943f  test    eax, eax
0x180199441  jnz     loc_180199537
0x180199447  mov     edi, 400h
0x18019944c  mov     [rbp+460h+Type], ebx
0x18019944f  mov     r8d, edi; Size
0x180199452  lea     rcx, [rbp+460h+Data]; void *
0x180199456  xor     edx, edx; Val
0x180199458  call    memset_0
0x18019945d  mov     rcx, [rbp+460h+hKey]; hKey
0x180199461  lea     rax, [rbp+460h+cbData]
0x180199465  mov     [rsp+560h+lpcbData], rax; lpcbData
0x18019946a  lea     r9, [rbp+460h+Type]; lpType
0x18019946e  lea     rax, [rbp+460h+Data]
0x180199472  mov     [rbp+460h+cbData], edi
0x180199475  xor     r8d, r8d; lpReserved
0x180199478  mov     [rsp+560h+phkResult], rax; lpData
0x18019947d  lea     rdx, aAlternateservi; "AlternateServiceStackDLLPath"
0x180199484  call    cs:__imp_RegQueryValueExW
0x18019948b  nop     dword ptr [rax+rax+00h]
0x180199490  mov     rcx, [rbp+460h+hKey]; hKey
0x180199494  mov     edi, eax
0x180199496  call    cs:__imp_RegCloseKey
0x18019949d  nop     dword ptr [rax+rax+00h]
0x1801994a2  test    edi, edi
0x1801994a4  jnz     loc_180199537
0x1801994aa  cmp     [rbp+460h+Type], 1
0x1801994ae  jnz     loc_180199537
0x1801994b4  lea     rdx, [rsp+560h+var_510]
0x1801994b9  mov     [rsp+560h+var_510], ebx
0x1801994bd  lea     rcx, [rbp+460h+Data]
0x1801994c1  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1801994c6  mov     esi, eax
0x1801994c8  test    eax, eax
  ... truncated ...
```
