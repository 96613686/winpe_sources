# ModifyGameInputFiles

- ea: `0x140002ac0`
- end: `0x140003605`
- name: `ModifyGameInputFiles`
- size: `2885`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400028f8`

## callees

- `0x140001008`
- `0x140001e5c`
- `0x1400021f4`
- `0x140002798`
- `0x140002888`
- `0x140002ac0`
- `0x140007735`
- `0x140007750`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140002c8d`
- `ntdll!RtlAllocateHeap` at `0x140002e52`
- `ntdll!RtlAllocateHeap` at `0x140002fcf`
- `ntdll!RtlAllocateHeap` at `0x14000318e`
- `ntdll!RtlAllocateHeap` at `0x140003255`
- `ntdll!RtlAllocateHeap` at `0x140002c8d`
- `ntdll!RtlAllocateHeap` at `0x140002e52`
- `ntdll!RtlAllocateHeap` at `0x140002fcf`
- `ntdll!RtlAllocateHeap` at `0x14000318e`
- `ntdll!RtlAllocateHeap` at `0x140003255`
- `ntdll!swprintf_s` at `0x140003311`
- `ntdll!swprintf_s` at `0x140003337`
- `ntdll!swprintf_s` at `0x14000337b`
- `ntdll!swprintf_s` at `0x1400033b0`
- `ntdll!swprintf_s` at `0x140003450`
- `ntdll!swprintf_s` at `0x140003485`
- `ntdll!swprintf_s` at `0x140003311`
- `ntdll!swprintf_s` at `0x140003337`
- `ntdll!swprintf_s` at `0x14000337b`
- `ntdll!swprintf_s` at `0x1400033b0`
- `ntdll!swprintf_s` at `0x140003450`
- `ntdll!swprintf_s` at `0x140003485`
- `ntdll!VerSetConditionMask` at `0x140002b2d`
- `ntdll!VerSetConditionMask` at `0x140002b3e`
- `ntdll!VerSetConditionMask` at `0x140002b4f`
- `ntdll!VerSetConditionMask` at `0x140002b2d`
- `ntdll!VerSetConditionMask` at `0x140002b3e`
- `ntdll!VerSetConditionMask` at `0x140002b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ee3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003085`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140002f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003085`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140002bd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140002d1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140002bd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140002d1a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140002db5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140002ed9`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140002db5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140002ed9`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140002b61`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140002b61`

## string_xrefs

- `0x140002b67`: `GameInput.dll`
- `0x14000331c`: `GameInput.dll`
- `0x140002b79`: `GameInputRedist.dll`
- `0x140002c1a`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002cdc`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002d6a`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002e03`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002e9b`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002f25`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x14000300d`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x1400030bf`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x1400032b0`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x1400035a4`: `onecore\xbox\gameinput\published\svc\service.cpp`

## pseudocode

```c
__int64 __fastcall ModifyGameInputFiles(char a1)
{
  unsigned __int64 v2; // r12
  ULONGLONG v3; // rax
  ULONGLONG v4; // rax
  ULONGLONG v5; // rax
  BOOL v6; // eax
  BOOL v7; // esi
  UINT SystemDirectoryW; // eax
  unsigned __int64 v9; // rbx
  int LastError; // ebx
  int v11; // r8d
  int v12; // r9d
  bool v13; // cc
  SIZE_T v14; // rax
  PVOID ProcessHeap; // rcx
  WCHAR *Heap; // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  char *v20; // rdx
  const char **v21; // rax
  int v22; // r8d
  int v23; // r9d
  UINT SystemWow64DirectoryW; // eax
  unsigned __int64 v25; // rbx
  int v26; // r8d
  int v27; // r9d
  SIZE_T v28; // rax
  PVOID v29; // rcx
  WCHAR *v30; // rax
  int v31; // r8d
  int v32; // r9d
  LSTATUS ValueW; // eax
  SIZE_T v34; // rax
  struct _PEB *v35; // rcx
  _WORD *v36; // rax
  int v37; // r8d
  int v38; // r9d
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // r13
  const char **v42; // r15
  unsigned __int64 v43; // rax
  __int64 v44; // rax
  SIZE_T v45; // rax
  PVOID v46; // rcx
  wchar_t *v47; // rax
  int v48; // r9d
  int v49; // r8d
  int v50; // ecx
  char *v51; // rdx
  __int64 v52; // rdx
  unsigned __int64 v53; // rsi
  __int64 v54; // rcx
  SIZE_T v55; // rax
  PVOID v56; // rcx
  __int64 v57; // rdi
  const char *v58; // r14
  int v59; // r8d
  int v60; // r9d
  int v61; // ecx
  char *v62; // rdx
  DWORD *pvData; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  const char *v67; // [rsp+48h] [rbp-B8h] BYREF
  char v68; // [rsp+50h] [rbp-B0h]
  const char *v69; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Buffer; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v72; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v73; // [rsp+78h] [rbp-88h] BYREF
  WCHAR *v74; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v75[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v76[5]; // [rsp+98h] [rbp-68h] BYREF
  char v77; // [rsp+C0h] [rbp-40h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF

  v68 = a1;
  memset_0(&VersionInformation.dwPlatformId, 0, 0x10Cu);
  v2 = 0;
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
  VersionInformation.dwBuildNumber = 18978;
  v3 = VerSetConditionMask(0, 2u, 3u);
  v4 = VerSetConditionMask(v3, 1u, 3u);
  v5 = VerSetConditionMask(v4, 4u, 3u);
  v6 = VerifyVersionInfoW(&VersionInformation, 7u, v5);
  v73 = 0;
  v7 = v6;
  LODWORD(v67) = v6;
  v75[0] = L"GameInput.dll";
  v69 = (const char *)L"GameInputRedist.dll";
  v75[1] = L"GameInputRedist.dll";
  v74 = 0;
  v76[0] = &v73;
  v76[1] = &v74;
  v76[2] = &v72;
  v76[3] = &Buffer;
  v76[4] = &lpFileName;
  v72 = 0;
  Buffer = 0;
  lpFileName = 0;
  v77 = 1;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v9 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      pcbData = LastError;
      v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      v65 = 268;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018 & 0x800,
        (unsigned int)byte_14000AD93,
        v11,
        v12,
        (__int64)&v67,
        (__int64)&v65,
        (__int64)&pcbData);
    }
    goto LABEL_6;
  }
  v14 = 2LL * SystemDirectoryW;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v9, 2u) )
    v14 = -1;
  Heap = (WCHAR *)RtlAllocateHeap(ProcessHeap, 0, v14);
  v73 = Heap;
  if ( !Heap )
  {
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_52;
    v19 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_52;
    pcbData = 270;
    v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    v20 = byte_14000AD43;
    pvData = &pcbData;
    v21 = &v67;
    goto LABEL_51;
  }
  if ( !GetSystemDirectoryW(Heap, v9) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v65 = LastError;
      v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      pcbData = 271;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000AD03,
        v22,
        v23,
        (__int64)&v67,
        (__int64)&pcbData,
        (__int64)&v65);
    }
    goto LABEL_6;
  }
  SystemWow64DirectoryW = GetSystemWow64DirectoryW(0, 0);
  v25 = SystemWow64DirectoryW;
  if ( !SystemWow64DirectoryW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v65 = LastError;
      v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      pcbData = 278;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000ACC3,
        v26,
        v27,
        (__int64)&v67,
        (__int64)&pcbData,
        (__int64)&v65);
    }
    goto LABEL_6;
  }
  v28 = 2LL * SystemWow64DirectoryW;
  v29 = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v25, 2u) )
    v28 = -1;
  v30 = (WCHAR *)RtlAllocateHeap(v29, 0, v28);
  v74 = v30;
  if ( !v30 )
  {
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_52;
    v19 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_52;
    pcbData = 280;
    v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    v20 = byte_14000AC73;
    pvData = &pcbData;
    v21 = &v67;
    goto LABEL_51;
  }
  if ( !GetSystemWow64DirectoryW(v30, v25) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v65 = LastError;
      v67 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      pcbData = 281;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000AC33,
        v31,
        v32,
        (__int64)&v67,
        (__int64)&pcbData,
        (__int64)&v65);
    }
LABEL_6:
    v13 = LastError <= 0;
    if ( !LastError )
    {
      LastError = -2147418113;
      goto LABEL_123;
    }
    goto LABEL_20;
  }
  if ( a1 )
  {
    pcbData = 0;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\GameInput", L"RedistDir", 0x20002u, 0, 0, &pcbData);
    LastError = ValueW;
    if ( ValueW )
    {
      if ( ValueW <= 0 )
        goto LABEL_123;
      LastError = (unsigned __int16)ValueW;
      goto LABEL_22;
    }
    v34 = 2LL * pcbData;
    v35 = NtCurrentPeb();
    if ( !is_mul_ok(pcbData, 2u) )
      v34 = -1;
    v36 = RtlAllocateHeap(v35->ProcessHeap, 0, v34);
    v72 = v36;
    if ( !v36 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        goto LABEL_52;
      v19 = qword_14000E018;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        goto LABEL_52;
      LODWORD(v67) = 303;
      v69 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      v20 = byte_14000ABE3;
      pvData = (DWORD *)&v67;
      v21 = &v69;
LABEL_51:
      v65 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v19,
        (_DWORD)v20,
        v17,
        v18,
        (__int64)v21,
        (__int64)pvData,
        (__int64)&v65);
LABEL_52:
      LastError = -2147024882;
      goto LABEL_123;
    }
    LastError = RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\GameInput",
                  L"RedistDir",
                  0x20002u,
                  0,
                  v36,
                  &pcbData);
    if ( LastError )
    {
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        LODWORD(v67) = LastError;
        v69 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
        v65 = 311;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)byte_14000ABA3,
          v37,
          v38,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v67);
      }
      v13 = LastError <= 0;
LABEL_20:
      if ( v13 )
        goto LABEL_123;
      LastError = (unsigned __int16)LastError;
LABEL_22:
      LastError |= 0x80070000;
      goto LABEL_123;
    }
  }
  v39 = 0;
  v40 = 0;
  v41 = 2LL - v7;
  v42 = (const char **)v75;
  if ( v7 )
    v42 = &v69;
  do
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)&v42[v40][2 * v43] );
    if ( v43 > v39 )
      v39 = v43;
    ++v40;
  }
  while ( v40 < v41 );
  if ( a1 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v72[v44] );
    v2 = v39 + v44 + 15;
    v45 = 2 * v2;
    v46 = NtCurrentPeb()->ProcessHeap;
    if ( !is_mul_ok(v2, 2u) )
      v45 = -1;
    v47 = (wchar_t *)RtlAllocateHeap(v46, 0, v45);
    v49 = 0;
    Buffer = v47;
    if ( !v47 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        goto LABEL_52;
      v50 = qword_14000E018;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        goto LABEL_52;
      v65 = 352;
      v51 = byte_14000AB53;
      goto LABEL_91;
    }
  }
  v52 = -1;
  do
    ++v52;
  while ( v73[v52] );
  v53 = v52 + v39 + 2;
  if ( v74 )
  {
    v54 = -1;
    do
      ++v54;
    while ( v74[v54] );
    if ( v53 >= v54 + v39 + 2 )
      v54 = v52;
    v53 = v39 + v54 + 2;
  }
  v55 = 2 * v53;
  v56 = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v53, 2u) )
    v55 = -1;
  lpFileName = (LPCWSTR)RtlAllocateHeap(v56, 0, v55);
  if ( !lpFileName )
  {
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_52;
    v50 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_52;
    v65 = 364;
    v51 = byte_14000AB03;
LABEL_91:
    v69 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    LODWORD(v67) = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v50,
      (_DWORD)v51,
      v49,
      v48,
      (__int64)&v69,
      (__int64)&v65,
      (__int64)&v67);
    goto LABEL_52;
  }
  if ( (_DWORD)v67 )
  {
    if ( a1 )
    {
      swprintf_s(Buffer, v2, L"%ws\\..\\%ws\\%ws", v72, L"x64", *v42);
      swprintf_s((wchar_t *const)lpFileName, v53, L"%ws\\%ws", v73, L"GameInput.dll");
      if ( IsFileNewerThan(Buffer, lpFileName) == 1 )
      {
        LastError = -2147286779;
        goto LABEL_123;
      }
    }
  }
  v57 = 0;
  while ( 1 )
  {
    v58 = v42[v57];
    swprintf_s((wchar_t *const)lpFileName, v53, L"%ws\\%ws", v73, v58);
    if ( v68 )
    {
      swprintf_s(Buffer, v2, L"%ws\\..\\%ws\\%ws", v72, L"x64", v58);
      LastError = CopyFileIfNewer(Buffer, lpFileName);
      if ( LastError < 0 )
      {
        if ( (unsigned int)dword_14000E000 <= 2 )
          goto LABEL_123;
        v61 = qword_14000E018;
        if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
          goto LABEL_123;
        v65 = 388;
        v62 = (char *)&word_14000AAC6;
LABEL_122:
        v69 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
        LODWORD(v67) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v61,
          (_DWORD)v62,
          v59,
          v60,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v67);
        goto LABEL_123;
      }
    }
    else
    {
      LastError = DeleteFiles(lpFileName);
      if ( LastError < 0 )
      {
        if ( (unsigned int)dword_14000E000 > 2 )
        {
          v61 = qword_14000E018;
          if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
          {
            v65 = 392;
            v62 = byte_14000AA89;
            goto LABEL_122;
          }
        }
        goto LABEL_123;
      }
    }
    if ( v74 )
      break;
LABEL_112:
    if ( ++v57 >= v41 )
    {
      utl::scope_exit__ModifyGameInputFiles_::_2_::_lambda_1___::_scope_exit__ModifyGameInputFiles_::_2_::_lambda_1___(v76);
      return 0;
    }
  }
  swprintf_s((wchar_t *const)lpFileName, v53, L"%ws\\%ws");
  if ( v68 )
  {
    swprintf_s(Buffer, v2, L"%ws\\..\\%ws\\%ws", v72, L"x86", v58);
    LastError = CopyFileIfNewer(Buffer, lpFileName);
    if ( LastError < 0 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        goto LABEL_123;
      v61 = qword_14000E018;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        goto LABEL_123;
      v65 = 400;
      v62 = (char *)&dword_14000AA4C;
      goto LABEL_122;
    }
    goto LABEL_112;
  }
  LastError = DeleteFiles(lpFileName);
  if ( LastError >= 0 )
    goto LABEL_112;
  if ( (unsigned int)dword_14000E000 > 2 )
  {
    v61 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v65 = 404;
      v62 = &byte_14000AA0F;
      goto LABEL_122;
    }
  }
LABEL_123:
  utl::scope_exit__ModifyGameInputFiles_::_2_::_lambda_1___::_scope_exit__ModifyGameInputFiles_::_2_::_lambda_1___(v76);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140002ac0  push    rbp
0x140002ac2  push    rbx
0x140002ac3  push    rsi
0x140002ac4  push    rdi
0x140002ac5  push    r12
0x140002ac7  push    r13
0x140002ac9  push    r14
0x140002acb  push    r15
0x140002acd  lea     rbp, [rsp-108h]
0x140002ad5  sub     rsp, 208h
0x140002adc  mov     rax, cs:__security_cookie
0x140002ae3  xor     rax, rsp
0x140002ae6  mov     [rbp+140h+var_50], rax
0x140002aed  mov     r14b, cl
0x140002af0  mov     [rsp+240h+var_1F0], cl
0x140002af4  mov     edi, 10Ch
0x140002af9  lea     rcx, [rbp+140h+VersionInformation.dwPlatformId]; void *
0x140002afd  mov     r8d, edi; Size
0x140002b00  xor     edx, edx; Val
0x140002b02  call    memset_0
0x140002b07  xor     r12d, r12d
0x140002b0a  mov     [rbp+140h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140002b11  mov     r8b, 3; Condition
0x140002b14  mov     qword ptr [rbp+140h+VersionInformation.dwMajorVersion], 0Ah
0x140002b1c  xor     ecx, ecx; ConditionMask
0x140002b1e  mov     [rbp+140h+VersionInformation.dwBuildNumber], 4A22h
0x140002b25  lea     r15d, [r12+2]
0x140002b2a  mov     edx, r15d; TypeMask
0x140002b2d  call    cs:__imp_VerSetConditionMask
0x140002b33  mov     r8b, 3; Condition
0x140002b36  lea     edx, [r12+1]; TypeMask
0x140002b3b  mov     rcx, rax; ConditionMask
0x140002b3e  call    cs:__imp_VerSetConditionMask
0x140002b44  mov     r8b, 3; Condition
0x140002b47  lea     edx, [r12+4]; TypeMask
0x140002b4c  mov     rcx, rax; ConditionMask
0x140002b4f  call    cs:__imp_VerSetConditionMask
0x140002b55  mov     r8, rax; dwlConditionMask
0x140002b58  lea     edx, [r12+7]; dwTypeMask
0x140002b5d  lea     rcx, [rbp+140h+VersionInformation]; lpVersionInformation
0x140002b61  call    cs:__imp_VerifyVersionInfoW
0x140002b67  lea     rcx, aGameinputDll; "GameInput.dll"
0x140002b6e  mov     [rsp+240h+var_1C8], r12
0x140002b73  mov     esi, eax
0x140002b75  mov     dword ptr [rsp+240h+var_1F8], eax
0x140002b79  lea     rax, aGameinputredis; "GameInputRedist.dll"
0x140002b80  mov     [rbp+140h+var_1B8], rcx
0x140002b84  mov     [rsp+240h+var_1E8], rax
0x140002b89  xor     edx, edx; uSize
0x140002b8b  mov     [rbp+140h+var_1B0], rax
0x140002b8f  xor     ecx, ecx; lpBuffer
0x140002b91  lea     rax, [rsp+240h+var_1C8]
0x140002b96  mov     [rbp+140h+var_1C0], r12
0x140002b9a  mov     [rbp+140h+var_1A8], rax
0x140002b9e  lea     rax, [rbp+140h+var_1C0]
0x140002ba2  mov     [rbp+140h+var_1A0], rax
0x140002ba6  lea     rax, [rsp+240h+var_1D0]
0x140002bab  mov     [rbp+140h+var_198], rax
0x140002baf  lea     rax, [rsp+240h+Buffer]
0x140002bb4  mov     [rbp+140h+var_190], rax
0x140002bb8  lea     rax, [rsp+240h+lpFileName]
0x140002bbd  mov     [rbp+140h+var_188], rax
0x140002bc1  mov     [rsp+240h+var_1D0], r12
0x140002bc6  mov     [rsp+240h+Buffer], r12
0x140002bcb  mov     [rsp+240h+lpFileName], r12
0x140002bd0  mov     [rbp+140h+var_180], 1
0x140002bd4  call    cs:__imp_GetSystemDirectoryW
0x140002bda  mov     ebx, eax
0x140002bdc  test    eax, eax
0x140002bde  jnz     loc_140002C6A
0x140002be4  call    cs:__imp_GetLastError
0x140002bea  mov     ecx, cs:dword_14000E000
0x140002bf0  mov     ebx, eax
0x140002bf2  cmp     ecx, r15d
0x140002bf5  jbe     short loc_140002C58
0x140002bf7  mov     rax, cs:qword_14000E018
0x140002bfe  mov     edx, 800h
0x140002c03  mov     rcx, cs:qword_14000E010
0x140002c0a  test    rdx, rcx
0x140002c0d  jz      short loc_140002C58
0x140002c0f  mov     rcx, rax
0x140002c12  and     rcx, rdx
0x140002c15  cmp     rcx, rax
0x140002c18  jnz     short loc_140002C58
0x140002c1a  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002c21  mov     [rsp+240h+var_1FC], ebx
0x140002c25  mov     [rsp+240h+var_1F8], rax
0x140002c2a  lea     rdx, byte_14000AD93
0x140002c31  lea     rax, [rsp+240h+var_1FC]
0x140002c36  mov     [rsp+240h+var_200], edi
0x140002c3a  mov     [rsp+240h+pcbData], rax
0x140002c3f  lea     rax, [rsp+240h+var_200]
0x140002c44  mov     [rsp+240h+pvData], rax
0x140002c49  lea     rax, [rsp+240h+var_1F8]
0x140002c4e  mov     [rsp+240h+pdwType], rax
0x140002c53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140002c58  test    ebx, ebx
0x140002c5a  jnz     loc_140002D9D
0x140002c60  mov     ebx, 8000FFFFh
0x140002c65  jmp     loc_1400035D7
0x140002c6a  mov     rcx, gs:60h
0x140002c73  mov     rax, r15
0x140002c76  mul     rbx
0x140002c79  mov     rcx, [rcx+30h]; HeapHandle
0x140002c7d  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140002c84  cmovb   rax, r13
0x140002c88  xor     edx, edx; Flags
0x140002c8a  mov     r8, rax; Size
0x140002c8d  call    cs:__imp_RtlAllocateHeap
0x140002c93  mov     [rsp+240h+var_1C8], rax
0x140002c98  mov     edi, 8007000Eh
0x140002c9d  test    rax, rax
0x140002ca0  jnz     short loc_140002D15
0x140002ca2  mov     eax, cs:dword_14000E000
0x140002ca8  cmp     eax, r15d
0x140002cab  jbe     loc_14000304F
0x140002cb1  mov     rcx, cs:qword_14000E018
0x140002cb8  mov     edx, 800h
0x140002cbd  mov     rax, cs:qword_14000E010
0x140002cc4  test    rdx, rax
0x140002cc7  jz      loc_14000304F
0x140002ccd  mov     rax, rcx
0x140002cd0  and     rax, rdx
0x140002cd3  cmp     rax, rcx
0x140002cd6  jnz     loc_14000304F
0x140002cdc  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002ce3  mov     [rsp+240h+var_1FC], 10Eh
0x140002ceb  mov     [rsp+240h+var_1F8], rax
0x140002cf0  lea     rdx, byte_14000AD43
0x140002cf7  lea     rax, [rsp+240h+var_200]
0x140002cfc  mov     [rsp+240h+pcbData], rax
0x140002d01  lea     rax, [rsp+240h+var_1FC]
0x140002d06  mov     [rsp+240h+pvData], rax
0x140002d0b  lea     rax, [rsp+240h+var_1F8]
0x140002d10  jmp     loc_140003041
0x140002d15  mov     edx, ebx; uSize
0x140002d17  mov     rcx, rax; lpBuffer
0x140002d1a  call    cs:__imp_GetSystemDirectoryW
0x140002d20  test    eax, eax
0x140002d22  jnz     loc_140002DB1
0x140002d28  call    cs:__imp_GetLastError
0x140002d2e  mov     ebx, eax
0x140002d30  mov     eax, cs:dword_14000E000
0x140002d36  cmp     eax, r15d
0x140002d39  jbe     loc_140002C58
0x140002d3f  mov     rcx, cs:qword_14000E018
0x140002d46  mov     edx, 800h
0x140002d4b  mov     rax, cs:qword_14000E010
0x140002d52  test    rdx, rax
0x140002d55  jz      loc_140002C58
0x140002d5b  mov     rax, rcx
0x140002d5e  and     rax, rdx
0x140002d61  cmp     rax, rcx
0x140002d64  jnz     loc_140002C58
0x140002d6a  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002d71  mov     [rsp+240h+var_200], ebx
0x140002d75  mov     [rsp+240h+var_1F8], rax
0x140002d7a  lea     rdx, byte_14000AD03
0x140002d81  lea     rax, [rsp+240h+var_200]
0x140002d86  mov     [rsp+240h+var_1FC], 10Fh
0x140002d8e  mov     [rsp+240h+pcbData], rax
0x140002d93  lea     rax, [rsp+240h+var_1FC]
0x140002d98  jmp     loc_140002C44
0x140002d9d  jle     loc_1400035D7
0x140002da3  movzx   ebx, bx
0x140002da6  or      ebx, 80070000h
0x140002dac  jmp     loc_1400035D7
0x140002db1  xor     edx, edx; uSize
0x140002db3  xor     ecx, ecx; lpBuffer
0x140002db5  call    cs:__imp_GetSystemWow64DirectoryW
0x140002dbb  mov     ebx, eax
0x140002dbd  test    eax, eax
0x140002dbf  jnz     short loc_140002E36
0x140002dc1  call    cs:__imp_GetLastError
0x140002dc7  mov     ebx, eax
0x140002dc9  mov     eax, cs:dword_14000E000
0x140002dcf  cmp     eax, r15d
0x140002dd2  jbe     loc_140002C58
0x140002dd8  mov     rcx, cs:qword_14000E018
0x140002ddf  mov     edx, 800h
0x140002de4  mov     rax, cs:qword_14000E010
0x140002deb  test    rdx, rax
0x140002dee  jz      loc_140002C58
0x140002df4  mov     rax, rcx
0x140002df7  and     rax, rdx
0x140002dfa  cmp     rax, rcx
0x140002dfd  jnz     loc_140002C58
0x140002e03  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002e0a  mov     [rsp+240h+var_200], ebx
0x140002e0e  mov     [rsp+240h+var_1F8], rax
0x140002e13  lea     rdx, byte_14000ACC3
0x140002e1a  lea     rax, [rsp+240h+var_200]
0x140002e1f  mov     [rsp+240h+var_1FC], 116h
0x140002e27  mov     [rsp+240h+pcbData], rax
0x140002e2c  lea     rax, [rsp+240h+var_1FC]
0x140002e31  jmp     loc_140002C44
0x140002e36  mov     rcx, gs:60h
0x140002e3f  mov     rax, r15
0x140002e42  mul     rbx
0x140002e45  mov     rcx, [rcx+30h]; HeapHandle
0x140002e49  cmovb   rax, r13
0x140002e4d  xor     edx, edx; Flags
0x140002e4f  mov     r8, rax; Size
0x140002e52  call    cs:__imp_RtlAllocateHeap
0x140002e58  mov     [rbp+140h+var_1C0], rax
0x140002e5c  test    rax, rax
0x140002e5f  jnz     short loc_140002ED4
0x140002e61  mov     eax, cs:dword_14000E000
0x140002e67  cmp     eax, r15d
0x140002e6a  jbe     loc_14000304F
0x140002e70  mov     rcx, cs:qword_14000E018
0x140002e77  mov     edx, 800h
0x140002e7c  mov     rax, cs:qword_14000E010
0x140002e83  test    rdx, rax
0x140002e86  jz      loc_14000304F
0x140002e8c  mov     rax, rcx
0x140002e8f  and     rax, rdx
0x140002e92  cmp     rax, rcx
0x140002e95  jnz     loc_14000304F
0x140002e9b  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002ea2  mov     [rsp+240h+var_1FC], 118h
0x140002eaa  mov     [rsp+240h+var_1F8], rax
0x140002eaf  lea     rdx, byte_14000AC73
0x140002eb6  lea     rax, [rsp+240h+var_200]
0x140002ebb  mov     [rsp+240h+pcbData], rax
0x140002ec0  lea     rax, [rsp+240h+var_1FC]
0x140002ec5  mov     [rsp+240h+pvData], rax
0x140002eca  lea     rax, [rsp+240h+var_1F8]
0x140002ecf  jmp     loc_140003041
0x140002ed4  mov     edx, ebx; uSize
0x140002ed6  mov     rcx, rax; lpBuffer
0x140002ed9  call    cs:__imp_GetSystemWow64DirectoryW
0x140002edf  test    eax, eax
0x140002ee1  jnz     short loc_140002F58
0x140002ee3  call    cs:__imp_GetLastError
0x140002ee9  mov     ebx, eax
0x140002eeb  mov     eax, cs:dword_14000E000
0x140002ef1  cmp     eax, r15d
0x140002ef4  jbe     loc_140002C58
0x140002efa  mov     rcx, cs:qword_14000E018
0x140002f01  mov     edx, 800h
0x140002f06  mov     rax, cs:qword_14000E010
0x140002f0d  test    rdx, rax
0x140002f10  jz      loc_140002C58
0x140002f16  mov     rax, rcx
0x140002f19  and     rax, rdx
0x140002f1c  cmp     rax, rcx
0x140002f1f  jnz     loc_140002C58
0x140002f25  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002f2c  mov     [rsp+240h+var_200], ebx
0x140002f30  mov     [rsp+240h+var_1F8], rax
0x140002f35  lea     rdx, byte_14000AC33
0x140002f3c  lea     rax, [rsp+240h+var_200]
0x140002f41  mov     [rsp+240h+var_1FC], 119h
0x140002f49  mov     [rsp+240h+pcbData], rax
0x140002f4e  lea     rax, [rsp+240h+var_1FC]
0x140002f53  jmp     loc_140002C44
0x140002f58  test    r14b, r14b
0x140002f5b  jz      loc_140003108
0x140002f61  lea     rax, [rsp+240h+var_1FC]
0x140002f66  mov     [rsp+240h+var_1FC], r12d
0x140002f6b  mov     [rsp+240h+pcbData], rax; pcbData
0x140002f70  lea     r8, Value; "RedistDir"
0x140002f77  mov     [rsp+240h+pvData], r12; pvData
0x140002f7c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\GameInput"
0x140002f83  mov     r9d, 20002h; dwFlags
0x140002f89  mov     [rsp+240h+pdwType], r12; pdwType
0x140002f8e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002f95  call    cs:__imp_RegGetValueW
0x140002f9b  mov     ebx, eax
0x140002f9d  test    eax, eax
0x140002f9f  jz      short loc_140002FAF
0x140002fa1  jle     loc_1400035D7
0x140002fa7  movzx   ebx, ax
0x140002faa  jmp     loc_140002DA6
0x140002faf  mov     ecx, [rsp+240h+var_1FC]
0x140002fb3  mov     rax, r15
0x140002fb6  mul     rcx
0x140002fb9  mov     rcx, gs:60h
0x140002fc2  cmovb   rax, r13
0x140002fc6  xor     edx, edx; Flags
0x140002fc8  mov     r8, rax; Size
0x140002fcb  mov     rcx, [rcx+30h]; HeapHandle
0x140002fcf  call    cs:__imp_RtlAllocateHeap
0x140002fd5  mov     [rsp+240h+var_1D0], rax
0x140002fda  test    rax, rax
0x140002fdd  jnz     short loc_140003056
0x140002fdf  mov     eax, cs:dword_14000E000
0x140002fe5  cmp     eax, r15d
0x140002fe8  jbe     short loc_14000304F
0x140002fea  mov     rcx, cs:qword_14000E018
0x140002ff1  mov     edx, 800h
0x140002ff6  mov     rax, cs:qword_14000E010
0x140002ffd  test    rdx, rax
0x140003000  jz      short loc_14000304F
0x140003002  mov     rax, rcx
0x140003005  and     rax, rdx
0x140003008  cmp     rax, rcx
0x14000300b  jnz     short loc_14000304F
0x14000300d  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
  ... truncated ...
```
