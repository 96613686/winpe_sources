# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x18001e850`
- end: `0x18001ee96`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1606`
- prototype: `__int64 __fastcall(const WCHAR *, int, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d80c`
- `0x18001e850`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800089c4`
- `0x1800089e4`
- `0x180018438`
- `0x180019fec`
- `0x18001e850`
- `0x18001ee9c`
- `0x18006b660`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ed9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee64`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001eb93`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001edd5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001eb93`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001edd5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001ec79`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001eca9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001ec79`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001eca9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001ebff`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001ebff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001eb36`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ed4a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ee46`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001eb36`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ed4a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ee46`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ec2f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ec2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ebdf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ebdf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ebb7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ec0a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ebb7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ec0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ea71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ea71`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001e9d9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001e9d9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18001eaa4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18001eaa4`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001e993`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001ea31`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001e993`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001ea31`

## string_xrefs

- `0x18001e8c7`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001e947`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001e9a6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001eb06`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001ecc3`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001ecdd`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001ed81`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001ee06`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001ee26`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(const WCHAR *a1, int a2, void *a3)
{
  WCHAR *v6; // rbx
  unsigned int v7; // ebx
  ULONG v9; // r8d
  HRESULT v10; // eax
  unsigned int LastError; // edi
  char *FirstFileW; // rsi
  const char *v13; // r9
  HRESULT v14; // eax
  HANDLE FileW; // rax
  __int64 v16; // rdi
  int v17; // eax
  unsigned int v18; // r14d
  DWORD v19; // r14d
  const char *v20; // r9
  const char *v21; // r9
  DWORD FileAttributesW; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  DWORD v30; // eax
  unsigned int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-B8h] BYREF
  char FileInformation[8]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v40[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[13]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v42; // [rsp+D0h] [rbp-30h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  hMem = 0;
  if ( !wcsncmp_0(a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPathIn,
      a1,
      -1);
    v6 = (WCHAR *)pszPathIn;
    if ( !pszPathIn )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      return v7;
    }
    v9 = 16;
  }
  else
  {
    pszPathIn = a1;
    v41[0] = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v41[1] = &pszPathIn;
    v42 = v41;
    v7 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           &hMem,
           v40);
    if ( v42 )
      (*(void (__fastcall **)(_QWORD *))(*v42 + 24LL))(v42);
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)v7,
        dwCreationDisposition);
      if ( hMem )
        LocalFree(hMem);
      return v7;
    }
    v6 = (WCHAR *)hMem;
    v9 = 1;
  }
  ppszPathOut = 0;
  v10 = PathAllocCombine(v6, L"*", v9, &ppszPathOut);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v10,
      dwCreationDisposition);
LABEL_93:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( v6 )
      LocalFree(v6);
    return LastError;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v13);
    goto LABEL_93;
  }
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      continue;
    }
    hMem = 0;
    v14 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, (PWSTR *)&hMem);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v14,
        dwCreationDisposition);
      goto LABEL_80;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( !DeleteFileW((LPCWSTR)hMem) )
      {
        if ( (a2 & 2) == 0 || GetLastError() != 5 )
        {
          v32 = 321;
LABEL_79:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v32,
                        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                        v21);
LABEL_80:
          if ( hMem )
            LocalFree(hMem);
LABEL_92:
          FindClose(FirstFileW);
          goto LABEL_93;
        }
        FileAttributesW = GetFileAttributesW((LPCWSTR)hMem);
        if ( (FileAttributesW & 1) == 0 )
        {
          v32 = 325;
          goto LABEL_79;
        }
        v23 = FileAttributesW & 0xFFFFFFFE;
        if ( !v23 )
          v23 = 128;
        SetFileAttributesW((LPCWSTR)hMem, v23);
        if ( !DeleteFileW((LPCWSTR)hMem) )
        {
          v32 = 336;
          goto LABEL_79;
        }
      }
      goto LABEL_52;
    }
    FileW = CreateFileW((LPCWSTR)hMem, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
    v16 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL && FileW )
    {
      pszPathIn = 0;
      if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &pszPathIn, 8u)
        && ((unsigned __int8)pszPathIn & 0x10) != 0
        && (((unsigned __int16)pszPathIn & 0x400) == 0
         || (HIDWORD(pszPathIn) & 0x10000000) != 0
         || HIDWORD(pszPathIn) == -2147483624) )
      {
        FindFileData.dwReserved0 = HIDWORD(pszPathIn);
        FindFileData.dwFileAttributes = (unsigned int)pszPathIn;
        v17 = wil::RemoveDirectoryRecursiveNoThrow(hMem, a2 & 0xFFFFFFFE, v16);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12C,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)(unsigned int)v17,
            dwCreationDisposition);
LABEL_31:
          CloseHandle((HANDLE)v16);
LABEL_32:
          if ( hMem )
            LocalFree(hMem);
          FindClose(FirstFileW);
          if ( ppszPathOut )
            LocalFree(ppszPathOut);
          if ( v6 )
            LocalFree(v6);
          return v18;
        }
LABEL_43:
        if ( v16 )
          CloseHandle((HANDLE)v16);
        goto LABEL_52;
      }
      v19 = GetLastError();
      CloseHandle((HANDLE)v16);
      SetLastError(v19);
      v16 = -1;
    }
    if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
    {
      v30 = GetLastError();
      if ( !v30 )
      {
        if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)v16);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_73;
      }
      v29 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x136, v31, (const char *)v30, dwCreationDisposition);
LABEL_65:
      v18 = v29;
      if ( (unsigned __int64)(v16 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_32;
      goto LABEL_31;
    }
    if ( !RemoveDirectoryW((LPCWSTR)hMem) )
    {
      v29 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x131,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              v20);
      goto LABEL_65;
    }
    if ( v16 != -1 )
      goto LABEL_43;
LABEL_52:
    if ( hMem )
      LocalFree(hMem);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  v24 = GetLastError();
  if ( v24 != 18 )
  {
    if ( !v24 )
      goto LABEL_73;
    v34 = v24;
    v33 = 348;
    goto LABEL_85;
  }
  if ( (a2 & 1) != 0 )
    goto LABEL_73;
  if ( a3 == (void *)-1LL )
  {
    if ( RemoveDirectoryW(v6) )
      goto LABEL_73;
    v27 = 381;
LABEL_62:
    v28 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            v26);
LABEL_63:
    LastError = v28;
    goto LABEL_92;
  }
  LODWORD(hMem) = 3;
  if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hMem, 4u) )
    goto LABEL_73;
  if ( GetLastError() == 5 )
  {
    v33 = 374;
    v34 = 5;
LABEL_85:
    v28 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v33, v25, (const char *)v34, dwCreationDisposition);
    goto LABEL_63;
  }
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
  {
    v27 = 369;
    goto LABEL_62;
  }
LABEL_73:
  FindClose(FirstFileW);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( v6 )
    LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x18001e850  mov     [rsp-8+arg_18], rbx
0x18001e855  push    rbp
0x18001e856  push    rsi
0x18001e857  push    rdi
0x18001e858  push    r12
0x18001e85a  push    r13
0x18001e85c  push    r14
0x18001e85e  push    r15
0x18001e860  lea     rbp, [rsp-240h]
0x18001e868  sub     rsp, 340h
0x18001e86f  mov     rax, cs:__security_cookie
0x18001e876  xor     rax, rsp
0x18001e879  mov     [rbp+270h+var_40], rax
0x18001e880  xor     r13d, r13d
0x18001e883  mov     r15, r8
0x18001e886  mov     r12d, edx
0x18001e889  mov     [rsp+370h+hMem], r13
0x18001e88e  lea     rdx, String2; "\\\\?\\"
0x18001e895  mov     rbx, rcx
0x18001e898  lea     r8d, [r13+4]; MaxCount
0x18001e89c  call    wcsncmp_0
0x18001e8a1  test    eax, eax
0x18001e8a3  jnz     short loc_18001E8F2
0x18001e8a5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e8a9  lea     rcx, [rsp+370h+pszPathIn]
0x18001e8ae  mov     rdx, rbx
0x18001e8b1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001e8b6  mov     rbx, [rsp+370h+pszPathIn]
0x18001e8bb  test    rbx, rbx
0x18001e8be  jnz     short loc_18001E8E7
0x18001e8c0  mov     rcx, [rbp+278h]; this
0x18001e8c7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e8ce  mov     ebx, 8007000Eh
0x18001e8d3  mov     edx, 104h; void *
0x18001e8d8  mov     r9d, ebx; char *
0x18001e8db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8e0  mov     eax, ebx
0x18001e8e2  jmp     loc_18001EE6C
0x18001e8e7  mov     r8d, 10h
0x18001e8ed  jmp     loc_18001E97F
0x18001e8f2  lea     rax, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18001e8f9  mov     [rsp+370h+pszPathIn], rbx
0x18001e8fe  mov     [rsp+370h+var_308], rax
0x18001e903  lea     rdx, [rsp+370h+var_310]
0x18001e908  lea     rax, [rsp+370h+pszPathIn]
0x18001e90d  mov     [rsp+370h+var_300], rax
0x18001e912  lea     rcx, [rsp+370h+hMem]
0x18001e917  lea     rax, [rsp+370h+var_308]
0x18001e91c  mov     [rbp+270h+var_2A0], rax
0x18001e920  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18001e925  mov     rcx, [rbp+270h+var_2A0]
0x18001e929  mov     ebx, eax
0x18001e92b  test    rcx, rcx
0x18001e92e  jz      short loc_18001E93C
0x18001e930  mov     rdx, [rcx]
0x18001e933  mov     rax, [rdx+18h]
0x18001e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e93c  test    ebx, ebx
0x18001e93e  jns     short loc_18001E974
0x18001e940  mov     rcx, [rbp+278h]; this
0x18001e947  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e94e  mov     r9d, ebx; char *
0x18001e951  mov     edx, 10Ch; void *
0x18001e956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e95b  mov     rcx, [rsp+370h+hMem]; hMem
0x18001e960  test    rcx, rcx
0x18001e963  jz      loc_18001E8E0
0x18001e969  call    cs:__imp_LocalFree
0x18001e96f  jmp     loc_18001E8E0
0x18001e974  mov     rbx, [rsp+370h+hMem]
0x18001e979  mov     r8d, 1; dwFlags
0x18001e97f  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x18001e984  mov     [rsp+370h+ppszPathOut], r13
0x18001e989  lea     rdx, pszMore; "*"
0x18001e990  mov     rcx, rbx; pszPathIn
0x18001e993  call    cs:__imp_PathAllocCombine
0x18001e999  mov     edi, eax
0x18001e99b  test    eax, eax
0x18001e99d  jns     short loc_18001E9BF
0x18001e99f  mov     rcx, [rbp+278h]; this
0x18001e9a6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e9ad  mov     r9d, eax; char *
0x18001e9b0  mov     edx, 111h; void *
0x18001e9b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9ba  jmp     loc_18001EE4C
0x18001e9bf  xor     edx, edx; Val
0x18001e9c1  lea     rcx, [rbp+270h+FindFileData]; void *
0x18001e9c5  mov     r8d, 250h; Size
0x18001e9cb  call    memset_0
0x18001e9d0  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x18001e9d5  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18001e9d9  call    cs:__imp_FindFirstFileW
0x18001e9df  mov     rsi, rax
0x18001e9e2  dec     rax
0x18001e9e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e9e9  ja      loc_18001EE1F
0x18001e9ef  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x18001e9f3  jz      short loc_18001EA1A
0x18001e9f5  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x18001e9fa  jnz     short loc_18001EA1A
0x18001e9fc  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x18001ea00  test    ax, ax
0x18001ea03  jz      loc_18001EC28
0x18001ea09  cmp     ax, 2Eh ; '.'
0x18001ea0d  jnz     short loc_18001EA1A
0x18001ea0f  cmp     [rbp+270h+FindFileData.cFileName+4], r13w
0x18001ea14  jz      loc_18001EC28
0x18001ea1a  lea     r9, [rsp+370h+hMem]; ppszPathOut
0x18001ea1f  mov     [rsp+370h+hMem], r13
0x18001ea24  mov     r8d, 18h; dwFlags
0x18001ea2a  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x18001ea2e  mov     rcx, rbx; pszPathIn
0x18001ea31  call    cs:__imp_PathAllocCombine
0x18001ea37  mov     edi, eax
0x18001ea39  test    eax, eax
0x18001ea3b  js      loc_18001EDFF
0x18001ea41  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x18001ea45  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18001ea4a  jz      loc_18001EBB7
0x18001ea50  xor     r9d, r9d; lpSecurityAttributes
0x18001ea53  mov     [rsp+370h+hTemplateFile], r13; hTemplateFile
0x18001ea58  mov     [rsp+370h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001ea60  mov     edx, 80010000h; dwDesiredAccess
0x18001ea65  mov     [rsp+370h+dwCreationDisposition], 3; int
0x18001ea6d  lea     r8d, [r9+1]; dwShareMode
0x18001ea71  call    cs:__imp_CreateFileW
0x18001ea77  mov     rdi, rax
0x18001ea7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ea7e  jz      loc_18001EB81
0x18001ea84  test    rax, rax
0x18001ea87  jz      loc_18001EB81
0x18001ea8d  mov     r9d, 8; dwBufferSize
0x18001ea93  mov     [rsp+370h+pszPathIn], r13
0x18001ea98  lea     r8, [rsp+370h+pszPathIn]; lpFileInformation
0x18001ea9d  mov     rcx, rax; hFile
0x18001eaa0  lea     edx, [r9+1]; FileInformationClass
0x18001eaa4  call    cs:__imp_GetFileInformationByHandleEx
0x18001eaaa  test    eax, eax
0x18001eaac  jz      loc_18001EB62
0x18001eab2  mov     rax, [rsp+370h+pszPathIn]
0x18001eab7  test    al, 10h
0x18001eab9  jz      loc_18001EB62
0x18001eabf  mov     ecx, dword ptr [rsp+370h+pszPathIn+4]
0x18001eac3  bt      eax, 0Ah
0x18001eac7  jnb     short loc_18001EADB
0x18001eac9  bt      ecx, 1Ch
0x18001eacd  jb      short loc_18001EADB
0x18001eacf  cmp     ecx, 80000018h
0x18001ead5  jnz     loc_18001EB62
0x18001eadb  mov     edx, r12d
0x18001eade  mov     [rbp+270h+FindFileData.dwReserved0], ecx
0x18001eae1  mov     rcx, [rsp+370h+hMem]
0x18001eae6  and     edx, 0FFFFFFFEh
0x18001eae9  mov     r8, rdi
0x18001eaec  mov     [rbp+270h+FindFileData.dwFileAttributes], eax
0x18001eaef  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18001eaf4  mov     r14d, eax
0x18001eaf7  test    eax, eax
0x18001eaf9  jns     loc_18001EBA7
0x18001eaff  mov     rcx, [rbp+278h]; this
0x18001eb06  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001eb0d  mov     r9d, eax; char *
0x18001eb10  mov     edx, 12Ch; void *
0x18001eb15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb1a  mov     rcx, rdi; hObject
0x18001eb1d  call    cs:__imp_CloseHandle
0x18001eb23  mov     rcx, [rsp+370h+hMem]; hMem
0x18001eb28  test    rcx, rcx
0x18001eb2b  jz      short loc_18001EB33
0x18001eb2d  call    cs:__imp_LocalFree
0x18001eb33  mov     rcx, rsi; hFindFile
0x18001eb36  call    cs:__imp_FindClose
0x18001eb3c  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x18001eb41  test    rcx, rcx
0x18001eb44  jz      short loc_18001EB4C
0x18001eb46  call    cs:__imp_LocalFree
0x18001eb4c  test    rbx, rbx
0x18001eb4f  jz      short loc_18001EB5A
0x18001eb51  mov     rcx, rbx; hMem
0x18001eb54  call    cs:__imp_LocalFree
0x18001eb5a  mov     eax, r14d
0x18001eb5d  jmp     loc_18001EE6C
0x18001eb62  call    cs:__imp_GetLastError
0x18001eb68  mov     rcx, rdi; hObject
0x18001eb6b  mov     r14d, eax
0x18001eb6e  call    cs:__imp_CloseHandle
0x18001eb74  mov     ecx, r14d; dwErrCode
0x18001eb77  call    cs:__imp_SetLastError
0x18001eb7d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001eb81  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x18001eb88  jz      loc_18001ED04
0x18001eb8e  mov     rcx, [rsp+370h+hMem]; lpPathName
0x18001eb93  call    cs:__imp_RemoveDirectoryW
0x18001eb99  test    eax, eax
0x18001eb9b  jz      loc_18001ECD6
0x18001eba1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001eba5  jz      short loc_18001EC18
0x18001eba7  test    rdi, rdi
0x18001ebaa  jz      short loc_18001EC18
0x18001ebac  mov     rcx, rdi; hObject
0x18001ebaf  call    cs:__imp_CloseHandle
0x18001ebb5  jmp     short loc_18001EC18
0x18001ebb7  call    cs:__imp_DeleteFileW
0x18001ebbd  test    eax, eax
0x18001ebbf  jnz     short loc_18001EC18
0x18001ebc1  test    r12b, 2
0x18001ebc5  jz      loc_18001EDAF
0x18001ebcb  call    cs:__imp_GetLastError
0x18001ebd1  cmp     eax, 5
0x18001ebd4  jnz     loc_18001EDAF
0x18001ebda  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18001ebdf  call    cs:__imp_GetFileAttributesW
0x18001ebe5  test    al, 1
0x18001ebe7  jz      loc_18001EDA8
0x18001ebed  and     eax, 0FFFFFFFEh
0x18001ebf0  mov     ecx, 80h
0x18001ebf5  cmovz   eax, ecx
0x18001ebf8  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18001ebfd  mov     edx, eax; dwFileAttributes
0x18001ebff  call    cs:__imp_SetFileAttributesW
0x18001ec05  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18001ec0a  call    cs:__imp_DeleteFileW
0x18001ec10  test    eax, eax
0x18001ec12  jz      loc_18001ED75
0x18001ec18  mov     rcx, [rsp+370h+hMem]; hMem
0x18001ec1d  test    rcx, rcx
0x18001ec20  jz      short loc_18001EC28
0x18001ec22  call    cs:__imp_LocalFree
0x18001ec28  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18001ec2c  mov     rcx, rsi; hFindFile
0x18001ec2f  call    cs:__imp_FindNextFileW
0x18001ec35  test    eax, eax
0x18001ec37  jnz     loc_18001E9EF
0x18001ec3d  call    cs:__imp_GetLastError
0x18001ec43  cmp     eax, 12h
0x18001ec46  jnz     loc_18001EDED
0x18001ec4c  test    r12b, 1
0x18001ec50  jnz     loc_18001ED47
0x18001ec56  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18001ec5a  jz      loc_18001EDD2
0x18001ec60  lea     edi, [rax-0Eh]
0x18001ec63  mov     dword ptr [rsp+370h+hMem], 3
0x18001ec6b  mov     r9d, edi; dwBufferSize
0x18001ec6e  lea     r8, [rsp+370h+hMem]; lpFileInformation
0x18001ec73  lea     edx, [rax+3]; FileInformationClass
0x18001ec76  mov     rcx, r15; hFile
0x18001ec79  call    cs:__imp_SetFileInformationByHandle
0x18001ec7f  test    eax, eax
0x18001ec81  jnz     loc_18001ED47
0x18001ec87  call    cs:__imp_GetLastError
0x18001ec8d  cmp     eax, 5
0x18001ec90  jz      loc_18001EDB6
0x18001ec96  lea     r9d, [rdi-3]; dwBufferSize
0x18001ec9a  mov     [rsp+370h+FileInformation], 1
0x18001ec9f  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x18001eca4  mov     edx, edi; FileInformationClass
0x18001eca6  mov     rcx, r15; hFile
0x18001eca9  call    cs:__imp_SetFileInformationByHandle
0x18001ecaf  test    eax, eax
0x18001ecb1  jnz     loc_18001ED47
0x18001ecb7  mov     edx, 171h; void *
0x18001ecbc  mov     rcx, [rbp+278h]; this
0x18001ecc3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ecca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001eccf  mov     edi, eax
0x18001ecd1  jmp     loc_18001EE43
0x18001ecd6  mov     rcx, [rbp+278h]; this
0x18001ecdd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ece4  mov     edx, 131h; void *
0x18001ece9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ecee  lea     rcx, [rdi-1]
0x18001ecf2  mov     r14d, eax
0x18001ecf5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ecf9  ja      loc_18001EB23
0x18001ecff  jmp     loc_18001EB1A
0x18001ed04  call    cs:__imp_GetLastError
0x18001ed0a  test    eax, eax
0x18001ed0c  jz      short loc_18001ED24
0x18001ed0e  mov     rcx, [rbp+278h]; this
0x18001ed15  mov     r9d, eax; char *
0x18001ed18  mov     edx, 136h; void *
0x18001ed1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ed22  jmp     short loc_18001ECEE
0x18001ed24  lea     rax, [rdi-1]
0x18001ed28  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ed2c  ja      short loc_18001ED37
0x18001ed2e  mov     rcx, rdi; hObject
0x18001ed31  call    cs:__imp_CloseHandle
0x18001ed37  mov     rcx, [rsp+370h+hMem]; hMem
0x18001ed3c  test    rcx, rcx
0x18001ed3f  jz      short loc_18001ED47
0x18001ed41  call    cs:__imp_LocalFree
0x18001ed47  mov     rcx, rsi; hFindFile
0x18001ed4a  call    cs:__imp_FindClose
0x18001ed50  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x18001ed55  test    rcx, rcx
0x18001ed58  jz      short loc_18001ED60
0x18001ed5a  call    cs:__imp_LocalFree
0x18001ed60  test    rbx, rbx
0x18001ed63  jz      short loc_18001ED6E
  ... truncated ...
```
