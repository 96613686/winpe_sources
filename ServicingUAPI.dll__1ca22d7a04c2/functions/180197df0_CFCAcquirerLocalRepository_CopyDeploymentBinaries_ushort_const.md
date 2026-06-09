# CFCAcquirerLocalRepository::CopyDeploymentBinaries(ushort const *)

- ea: `0x180197df0`
- end: `0x18019859d`
- name: `?CopyDeploymentBinaries@CFCAcquirerLocalRepository@@UEAAJPEBG@Z`
- size: `1965`
- prototype: `int(CFCAcquirerLocalRepository *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800031d0`
- `0x180068c4c`
- `0x18006fab0`
- `0x1801975bc`
- `0x180197644`
- `0x180197df0`
- `0x18019cb24`
- `0x18019d714`
- `0x1801ab8e4`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019813c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801981b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019813c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801981b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198403`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18019812c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18019812c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801984e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019853e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019856a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801984e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019853e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019856a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801984cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801984fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801984cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801984fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198556`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197e88`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197f01`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198019`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198308`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197e88`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197f01`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198019`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198308`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801983f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801983f3`

## string_xrefs

- `0x180197f73`: `UpdateAgent.dll`
- `0x180198285`: `UpdateAgent.dll`
- `0x180197fd6`: `CFCAcquirerLocalRepository::CopyDeploymentBinaries`
- `0x1801980e8`: `CFCAcquirerLocalRepository::CopyDeploymentBinaries`
- `0x1801982c5`: `CFCAcquirerLocalRepository::CopyDeploymentBinaries`
- `0x180198494`: `CFCAcquirerLocalRepository::CopyDeploymentBinaries`
- `0x180198055`: `FCAcquirerLocalRepository: Couldn't find media UpdateAgent path: %ws`
- `0x180197f83`: `FCAcquirerLocalRepository: Searching %ws in local UpdateAgent path [%ws]`
- `0x1801983d1`: `FCAcquirerLocalRepository: Copying %ws from [%ws] to [%ws]`
- `0x180198225`: `FCAcquirerLocalRepository: Module DLL Path: %ws`

## pseudocode

```c
__int64 __fastcall CFCAcquirerLocalRepository::CopyDeploymentBinaries(
        CFCAcquirerLocalRepository *this,
        const unsigned __int16 *a2)
{
  bool v2; // zf
  void *v4; // rbx
  const WCHAR *v5; // r15
  const WCHAR *v6; // r13
  signed int v7; // esi
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // eax
  DWORD FileAttributesW; // edi
  int v12; // edi
  const WCHAR *v13; // rcx
  DWORD v14; // esi
  int v15; // esi
  _QWORD *v16; // rdi
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  DWORD v22; // eax
  BOOL v23; // esi
  const unsigned __int16 *v24; // r14
  int v25; // eax
  __int64 v26; // rdi
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  signed int LastError; // eax
  __int64 v31; // rax
  signed int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // r14
  int v36; // eax
  __int64 v37; // rdi
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  DWORD v41; // eax
  BOOL v42; // esi
  int v43; // eax
  signed int v44; // eax
  int v45; // eax
  int v46; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v48; // rax
  HANDLE v49; // rax
  HANDLE v50; // rax
  __int64 v52; // [rsp+20h] [rbp-40h]
  __int64 v53; // [rsp+28h] [rbp-38h]
  signed int v54; // [rsp+28h] [rbp-38h]
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v56; // [rsp+38h] [rbp-28h]
  HMODULE phModule; // [rsp+40h] [rbp-20h] BYREF
  __int64 v58; // [rsp+48h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-10h] BYREF

  v56 = a2;
  v2 = (*((_BYTE *)this - 68) & 8) == 0;
  phModule = 0;
  v4 = 0;
  v58 = 0;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  lpNewFileName = 0;
  if ( !v2 )
  {
    v7 = 0;
LABEL_92:
    v35 = v58;
    goto LABEL_93;
  }
  if ( !a2 )
  {
    v8 = *((_QWORD *)this - 1);
    v7 = -2147024809;
    v9 = 0;
    if ( v8 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v8 + 32LL))(*((_QWORD *)this - 1), 2147942487LL);
      LODWORD(v53) = -2147024809;
      LODWORD(v52) = 228;
      goto LABEL_89;
    }
LABEL_91:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    goto LABEL_92;
  }
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
    v12 = 0;
  else
    v12 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v12 )
  {
    v8 = *((_QWORD *)this - 1);
    v9 = 0;
    v7 = -2147024893;
    if ( !v8 )
      goto LABEL_91;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, 2147942403LL);
    LODWORD(v53) = -2147024893;
    LODWORD(v52) = 230;
    goto LABEL_89;
  }
  v13 = (const WCHAR *)*((_QWORD *)this + 2);
  if ( v13 )
  {
    v14 = GetFileAttributesW(v13);
    if ( v14 == -1 )
      v15 = 0;
    else
      v15 = (v14 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v16 = (_QWORD *)((char *)this - 8);
    if ( !v15 )
    {
      v8 = *v16;
      v9 = 0;
      v7 = -2147024893;
      if ( !v8 )
        goto LABEL_91;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, 2147942403LL);
      LODWORD(v53) = -2147024893;
      LODWORD(v52) = 237;
      goto LABEL_89;
    }
    if ( *v16 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        *v16,
        2,
        L"FCAcquirerLocalRepository: Searching %ws in local UpdateAgent path [%ws]",
        L"UpdateAgent.dll",
        *((_QWORD *)this + 2));
    v17 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 2), L"UpdateAgent.dll", 0, &lpFileName);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = *v16;
      v19 = 0;
      if ( v18 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 32LL))(v18, (unsigned int)v17);
        LODWORD(v52) = 241;
        v21 = CFCLogLiteT<CEmptyType>::LogFormat(
                v18,
                4 - (unsigned int)(v20 != 0),
                L"%s(%d): Result = 0x%X",
                L"CFCAcquirerLocalRepository::CopyDeploymentBinaries",
                v52,
                v7);
        v19 = (unsigned int)v21;
        if ( v21 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
      v5 = lpFileName;
      goto LABEL_92;
    }
    v5 = lpFileName;
    v22 = GetFileAttributesW(lpFileName);
    v23 = v22 != -1 && (v22 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v23 )
    {
      if ( *v16 )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *v16,
          4,
          L"FCAcquirerLocalRepository: Couldn't find media UpdateAgent path: %ws",
          v5);
      v8 = *v16;
      v9 = 0;
      v7 = -2147024894;
      if ( !v8 )
        goto LABEL_91;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, 2147942402LL);
      LODWORD(v53) = -2147024894;
      LODWORD(v52) = 247;
      goto LABEL_89;
    }
    v24 = v56;
    v25 = CMiscHelpersT<CEmptyType>::CombinePath(v56, L"UpdateAgent.dll", 0, &lpNewFileName);
    v7 = v25;
    if ( v25 < 0 )
    {
      v26 = *v16;
      v27 = 0;
      if ( v26 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 32LL))(v26, (unsigned int)v25);
        v54 = v7;
        LODWORD(v52) = 250;
        goto LABEL_37;
      }
      goto LABEL_39;
    }
    goto LABEL_73;
  }
  if ( !GetModuleHandleExW(6u, (LPCWSTR)CFCAcquirerLocalRepository::Create, &phModule) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v9 = 0;
      if ( v7 >= 0 )
        goto LABEL_91;
    }
    else
    {
      v7 = -2147467259;
      v9 = 0;
    }
    v8 = *((_QWORD *)this - 1);
    if ( !v8 )
      goto LABEL_91;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v8 + 32LL))(*((_QWORD *)this - 1), (unsigned int)v7);
    LODWORD(v53) = v7;
    LODWORD(v52) = 258;
    goto LABEL_89;
  }
  v31 = FormModuleFullPathName(phModule);
  v4 = (void *)v31;
  if ( !v31 )
  {
    v4 = 0;
    v32 = GetLastError();
    v7 = v32;
    if ( v32 )
    {
      if ( v32 > 0 )
        v7 = (unsigned __int16)v32 | 0x80070000;
      v9 = 0;
      if ( v7 >= 0 )
        goto LABEL_91;
    }
    else
    {
      v7 = -2147467259;
      v9 = 0;
    }
    v8 = *((_QWORD *)this - 1);
    if ( !v8 )
      goto LABEL_91;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v8 + 32LL))(*((_QWORD *)this - 1), (unsigned int)v7);
    LODWORD(v53) = v7;
    LODWORD(v52) = 263;
    goto LABEL_89;
  }
  v16 = (_QWORD *)((char *)this - 8);
  v33 = *((_QWORD *)this - 1);
  if ( v33 )
    CFCLogLiteT<CEmptyType>::LogFormat(v33, 2, L"FCAcquirerLocalRepository: Module DLL Path: %ws", v31);
  v34 = CMiscHelpersT<CEmptyType>::ParseFileName(v4, 0);
  v7 = v34;
  if ( v34 < 0 )
  {
    v8 = *v16;
    v9 = 0;
    if ( !v8 )
      goto LABEL_91;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, (unsigned int)v34);
    LODWORD(v53) = v7;
    LODWORD(v52) = 268;
    goto LABEL_89;
  }
  v35 = v58;
  v36 = CMiscHelpersT<CEmptyType>::CombinePath(v58, L"UpdateAgent.dll", 0, &lpFileName);
  v7 = v36;
  if ( v36 >= 0 )
  {
    v5 = lpFileName;
    v41 = GetFileAttributesW(lpFileName);
    v42 = v41 != -1 && (v41 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v42 )
    {
      v8 = *v16;
      v9 = 0;
      v7 = -2147024894;
      if ( !v8 )
        goto LABEL_91;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, 2147942402LL);
      LODWORD(v53) = -2147024894;
      LODWORD(v52) = 271;
      goto LABEL_89;
    }
    v24 = v56;
LABEL_73:
    v43 = CMiscHelpersT<CEmptyType>::CombinePath(v24, L"UpdateAgent.dll", 0, &lpNewFileName);
    v7 = v43;
    if ( v43 < 0 )
    {
      v26 = *v16;
      v27 = 0;
      if ( v26 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 32LL))(v26, (unsigned int)v43);
        v54 = v7;
        LODWORD(v52) = 274;
LABEL_37:
        v29 = CFCLogLiteT<CEmptyType>::LogFormat(
                v26,
                4 - (unsigned int)(v28 != 0),
                L"%s(%d): Result = 0x%X",
                L"CFCAcquirerLocalRepository::CopyDeploymentBinaries",
                v52,
                v54);
        v27 = (unsigned int)v29;
        if ( v29 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v29);
      }
LABEL_39:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v27);
      v6 = lpNewFileName;
      goto LABEL_92;
    }
    v6 = lpNewFileName;
    if ( *v16 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        *v16,
        2,
        L"FCAcquirerLocalRepository: Copying %ws from [%ws] to [%ws]",
        L"UpdateAgent.dll",
        v5,
        lpNewFileName);
    if ( CopyFileW(v5, v6, 0) )
    {
      v45 = CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(v6);
      v7 = v45;
      if ( v45 >= 0 )
        goto LABEL_92;
      v8 = *v16;
      v9 = 0;
      if ( !v8 )
        goto LABEL_91;
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, (unsigned int)v45);
      LODWORD(v53) = v7;
      LODWORD(v52) = 279;
    }
    else
    {
      v44 = GetLastError();
      v7 = v44;
      if ( v44 )
      {
        if ( v44 > 0 )
          v7 = (unsigned __int16)v44 | 0x80070000;
        v9 = 0;
        if ( v7 >= 0 )
          goto LABEL_91;
      }
      else
      {
        v7 = -2147467259;
        v9 = 0;
      }
      v8 = *v16;
      if ( !v8 )
        goto LABEL_91;
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, (unsigned int)v7);
      LODWORD(v53) = v7;
      LODWORD(v52) = 278;
    }
LABEL_89:
    v46 = CFCLogLiteT<CEmptyType>::LogFormat(
            v8,
            4 - (unsigned int)(v10 != 0),
            L"%s(%d): Result = 0x%X",
            L"CFCAcquirerLocalRepository::CopyDeploymentBinaries",
            v52,
            v53);
    v9 = (unsigned int)v46;
    if ( v46 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v46);
    goto LABEL_91;
  }
  v37 = *v16;
  v38 = 0;
  if ( v37 )
  {
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 32LL))(v37, (unsigned int)v36);
    LODWORD(v52) = 269;
    v40 = CFCLogLiteT<CEmptyType>::LogFormat(
            v37,
            4 - (unsigned int)(v39 != 0),
            L"%s(%d): Result = 0x%X",
            L"CFCAcquirerLocalRepository::CopyDeploymentBinaries",
            v52,
            v7);
    v38 = (unsigned int)v40;
    if ( v40 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
  v5 = lpFileName;
LABEL_93:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v35 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, (LPVOID)(v35 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180197df0  mov     [rsp-38h+arg_10], rbx
0x180197df5  push    rbp
0x180197df6  push    rsi
0x180197df7  push    rdi
0x180197df8  push    r12
0x180197dfa  push    r13
0x180197dfc  push    r14
0x180197dfe  push    r15
0x180197e00  mov     rbp, rsp
0x180197e03  sub     rsp, 60h
0x180197e07  mov     rax, cs:__security_cookie
0x180197e0e  xor     rax, rsp
0x180197e11  mov     [rbp+var_8], rax
0x180197e15  xor     r12d, r12d
0x180197e18  mov     [rbp+var_28], rdx
0x180197e1c  test    byte ptr [rcx-44h], 8
0x180197e20  mov     rax, rdx
0x180197e23  mov     r14, rcx
0x180197e26  mov     [rbp+phModule], r12
0x180197e2a  mov     ebx, r12d
0x180197e2d  mov     [rbp+var_18], r12
0x180197e31  mov     r15d, r12d
0x180197e34  mov     [rbp+lpFileName], r12
0x180197e38  mov     r13d, r12d
0x180197e3b  mov     [rbp+lpNewFileName], r12
0x180197e3f  jz      short loc_180197E49
0x180197e41  mov     esi, r12d
0x180197e44  jmp     loc_1801984BF
0x180197e49  test    rax, rax
0x180197e4c  jnz     short loc_180197E85
0x180197e4e  mov     rdi, [r14-8]
0x180197e52  mov     esi, 80070057h
0x180197e57  mov     ecx, r12d
0x180197e5a  test    rdi, rdi
0x180197e5d  jz      loc_1801984BA
0x180197e63  mov     rax, [rdi]
0x180197e66  mov     edx, esi
0x180197e68  mov     rcx, rdi
0x180197e6b  mov     rax, [rax+20h]
0x180197e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197e74  mov     dword ptr [rsp+60h+var_38], esi
0x180197e78  mov     dword ptr [rsp+60h+var_40], 0E4h
0x180197e80  jmp     loc_180198492
0x180197e85  mov     rcx, rax; lpFileName
0x180197e88  call    cs:__imp_GetFileAttributesW
0x180197e8f  nop     dword ptr [rax+rax+00h]
0x180197e94  mov     edi, eax
0x180197e96  cmp     eax, 0FFFFFFFFh
0x180197e99  jz      short loc_180197EA3
0x180197e9b  shr     edi, 4
0x180197e9e  and     edi, 1
0x180197ea1  jmp     short loc_180197EA6
0x180197ea3  mov     edi, r12d
0x180197ea6  xor     ecx, ecx
0x180197ea8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197ead  xor     ecx, ecx
0x180197eaf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197eb4  test    edi, edi
0x180197eb6  jnz     short loc_180197EF4
0x180197eb8  mov     rdi, [r14-8]
0x180197ebc  xor     ecx, ecx
0x180197ebe  mov     r12d, 80070003h
0x180197ec4  mov     esi, r12d
0x180197ec7  test    rdi, rdi
0x180197eca  jz      loc_1801984BA
0x180197ed0  mov     rax, [rdi]
0x180197ed3  mov     edx, r12d
0x180197ed6  mov     rcx, rdi
0x180197ed9  mov     rax, [rax+20h]
0x180197edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197ee2  mov     dword ptr [rsp+60h+var_38], r12d
0x180197ee7  mov     dword ptr [rsp+60h+var_40], 0E6h
0x180197eef  jmp     loc_180198492
0x180197ef4  mov     rcx, [r14+10h]; lpFileName
0x180197ef8  test    rcx, rcx
0x180197efb  jz      loc_18019811C
0x180197f01  call    cs:__imp_GetFileAttributesW
0x180197f08  nop     dword ptr [rax+rax+00h]
0x180197f0d  mov     esi, eax
0x180197f0f  cmp     eax, 0FFFFFFFFh
0x180197f12  jz      short loc_180197F1C
0x180197f14  shr     esi, 4
0x180197f17  and     esi, 1
0x180197f1a  jmp     short loc_180197F1F
0x180197f1c  mov     esi, r12d
0x180197f1f  xor     ecx, ecx
0x180197f21  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197f26  xor     ecx, ecx
0x180197f28  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197f2d  lea     rdi, [r14-8]
0x180197f31  test    esi, esi
0x180197f33  jnz     short loc_180197F70
0x180197f35  mov     rdi, [rdi]
0x180197f38  xor     ecx, ecx
0x180197f3a  mov     r12d, 80070003h
0x180197f40  mov     esi, r12d
0x180197f43  test    rdi, rdi
0x180197f46  jz      loc_1801984BA
0x180197f4c  mov     rax, [rdi]
0x180197f4f  mov     edx, r12d
0x180197f52  mov     rcx, rdi
0x180197f55  mov     rax, [rax+20h]
0x180197f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197f5e  mov     dword ptr [rsp+60h+var_38], r12d
0x180197f63  mov     dword ptr [rsp+60h+var_40], 0EDh
0x180197f6b  jmp     loc_180198492
0x180197f70  mov     rcx, [rdi]
0x180197f73  lea     r12, aUpdateagentDll; "UpdateAgent.dll"
0x180197f7a  test    rcx, rcx
0x180197f7d  jz      short loc_180197F9C
0x180197f7f  mov     rax, [r14+10h]
0x180197f83  lea     r8, aFcacquirerloca_1; "FCAcquirerLocalRepository: Searching %w"...
0x180197f8a  mov     r9, r12
0x180197f8d  mov     [rsp+60h+var_40], rax
0x180197f92  mov     edx, 2
0x180197f97  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197f9c  mov     rcx, [r14+10h]
0x180197fa0  lea     r9, [rbp+lpFileName]
0x180197fa4  xor     r8d, r8d
0x180197fa7  mov     rdx, r12
0x180197faa  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180197faf  mov     esi, eax
0x180197fb1  test    eax, eax
0x180197fb3  jns     short loc_180198012
0x180197fb5  mov     rdi, [rdi]
0x180197fb8  xor     ecx, ecx
0x180197fba  test    rdi, rdi
0x180197fbd  jz      short loc_180198004
0x180197fbf  mov     rcx, [rdi]
0x180197fc2  mov     edx, esi
0x180197fc4  mov     rax, [rcx+20h]
0x180197fc8  mov     rcx, rdi
0x180197fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197fd0  neg     eax
0x180197fd2  mov     dword ptr [rsp+60h+var_38], esi
0x180197fd6  lea     r9, aCfcacquirerloc_4; "CFCAcquirerLocalRepository::CopyDeploym"...
0x180197fdd  mov     dword ptr [rsp+60h+var_40], 0F1h
0x180197fe5  sbb     edx, edx
0x180197fe7  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180197fee  add     edx, 4
0x180197ff1  mov     rcx, rdi
0x180197ff4  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197ff9  mov     ecx, eax
0x180197ffb  test    eax, eax
0x180197ffd  jns     short loc_180198004
0x180197fff  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180198004  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180198009  mov     r15, [rbp+lpFileName]
0x18019800d  jmp     loc_1801984BF
0x180198012  mov     r15, [rbp+lpFileName]
0x180198016  mov     rcx, r15; lpFileName
0x180198019  call    cs:__imp_GetFileAttributesW
0x180198020  nop     dword ptr [rax+rax+00h]
0x180198025  mov     esi, eax
0x180198027  cmp     eax, 0FFFFFFFFh
0x18019802a  jz      short loc_180198036
0x18019802c  shr     esi, 4
0x18019802f  not     esi
0x180198031  and     esi, 1
0x180198034  jmp     short loc_180198038
0x180198036  xor     esi, esi
0x180198038  xor     ecx, ecx
0x18019803a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019803f  xor     ecx, ecx
0x180198041  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180198046  test    esi, esi
0x180198048  jnz     short loc_18019809F
0x18019804a  mov     rcx, [rdi]
0x18019804d  test    rcx, rcx
0x180198050  jz      short loc_180198064
0x180198052  mov     r9, r15
0x180198055  lea     r8, aFcacquirerloca; "FCAcquirerLocalRepository: Couldn't fin"...
0x18019805c  lea     edx, [rsi+4]
0x18019805f  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180198064  mov     rdi, [rdi]
0x180198067  xor     ecx, ecx
0x180198069  mov     r14d, 80070002h
0x18019806f  mov     esi, r14d
0x180198072  test    rdi, rdi
0x180198075  jz      loc_1801984BA
0x18019807b  mov     rax, [rdi]
0x18019807e  mov     edx, r14d
0x180198081  mov     rcx, rdi
0x180198084  mov     rax, [rax+20h]
0x180198088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019808d  mov     dword ptr [rsp+60h+var_38], r14d
0x180198092  mov     dword ptr [rsp+60h+var_40], 0F7h
0x18019809a  jmp     loc_180198492
0x18019809f  mov     r14, [rbp+var_28]
0x1801980a3  lea     r9, [rbp+lpNewFileName]
0x1801980a7  mov     rcx, r14
0x1801980aa  xor     r8d, r8d
0x1801980ad  mov     rdx, r12
0x1801980b0  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1801980b5  mov     esi, eax
0x1801980b7  test    eax, eax
0x1801980b9  jns     loc_180198378
0x1801980bf  mov     rdi, [rdi]
0x1801980c2  xor     ecx, ecx
0x1801980c4  test    rdi, rdi
0x1801980c7  jz      short loc_18019810E
0x1801980c9  mov     rax, [rdi]
0x1801980cc  mov     edx, esi
0x1801980ce  mov     rcx, rdi
0x1801980d1  mov     rax, [rax+20h]
0x1801980d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801980da  mov     dword ptr [rsp+60h+var_38], esi
0x1801980de  mov     dword ptr [rsp+60h+var_40], 0FAh
0x1801980e6  neg     eax
0x1801980e8  lea     r9, aCfcacquirerloc_4; "CFCAcquirerLocalRepository::CopyDeploym"...
0x1801980ef  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1801980f6  mov     rcx, rdi
0x1801980f9  sbb     edx, edx
0x1801980fb  add     edx, 4
0x1801980fe  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180198103  mov     ecx, eax
0x180198105  test    eax, eax
0x180198107  jns     short loc_18019810E
0x180198109  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019810e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180198113  mov     r13, [rbp+lpNewFileName]
0x180198117  jmp     loc_1801984BF
0x18019811c  lea     r8, [rbp+phModule]; phModule
0x180198120  mov     ecx, 6; dwFlags
0x180198125  lea     rdx, ?Create@CFCAcquirerLocalRepository@@SAJPEAPEAVIFCAcquirerLocalRepository@@@Z; lpModuleName
0x18019812c  call    cs:__imp_GetModuleHandleExW
0x180198133  nop     dword ptr [rax+rax+00h]
0x180198138  test    eax, eax
0x18019813a  jnz     short loc_18019819F
0x18019813c  call    cs:__imp_GetLastError
0x180198143  nop     dword ptr [rax+rax+00h]
0x180198148  mov     esi, eax
0x18019814a  test    eax, eax
0x18019814c  jnz     short loc_180198157
0x18019814e  mov     esi, 80004005h
0x180198153  xor     ecx, ecx
0x180198155  jmp     short loc_18019816D
0x180198157  jle     short loc_180198162
0x180198159  movzx   esi, ax
0x18019815c  or      esi, 80070000h
0x180198162  mov     ecx, r12d
0x180198165  test    esi, esi
0x180198167  jns     loc_1801984BA
0x18019816d  mov     rdi, [r14-8]
0x180198171  mov     r12d, esi
0x180198174  test    rdi, rdi
0x180198177  jz      loc_1801984BA
0x18019817d  mov     rax, [rdi]
0x180198180  mov     edx, esi
0x180198182  mov     rcx, rdi
0x180198185  mov     rax, [rax+20h]
0x180198189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019818e  mov     dword ptr [rsp+60h+var_38], esi
0x180198192  mov     dword ptr [rsp+60h+var_40], 102h
0x18019819a  jmp     loc_180198492
0x18019819f  mov     rcx, [rbp+phModule]; hModule
0x1801981a3  call    FormModuleFullPathName
0x1801981a8  mov     rbx, rax
0x1801981ab  test    rax, rax
0x1801981ae  jnz     short loc_180198216
0x1801981b0  mov     rbx, r12
0x1801981b3  call    cs:__imp_GetLastError
0x1801981ba  nop     dword ptr [rax+rax+00h]
0x1801981bf  mov     esi, eax
0x1801981c1  test    eax, eax
0x1801981c3  jnz     short loc_1801981CE
0x1801981c5  mov     esi, 80004005h
0x1801981ca  xor     ecx, ecx
0x1801981cc  jmp     short loc_1801981E4
0x1801981ce  jle     short loc_1801981D9
0x1801981d0  movzx   esi, ax
0x1801981d3  or      esi, 80070000h
0x1801981d9  mov     ecx, r12d
0x1801981dc  test    esi, esi
0x1801981de  jns     loc_1801984BA
0x1801981e4  mov     rdi, [r14-8]
0x1801981e8  mov     r12d, esi
0x1801981eb  test    rdi, rdi
0x1801981ee  jz      loc_1801984BA
0x1801981f4  mov     rax, [rdi]
0x1801981f7  mov     edx, esi
0x1801981f9  mov     rcx, rdi
0x1801981fc  mov     rax, [rax+20h]
0x180198200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198205  mov     dword ptr [rsp+60h+var_38], esi
0x180198209  mov     dword ptr [rsp+60h+var_40], 107h
0x180198211  jmp     loc_180198492
0x180198216  lea     rdi, [r14-8]
0x18019821a  mov     rcx, [rdi]
0x18019821d  test    rcx, rcx
0x180198220  jz      short loc_180198236
0x180198222  mov     r9, rbx
0x180198225  lea     r8, aFcacquirerloca_4; "FCAcquirerLocalRepository: Module DLL P"...
0x18019822c  mov     edx, 2
0x180198231  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180198236  xor     r9d, r9d
0x180198239  mov     [rsp+60h+var_40], r12; __int64
0x18019823e  lea     r8, [rbp+var_18]
0x180198242  mov     rcx, rbx; Src
0x180198245  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
  ... truncated ...
```
