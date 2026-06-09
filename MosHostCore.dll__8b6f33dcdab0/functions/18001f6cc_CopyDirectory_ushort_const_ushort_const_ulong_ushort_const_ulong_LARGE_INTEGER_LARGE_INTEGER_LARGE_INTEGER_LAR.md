# CopyDirectory(ushort const *,ushort const *,ulong,ushort const * *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,void (*)(void *))

- ea: `0x18001f6cc`
- end: `0x18001fdc7`
- name: `?CopyDirectory@@YAJPEBG0KPEAPEBGP6AKT_LARGE_INTEGER@@222KKPEAX33@Z3PEAHP6AX3@Z@Z`
- size: `1787`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *lpData, LPBOOL pbCancel, void (*)(void *))`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000c1ec`
- `0x18001f6cc`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180008e00`
- `0x18001f6a8`
- `0x18001f6cc`
- `0x18001fdd0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f78b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f78b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f931`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f931`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f861`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f95c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f97a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001fa1f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001fa40`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f861`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f95c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f97a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001fa1f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001fa40`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f88d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f88d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f7e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f7e8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001f781`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001f781`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fb1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fb39`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fb1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001fb39`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001fb7d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001fb7d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001fc2a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001fc2a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f758`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f834`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f758`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f834`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001f87a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001f87a`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001f9b5`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001fa7b`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001fbb8`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001f9b5`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001fa7b`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001fbb8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18001f80a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18001f80a`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001faa6`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001fbe3`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001faa6`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001fbe3`

## string_xrefs

- `0x18001f751`: `CopyDirectory`
- `0x18001f7b9`: `CopyDirectory`
- `0x18001f828`: `CopyDirectory`
- `0x18001f871`: `CopyDirectory`
- `0x18001f89b`: `CopyDirectory`
- `0x18001f9a3`: `[DirectoryUtils] Copying directory from %ls to %ls`
- `0x18001fa69`: `[DirectoryUtils] Copying file from %ls to %ls`
- `0x18001fba3`: `[DirectoryUtils] Overwriting file from %ls to %ls`

## pseudocode

```c
__int64 __fastcall CopyDirectory(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4,
        unsigned int (*a5)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *lpData,
        LPBOOL pbCancel,
        void (*a8)(void *))
{
  void *v11; // rdi
  int v12; // r8d
  int v13; // ecx
  unsigned int v14; // ebx
  signed int LastError; // eax
  int v16; // r8d
  int v17; // ecx
  unsigned int v18; // eax
  HRESULT v19; // eax
  int v20; // r8d
  char *FirstFileW; // r15
  bool i; // zf
  int v23; // edx
  int v24; // edx
  __int64 v25; // rdi
  signed int v26; // eax
  HANDLE FileW; // [rsp+40h] [rbp-C0h] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 **v30; // [rsp+50h] [rbp-B0h]
  void *v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[36]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v34[3]; // [rsp+90h] [rbp-70h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPathIn[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR PathName[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR pszPathOut[264]; // [rsp+730h] [rbp+630h] BYREF

  v30 = a4;
  v11 = lpData;
  v31 = lpData;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v32 = -1;
  if ( !a4 )
  {
    v12 = 635;
    v13 = -2147024809;
LABEL_3:
    v14 = ZTraceReportOriginationNoThis(v13, "CopyDirectory", v12);
    goto LABEL_102;
  }
  if ( pbCancel && *pbCancel )
  {
    v12 = 637;
    v13 = -2147023673;
    goto LABEL_3;
  }
  if ( !CreateDirectoryW(a2, 0) && GetLastError() != 183 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v12 = 641;
LABEL_14:
    v13 = LastError;
    goto LABEL_3;
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x2200000u, 0);
  FileInformation = 0;
  if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
    && (FileInformation & 0x410) != 0x10 )
  {
    v16 = 661;
    v17 = -2147418113;
LABEL_18:
    v18 = ZTraceReportOriginationNoThis(v17, "CopyDirectory", v16);
    goto LABEL_19;
  }
  v19 = PathCchCombine(pszPathOut, 0x104u, a1, L"*");
  if ( v19 < 0 )
  {
    v20 = 665;
    goto LABEL_22;
  }
  FirstFileW = (char *)FindFirstFileW(pszPathOut, &FindFileData);
  v32 = (__int64)FirstFileW;
  for ( i = FirstFileW + 1 == 0; ; i = !FindNextFileW(FirstFileW, &FindFileData) )
  {
    if ( i )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
      if ( GetLastError() == 2 || GetLastError() == 5 || GetLastError() == 18 )
      {
        v14 = 0;
        goto LABEL_102;
      }
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v12 = 783;
      goto LABEL_14;
    }
    if ( pbCancel && *pbCancel )
    {
      v16 = 673;
      v17 = -2147023673;
      goto LABEL_18;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      break;
    v19 = PathCchCombine(PathName, 0x104u, a1, FindFileData.cFileName);
    if ( v19 < 0 )
    {
      v20 = 720;
      goto LABEL_22;
    }
    v19 = PathCchCombine(pszPathIn, 0x104u, a2, FindFileData.cFileName);
    if ( v19 < 0 )
    {
      v20 = 721;
      goto LABEL_22;
    }
    ZTraceHelperNoThis(5, "CopyDirectory", 723, "[DirectoryUtils] Copying file from %ls to %ls", PathName, pszPathIn);
    if ( CopyFileExW(PathName, pszPathIn, MigrationEngine::s_CopyProgressCallback, v11, pbCancel, 1u) )
    {
      v19 = CopyFileTimes(PathName, pszPathIn);
      if ( v19 < 0 )
      {
        v20 = 728;
        goto LABEL_22;
      }
    }
    else
    {
      memset(v34, 0, 36);
      memset(v33, 0, sizeof(v33));
      if ( GetLastError() != 80 && GetLastError() != 5 )
      {
        v26 = GetLastError();
        if ( v26 )
        {
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
        }
        else
        {
          v26 = -2143748092;
        }
        v16 = 738;
        goto LABEL_69;
      }
      if ( !GetFileAttributesExW(PathName, GetFileExInfoStandard, v34) )
      {
        v26 = GetLastError();
        if ( v26 )
        {
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
        }
        else
        {
          v26 = -2143748092;
        }
        v16 = 740;
        goto LABEL_69;
      }
      if ( !GetFileAttributesExW(pszPathIn, GetFileExInfoStandard, v33) )
      {
        v26 = GetLastError();
        if ( v26 )
        {
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
        }
        else
        {
          v26 = -2143748092;
        }
        v16 = 741;
        goto LABEL_69;
      }
      if ( (v34[0] & 1) != (v33[0] & 1) || *(_QWORD *)((char *)&v34[1] + 12) != *(_QWORD *)&v33[28] )
      {
        if ( (v33[0] & 1) != 0 && !SetFileAttributesW(pszPathIn, *(_DWORD *)v33 & 0xFFFFFFFE) )
        {
          v26 = GetLastError();
          if ( v26 )
          {
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
          }
          else
          {
            v26 = -2143748092;
          }
          v16 = 758;
          goto LABEL_69;
        }
        ZTraceHelperNoThis(
          5,
          "CopyDirectory",
          761,
          "[DirectoryUtils] Overwriting file from %ls to %ls",
          PathName,
          pszPathIn);
        if ( !CopyFileExW(PathName, pszPathIn, MigrationEngine::s_CopyProgressCallback, v11, pbCancel, 0) )
        {
          v26 = GetLastError();
          if ( v26 )
          {
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
          }
          else
          {
            v26 = -2143748092;
          }
          v16 = 762;
LABEL_69:
          v17 = v26;
          goto LABEL_18;
        }
        v19 = CopyFileTimes(PathName, pszPathIn);
        if ( v19 < 0 )
        {
          v20 = 765;
          goto LABEL_22;
        }
      }
    }
    if ( a8 )
      ((void (__fastcall *)(void *))a8)(v11);
LABEL_60:
    ;
  }
  v23 = FindFileData.cFileName[0] - 46;
  if ( FindFileData.cFileName[0] == 46 )
    v23 = FindFileData.cFileName[1];
  if ( !v23 )
    goto LABEL_60;
  v24 = FindFileData.cFileName[0] - 46;
  if ( FindFileData.cFileName[0] == 46 )
  {
    v24 = FindFileData.cFileName[1] - 46;
    if ( FindFileData.cFileName[1] == 46 )
      v24 = FindFileData.cFileName[2];
  }
  if ( !v24 )
    goto LABEL_60;
  v25 = 0;
  do
  {
    if ( CompareStringOrdinal(FindFileData.cFileName, -1, v30[v25], -1, 1) == 2 )
    {
      v11 = v31;
      goto LABEL_60;
    }
    v25 = (unsigned int)(v25 + 1);
  }
  while ( !(_DWORD)v25 );
  v19 = PathCchCombine(pszPathIn, 0x104u, a1, FindFileData.cFileName);
  if ( v19 < 0 )
  {
    v20 = 700;
  }
  else
  {
    v19 = PathCchCombine(PathName, 0x104u, a2, FindFileData.cFileName);
    if ( v19 < 0 )
    {
      v20 = 701;
    }
    else
    {
      ZTraceHelperNoThis(
        5,
        "CopyDirectory",
        703,
        "[DirectoryUtils] Copying directory from %ls to %ls",
        pszPathIn,
        PathName);
      v11 = v31;
      v19 = CopyDirectory(
              pszPathIn,
              PathName,
              1u,
              (const unsigned __int16 **)v30,
              MigrationEngine::s_CopyProgressCallback,
              v31,
              pbCancel,
              a8);
      if ( v19 >= 0 )
        goto LABEL_60;
      v20 = 712;
    }
  }
LABEL_22:
  v18 = ZTraceReportPropagationNoThis(v19, "CopyDirectory", v20);
LABEL_19:
  v14 = v18;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
LABEL_102:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
  return v14;
}

```

## disassembly

```asm
0x18001f6cc  mov     [rsp-8+arg_10], rbx
0x18001f6d1  push    rbp
0x18001f6d2  push    rsi
0x18001f6d3  push    rdi
0x18001f6d4  push    r12
0x18001f6d6  push    r13
0x18001f6d8  push    r14
0x18001f6da  push    r15
0x18001f6dc  lea     rbp, [rsp-850h]
0x18001f6e4  sub     rsp, 950h
0x18001f6eb  mov     rax, cs:__security_cookie
0x18001f6f2  xor     rax, rsp
0x18001f6f5  mov     [rbp+880h+var_40], rax
0x18001f6fc  mov     rbx, r9
0x18001f6ff  mov     [rsp+980h+var_930], rbx
0x18001f704  mov     r14, rdx
0x18001f707  mov     r12, rcx
0x18001f70a  mov     rdi, [rbp+880h+lpData]
0x18001f711  mov     [rsp+980h+var_928], rdi
0x18001f716  mov     rsi, [rbp+880h+pbCancel]
0x18001f71d  mov     r13, [rbp+880h+arg_38]
0x18001f724  xor     edx, edx; Val
0x18001f726  mov     r8d, 250h; Size
0x18001f72c  lea     rcx, [rbp+880h+FindFileData]; void *
0x18001f730  call    memset_0
0x18001f735  mov     [rsp+980h+var_920], 0FFFFFFFFFFFFFFFFh
0x18001f73e  xor     r15d, r15d
0x18001f741  test    rbx, rbx
0x18001f744  jnz     short loc_18001F765
0x18001f746  mov     r8d, 27Bh
0x18001f74c  mov     ecx, 80070057h
0x18001f751  lea     rdx, aCopydirectory; "CopyDirectory"
0x18001f758  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18001f75e  mov     ebx, eax
0x18001f760  jmp     loc_18001FD91
0x18001f765  test    rsi, rsi
0x18001f768  jz      short loc_18001F77C
0x18001f76a  cmp     [rsi], r15d
0x18001f76d  jz      short loc_18001F77C
0x18001f76f  mov     r8d, 27Dh
0x18001f775  mov     ecx, 800704C7h
0x18001f77a  jmp     short loc_18001F751
0x18001f77c  xor     edx, edx; lpSecurityAttributes
0x18001f77e  mov     rcx, r14; lpPathName
0x18001f781  call    cs:__imp_CreateDirectoryW
0x18001f787  test    eax, eax
0x18001f789  jnz     short loc_18001F7C4
0x18001f78b  call    cs:__imp_GetLastError
0x18001f791  cmp     eax, 0B7h
0x18001f796  jz      short loc_18001F7C4
0x18001f798  call    cs:__imp_GetLastError
0x18001f79e  test    eax, eax
0x18001f7a0  jz      short loc_18001F7AE
0x18001f7a2  jle     short loc_18001F7B3
0x18001f7a4  movzx   eax, ax
0x18001f7a7  or      eax, 80070000h
0x18001f7ac  jmp     short loc_18001F7B3
0x18001f7ae  mov     eax, 80390004h
0x18001f7b3  mov     r8d, 281h
0x18001f7b9  lea     rdx, aCopydirectory; "CopyDirectory"
0x18001f7c0  mov     ecx, eax
0x18001f7c2  jmp     short loc_18001F758
0x18001f7c4  mov     [rsp+980h+hTemplateFile], r15; hTemplateFile
0x18001f7c9  mov     [rsp+980h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001f7d1  mov     [rsp+980h+dwCreationDisposition], 3; dwCreationDisposition
0x18001f7d9  xor     r9d, r9d; lpSecurityAttributes
0x18001f7dc  mov     edx, 80000000h; dwDesiredAccess
0x18001f7e1  lea     r8d, [r9+1]; dwShareMode
0x18001f7e5  mov     rcx, r14; lpFileName
0x18001f7e8  call    cs:__imp_CreateFileW
0x18001f7ee  mov     [rsp+980h+var_940], rax
0x18001f7f3  mov     [rsp+980h+FileInformation], r15
0x18001f7f8  mov     r9d, 8; dwBufferSize
0x18001f7fe  lea     r8, [rsp+980h+FileInformation]; lpFileInformation
0x18001f803  lea     edx, [r9+1]; FileInformationClass
0x18001f807  mov     rcx, rax; hFile
0x18001f80a  call    cs:__imp_GetFileInformationByHandleEx
0x18001f810  test    eax, eax
0x18001f812  jz      short loc_18001F84B
0x18001f814  mov     eax, dword ptr [rsp+980h+FileInformation]
0x18001f818  and     eax, 410h
0x18001f81d  cmp     eax, 10h
0x18001f820  jz      short loc_18001F84B
0x18001f822  mov     r8d, 295h
0x18001f828  lea     rdx, aCopydirectory; "CopyDirectory"
0x18001f82f  mov     ecx, 8000FFFFh
0x18001f834  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18001f83a  mov     ebx, eax
0x18001f83c  lea     rcx, [rsp+980h+var_940]
0x18001f841  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f846  jmp     loc_18001FD91
0x18001f84b  lea     r9, asc_18002A358; "*"
0x18001f852  mov     r8, r12; pszPathIn
0x18001f855  mov     edx, 104h; cchPathOut
0x18001f85a  lea     rcx, [rbp+880h+pszPathOut]; pszPathOut
0x18001f861  call    cs:__imp_PathCchCombine
0x18001f867  test    eax, eax
0x18001f869  jns     short loc_18001F882
0x18001f86b  mov     r8d, 299h
0x18001f871  lea     rdx, aCopydirectory; "CopyDirectory"
0x18001f878  mov     ecx, eax
0x18001f87a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18001f880  jmp     short loc_18001F83A
0x18001f882  lea     rdx, [rbp+880h+FindFileData]; lpFindFileData
0x18001f886  lea     rcx, [rbp+880h+pszPathOut]; lpFileName
0x18001f88d  call    cs:__imp_FindFirstFileW
0x18001f893  mov     r15, rax
0x18001f896  mov     [rsp+980h+var_920], rax
0x18001f89b  lea     rbx, aCopydirectory; "CopyDirectory"
0x18001f8a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f8a6  jz      loc_18001FD3B
0x18001f8ac  mov     ecx, 2Eh ; '.'
0x18001f8b1  test    rsi, rsi
0x18001f8b4  jz      short loc_18001F8BF
0x18001f8b6  cmp     dword ptr [rsi], 0
0x18001f8b9  jnz     loc_18001FC37
0x18001f8bf  test    byte ptr [rbp+880h+FindFileData.dwFileAttributes], 10h
0x18001f8c3  jz      loc_18001FA0C
0x18001f8c9  movzx   edx, [rbp+880h+FindFileData.cFileName]
0x18001f8cd  movzx   eax, cx
0x18001f8d0  sub     edx, eax
0x18001f8d2  jnz     short loc_18001F8E2
0x18001f8d4  movzx   edx, [rbp+880h+FindFileData.cFileName+2]
0x18001f8d8  xor     eax, eax
0x18001f8da  movzx   ecx, ax
0x18001f8dd  sub     edx, ecx
0x18001f8df  lea     ecx, [rax+2Eh]
0x18001f8e2  test    edx, edx
0x18001f8e4  jz      loc_18001FC23
0x18001f8ea  movzx   edx, [rbp+880h+FindFileData.cFileName]
0x18001f8ee  movzx   eax, cx
0x18001f8f1  sub     edx, eax
0x18001f8f3  jnz     short loc_18001F90B
0x18001f8f5  movzx   edx, [rbp+880h+FindFileData.cFileName+2]
0x18001f8f9  movzx   eax, cx
0x18001f8fc  sub     edx, eax
0x18001f8fe  jnz     short loc_18001F90B
0x18001f900  movzx   edx, [rbp+880h+FindFileData.cFileName+4]
0x18001f904  xor     eax, eax
0x18001f906  movzx   ecx, ax
0x18001f909  sub     edx, ecx
0x18001f90b  test    edx, edx
0x18001f90d  jz      loc_18001FC23
0x18001f913  xor     edi, edi
0x18001f915  mov     [rsp+980h+dwCreationDisposition], 1; bIgnoreCase
0x18001f91d  or      r9d, 0FFFFFFFFh; cchCount2
0x18001f921  mov     rax, [rsp+980h+var_930]
0x18001f926  mov     r8, [rax+rdi*8]; lpString2
0x18001f92a  or      edx, r9d; cchCount1
0x18001f92d  lea     rcx, [rbp+880h+FindFileData.cFileName]; lpString1
0x18001f931  call    cs:__imp_CompareStringOrdinal
0x18001f937  cmp     eax, 2
0x18001f93a  jz      loc_18001FC1E
0x18001f940  inc     edi
0x18001f942  cmp     edi, 1
0x18001f945  jb      short loc_18001F915
0x18001f947  lea     r9, [rbp+880h+FindFileData.cFileName]; pszMore
0x18001f94b  mov     r8, r12; pszPathIn
0x18001f94e  mov     edi, 104h
0x18001f953  mov     edx, edi; cchPathOut
0x18001f955  lea     rcx, [rbp+880h+pszPathIn]; pszPathOut
0x18001f95c  call    cs:__imp_PathCchCombine
0x18001f962  test    eax, eax
0x18001f964  js      loc_18001FC55
0x18001f96a  lea     r9, [rbp+880h+FindFileData.cFileName]; pszMore
0x18001f96e  mov     r8, r14; pszPathIn
0x18001f971  mov     edx, edi; cchPathOut
0x18001f973  lea     rcx, [rbp+880h+PathName]; pszPathOut
0x18001f97a  call    cs:__imp_PathCchCombine
0x18001f980  mov     rdx, rbx
0x18001f983  test    eax, eax
0x18001f985  js      loc_18001FC4A
0x18001f98b  lea     rax, [rbp+880h+PathName]
0x18001f992  mov     qword ptr [rsp+980h+dwFlagsAndAttributes], rax
0x18001f997  lea     rax, [rbp+880h+pszPathIn]
0x18001f99e  mov     qword ptr [rsp+980h+dwCreationDisposition], rax
0x18001f9a3  lea     r9, aDirectoryutils; "[DirectoryUtils] Copying directory from"...
0x18001f9aa  mov     r8d, 2BFh
0x18001f9b0  mov     ecx, 5
0x18001f9b5  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001f9bb  mov     [rsp+980h+var_948], r13; void (*)(void *)
0x18001f9c0  mov     [rsp+980h+hTemplateFile], rsi; pbCancel
0x18001f9c5  mov     rdi, [rsp+980h+var_928]
0x18001f9ca  mov     qword ptr [rsp+980h+dwFlagsAndAttributes], rdi; lpData
0x18001f9cf  lea     rax, ?s_CopyProgressCallback@MigrationEngine@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; MigrationEngine::s_CopyProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18001f9d6  mov     qword ptr [rsp+980h+dwCreationDisposition], rax; unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *)
0x18001f9db  mov     r9, [rsp+980h+var_930]; unsigned __int16 **
0x18001f9e0  mov     r8d, 1; unsigned int
0x18001f9e6  lea     rdx, [rbp+880h+PathName]; unsigned __int16 *
0x18001f9ed  lea     rcx, [rbp+880h+pszPathIn]; unsigned __int16 *
0x18001f9f4  call    ?CopyDirectory@@YAJPEBG0KPEAPEBGP6AKT_LARGE_INTEGER@@222KKPEAX33@Z3PEAHP6AX3@Z@Z; CopyDirectory(ushort const *,ushort const *,ulong,ushort const * *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,void (*)(void *))
0x18001f9f9  test    eax, eax
0x18001f9fb  jns     loc_18001FC23
0x18001fa01  mov     r8d, 2C8h
0x18001fa07  jmp     loc_18001FC5B
0x18001fa0c  lea     r9, [rbp+880h+FindFileData.cFileName]; pszMore
0x18001fa10  mov     r8, r12; pszPathIn
0x18001fa13  mov     edx, 104h; cchPathOut
0x18001fa18  lea     rcx, [rbp+880h+PathName]; pszPathOut
0x18001fa1f  call    cs:__imp_PathCchCombine
0x18001fa25  test    eax, eax
0x18001fa27  js      loc_18001FD30
0x18001fa2d  lea     r9, [rbp+880h+FindFileData.cFileName]; pszMore
0x18001fa31  mov     r8, r14; pszPathIn
0x18001fa34  mov     edx, 104h; cchPathOut
0x18001fa39  lea     rcx, [rbp+880h+pszPathIn]; pszPathOut
0x18001fa40  call    cs:__imp_PathCchCombine
0x18001fa46  mov     rdx, rbx
0x18001fa49  test    eax, eax
0x18001fa4b  js      loc_18001FD25
0x18001fa51  lea     rax, [rbp+880h+pszPathIn]
0x18001fa58  mov     qword ptr [rsp+980h+dwFlagsAndAttributes], rax
0x18001fa5d  lea     rax, [rbp+880h+PathName]
0x18001fa64  mov     qword ptr [rsp+980h+dwCreationDisposition], rax
0x18001fa69  lea     r9, aDirectoryutils_0; "[DirectoryUtils] Copying file from %ls "...
0x18001fa70  mov     r8d, 2D3h
0x18001fa76  mov     ecx, 5
0x18001fa7b  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001fa81  mov     [rsp+980h+dwFlagsAndAttributes], 1; dwCopyFlags
0x18001fa89  mov     qword ptr [rsp+980h+dwCreationDisposition], rsi; pbCancel
0x18001fa8e  mov     r9, rdi; lpData
0x18001fa91  lea     r8, ?s_CopyProgressCallback@MigrationEngine@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18001fa98  lea     rdx, [rbp+880h+pszPathIn]; lpNewFileName
0x18001fa9f  lea     rcx, [rbp+880h+PathName]; lpExistingFileName
0x18001faa6  call    cs:__imp_CopyFileExW
0x18001faac  test    eax, eax
0x18001faae  jz      short loc_18001FAD6
0x18001fab0  lea     rdx, [rbp+880h+pszPathIn]; LPCWSTR
0x18001fab7  lea     rcx, [rbp+880h+PathName]; lpFileName
0x18001fabe  call    CopyFileTimes
0x18001fac3  test    eax, eax
0x18001fac5  jns     loc_18001FC0C
0x18001facb  mov     r8d, 2D8h
0x18001fad1  jmp     loc_18001FC5B
0x18001fad6  xorps   xmm0, xmm0
0x18001fad9  xor     eax, eax
0x18001fadb  movups  [rbp+880h+var_8F0], xmm0
0x18001fadf  movups  xmmword ptr [rbp+880h+var_8E0], xmm0
0x18001fae3  mov     dword ptr [rbp+880h+var_8E0+10h], eax
0x18001fae6  xorps   xmm1, xmm1
0x18001fae9  movups  [rsp+980h+var_918], xmm1
0x18001faee  movups  xmmword ptr [rsp+980h+var_908], xmm1
0x18001faf3  mov     dword ptr [rbp+880h+var_908+10h], eax
0x18001faf6  call    cs:__imp_GetLastError
0x18001fafc  cmp     eax, 50h ; 'P'
0x18001faff  jz      short loc_18001FB10
0x18001fb01  call    cs:__imp_GetLastError
0x18001fb07  cmp     eax, 5
0x18001fb0a  jnz     loc_18001FC63
0x18001fb10  lea     r8, [rbp+880h+var_8F0]; lpFileInformation
0x18001fb14  xor     edx, edx; fInfoLevelId
0x18001fb16  lea     rcx, [rbp+880h+PathName]; lpFileName
0x18001fb1d  call    cs:__imp_GetFileAttributesExW
0x18001fb23  test    eax, eax
0x18001fb25  jz      loc_18001FCFF
0x18001fb2b  lea     r8, [rsp+980h+var_918]; lpFileInformation
0x18001fb30  xor     edx, edx; fInfoLevelId
0x18001fb32  lea     rcx, [rbp+880h+pszPathIn]; lpFileName
0x18001fb39  call    cs:__imp_GetFileAttributesExW
0x18001fb3f  test    eax, eax
0x18001fb41  jz      loc_18001FCDC
0x18001fb47  mov     cl, byte ptr [rsp+980h+var_918]
0x18001fb4b  and     cl, 1
0x18001fb4e  mov     al, byte ptr [rbp+880h+var_8F0]
0x18001fb51  and     al, 1
0x18001fb53  cmp     al, cl
0x18001fb55  jnz     short loc_18001FB6B
0x18001fb57  mov     eax, dword ptr [rbp+880h+var_908+0Ch]
0x18001fb5a  cmp     dword ptr [rbp+880h+var_8E0+0Ch], eax
0x18001fb5d  jnz     short loc_18001FB6B
0x18001fb5f  mov     eax, dword ptr [rbp+880h+var_908+10h]
0x18001fb62  cmp     dword ptr [rbp+880h+var_8E0+10h], eax
0x18001fb65  jz      loc_18001FC0C
0x18001fb6b  test    cl, cl
0x18001fb6d  jz      short loc_18001FB8B
0x18001fb6f  mov     edx, dword ptr [rsp+980h+var_918]
0x18001fb73  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18001fb76  lea     rcx, [rbp+880h+pszPathIn]; lpFileName
0x18001fb7d  call    cs:__imp_SetFileAttributesW
0x18001fb83  test    eax, eax
0x18001fb85  jz      loc_18001FC8E
0x18001fb8b  lea     rax, [rbp+880h+pszPathIn]
0x18001fb92  mov     qword ptr [rsp+980h+dwFlagsAndAttributes], rax
0x18001fb97  lea     rax, [rbp+880h+PathName]
0x18001fb9e  mov     qword ptr [rsp+980h+dwCreationDisposition], rax
0x18001fba3  lea     r9, aDirectoryutils_1; "[DirectoryUtils] Overwriting file from "...
0x18001fbaa  mov     r8d, 2F9h
0x18001fbb0  mov     rdx, rbx
0x18001fbb3  mov     ecx, 5
0x18001fbb8  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001fbbe  mov     [rsp+980h+dwFlagsAndAttributes], 0; dwCopyFlags
0x18001fbc6  mov     qword ptr [rsp+980h+dwCreationDisposition], rsi; pbCancel
0x18001fbcb  mov     r9, rdi; lpData
0x18001fbce  lea     r8, ?s_CopyProgressCallback@MigrationEngine@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18001fbd5  lea     rdx, [rbp+880h+pszPathIn]; lpNewFileName
0x18001fbdc  lea     rcx, [rbp+880h+PathName]; lpExistingFileName
0x18001fbe3  call    cs:__imp_CopyFileExW
0x18001fbe9  test    eax, eax
0x18001fbeb  jz      loc_18001FCB9
0x18001fbf1  lea     rdx, [rbp+880h+pszPathIn]; LPCWSTR
  ... truncated ...
```
