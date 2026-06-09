# wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800463e4`
- end: `0x180046a38`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1620`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045918`
- `0x1800463e4`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000a444`
- `0x18000a464`
- `0x180029624`
- `0x18003e0b4`
- `0x18003f4a4`
- `0x1800463e4`
- `0x1800643b4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004675f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004681b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004675f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004681b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046898`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004670b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004670b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800466b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800468cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800466b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800468cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800464fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800467b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800469f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800464fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800466e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800467b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800469f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a06`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180046793`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180046793`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800466ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800468e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800469e8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800466ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800468e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800469e8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004656d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004656d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004674b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004679e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004674b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004679e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180046773`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180046773`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800467c3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800467c3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004680d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004683d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004680d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004683d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180046727`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180046977`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180046727`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180046977`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046605`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046605`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180046638`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180046638`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180046527`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800465c5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180046527`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800465c5`

## string_xrefs

- `0x18004645b`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800464db`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18004653a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18004669a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180046857`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180046871`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800468a9`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18004691c`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180046963`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800469a8`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800469c8`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(char *a1, int a2, void *a3)
{
  const char *v6; // r9
  WCHAR *v7; // rbx
  unsigned int v8; // ebx
  ULONG v10; // r8d
  HRESULT v11; // eax
  unsigned int LastError; // edi
  char *FirstFileW; // rsi
  const char *v14; // r9
  HRESULT v15; // eax
  HANDLE FileW; // rax
  __int64 v17; // rdi
  int v18; // eax
  unsigned int v19; // r14d
  DWORD v20; // r14d
  const char *v21; // r9
  const char *v22; // r9
  DWORD FileAttributesW; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  const char *v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  DWORD v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-B8h] BYREF
  char FileInformation[8]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v39[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v40[13]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v41; // [rsp+D0h] [rbp-30h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  hMem = 0;
  if ( !wcsncmp_0((const wchar_t *)a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &pszPathIn,
      a1,
      0xFFFFFFFFFFFFFFFFuLL,
      v6);
    v7 = (WCHAR *)pszPathIn;
    if ( !pszPathIn )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      return v8;
    }
    v10 = 16;
  }
  else
  {
    pszPathIn = (PCWSTR)a1;
    v40[0] = ___7____func_V_lambda_1___1____GetFullPathNameW_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6APEAXPEAX_Z_1_LocalFree__YAPEAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEB_WAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6APEAXPEAX_Z_1_LocalFree__YAPEAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___2_PEAPEB_W_Z___A6AJPEA_W_KPEA_K_Z___function_wistd__6B_;
    v40[1] = &pszPathIn;
    v41 = v40;
    v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
           (char *)&hMem,
           (__int64)v39);
    if ( v41 )
      (*(void (__fastcall **)(_QWORD *))(*v41 + 24LL))(v41);
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)v8,
        dwCreationDisposition);
      if ( hMem )
        LocalFree(hMem);
      return v8;
    }
    v7 = (WCHAR *)hMem;
    v10 = 1;
  }
  ppszPathOut = 0;
  v11 = PathAllocCombine(v7, L"*", v10, &ppszPathOut);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v11,
      dwCreationDisposition);
LABEL_93:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( v7 )
      LocalFree(v7);
    return LastError;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v14);
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
    v15 = PathAllocCombine(v7, FindFileData.cFileName, 0x18u, (PWSTR *)&hMem);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
      goto LABEL_80;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( !DeleteFileW((LPCWSTR)hMem) )
      {
        if ( (a2 & 2) == 0 || GetLastError() != 5 )
        {
          v31 = 321;
LABEL_79:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v31,
                        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                        v22);
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
          v31 = 325;
          goto LABEL_79;
        }
        v24 = FileAttributesW & 0xFFFFFFFE;
        if ( !v24 )
          v24 = 128;
        SetFileAttributesW((LPCWSTR)hMem, v24);
        if ( !DeleteFileW((LPCWSTR)hMem) )
        {
          v31 = 336;
          goto LABEL_79;
        }
      }
      goto LABEL_52;
    }
    FileW = CreateFileW((LPCWSTR)hMem, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
    v17 = (__int64)FileW;
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
        v18 = wil::RemoveDirectoryRecursiveNoThrow(hMem, a2 & 0xFFFFFFFE, v17);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12C,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
            (const char *)(unsigned int)v18,
            dwCreationDisposition);
LABEL_31:
          CloseHandle((HANDLE)v17);
LABEL_32:
          if ( hMem )
            LocalFree(hMem);
          FindClose(FirstFileW);
          if ( ppszPathOut )
            LocalFree(ppszPathOut);
          if ( v7 )
            LocalFree(v7);
          return v19;
        }
LABEL_43:
        if ( v17 )
          CloseHandle((HANDLE)v17);
        goto LABEL_52;
      }
      v20 = GetLastError();
      CloseHandle((HANDLE)v17);
      SetLastError(v20);
      v17 = -1;
    }
    if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
    {
      v30 = GetLastError();
      if ( !v30 )
      {
        if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)v17);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_73;
      }
      v29 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x136,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v30,
              dwCreationDisposition);
LABEL_65:
      v19 = v29;
      if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_32;
      goto LABEL_31;
    }
    if ( !RemoveDirectoryW((LPCWSTR)hMem) )
    {
      v29 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x131,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              v21);
      goto LABEL_65;
    }
    if ( v17 != -1 )
      goto LABEL_43;
LABEL_52:
    if ( hMem )
      LocalFree(hMem);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  v25 = GetLastError();
  if ( v25 != 18 )
  {
    if ( !v25 )
      goto LABEL_73;
    v32 = v25;
    v33 = 348;
    goto LABEL_85;
  }
  if ( (a2 & 1) != 0 )
    goto LABEL_73;
  if ( a3 == (void *)-1LL )
  {
    if ( RemoveDirectoryW(v7) )
      goto LABEL_73;
    v27 = 381;
LABEL_62:
    v28 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
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
    v32 = 5;
    v33 = 374;
LABEL_85:
    v28 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v33,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
            (const char *)v32,
            dwCreationDisposition);
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
  if ( v7 )
    LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x1800463e4  mov     [rsp-8+arg_18], rbx
0x1800463e9  push    rbp
0x1800463ea  push    rsi
0x1800463eb  push    rdi
0x1800463ec  push    r12
0x1800463ee  push    r13
0x1800463f0  push    r14
0x1800463f2  push    r15
0x1800463f4  lea     rbp, [rsp-240h]
0x1800463fc  sub     rsp, 340h
0x180046403  mov     rax, cs:__security_cookie
0x18004640a  xor     rax, rsp
0x18004640d  mov     [rbp+270h+var_40], rax
0x180046414  xor     r13d, r13d
0x180046417  mov     r15, r8
0x18004641a  mov     r12d, edx
0x18004641d  mov     [rsp+370h+hMem], r13
0x180046422  lea     rdx, String2; "\\\\?\\"
0x180046429  mov     rbx, rcx
0x18004642c  lea     r8d, [r13+4]; MaxCount
0x180046430  call    wcsncmp_0
0x180046435  test    eax, eax
0x180046437  jnz     short loc_180046486
0x180046439  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004643d  lea     rcx, [rsp+370h+pszPathIn]
0x180046442  mov     rdx, rbx
0x180046445  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18004644a  mov     rbx, [rsp+370h+pszPathIn]
0x18004644f  test    rbx, rbx
0x180046452  jnz     short loc_18004647B
0x180046454  mov     rcx, [rbp+278h]; this
0x18004645b  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046462  mov     ebx, 8007000Eh
0x180046467  mov     edx, 104h; void *
0x18004646c  mov     r9d, ebx; char *
0x18004646f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046474  mov     eax, ebx
0x180046476  jmp     loc_180046A0E
0x18004647b  mov     r8d, 10h
0x180046481  jmp     loc_180046513
0x180046486  lea     rax, ??_7?$__func@V_lambda_1_@?1???$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@PEAPEB_W@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const * *)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18004648d  mov     [rsp+370h+pszPathIn], rbx
0x180046492  mov     [rsp+370h+var_308], rax
0x180046497  lea     rdx, [rsp+370h+var_310]
0x18004649c  lea     rax, [rsp+370h+pszPathIn]
0x1800464a1  mov     [rsp+370h+var_300], rax
0x1800464a6  lea     rcx, [rsp+370h+hMem]
0x1800464ab  lea     rax, [rsp+370h+var_308]
0x1800464b0  mov     [rbp+270h+var_2A0], rax
0x1800464b4  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)> const &)
0x1800464b9  mov     rcx, [rbp+270h+var_2A0]
0x1800464bd  mov     ebx, eax
0x1800464bf  test    rcx, rcx
0x1800464c2  jz      short loc_1800464D0
0x1800464c4  mov     rdx, [rcx]
0x1800464c7  mov     rax, [rdx+18h]
0x1800464cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464d0  test    ebx, ebx
0x1800464d2  jns     short loc_180046508
0x1800464d4  mov     rcx, [rbp+278h]; this
0x1800464db  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800464e2  mov     r9d, ebx; char *
0x1800464e5  mov     edx, 10Ch; void *
0x1800464ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464ef  mov     rcx, [rsp+370h+hMem]; hMem
0x1800464f4  test    rcx, rcx
0x1800464f7  jz      loc_180046474
0x1800464fd  call    cs:__imp_LocalFree
0x180046503  jmp     loc_180046474
0x180046508  mov     rbx, [rsp+370h+hMem]
0x18004650d  mov     r8d, 1; dwFlags
0x180046513  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x180046518  mov     [rsp+370h+ppszPathOut], r13
0x18004651d  lea     rdx, pszMore; "*"
0x180046524  mov     rcx, rbx; pszPathIn
0x180046527  call    cs:__imp_PathAllocCombine
0x18004652d  mov     edi, eax
0x18004652f  test    eax, eax
0x180046531  jns     short loc_180046553
0x180046533  mov     rcx, [rbp+278h]; this
0x18004653a  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046541  mov     r9d, eax; char *
0x180046544  mov     edx, 111h; void *
0x180046549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004654e  jmp     loc_1800469EE
0x180046553  xor     edx, edx; Val
0x180046555  lea     rcx, [rbp+270h+FindFileData]; void *
0x180046559  mov     r8d, 250h; Size
0x18004655f  call    memset_0
0x180046564  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x180046569  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18004656d  call    cs:__imp_FindFirstFileW
0x180046573  mov     rsi, rax
0x180046576  dec     rax
0x180046579  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004657d  ja      loc_1800469C1
0x180046583  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180046587  jz      short loc_1800465AE
0x180046589  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x18004658e  jnz     short loc_1800465AE
0x180046590  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x180046594  test    ax, ax
0x180046597  jz      loc_1800467BC
0x18004659d  cmp     ax, 2Eh ; '.'
0x1800465a1  jnz     short loc_1800465AE
0x1800465a3  cmp     [rbp+270h+FindFileData.cFileName+4], r13w
0x1800465a8  jz      loc_1800467BC
0x1800465ae  lea     r9, [rsp+370h+hMem]; ppszPathOut
0x1800465b3  mov     [rsp+370h+hMem], r13
0x1800465b8  mov     r8d, 18h; dwFlags
0x1800465be  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x1800465c2  mov     rcx, rbx; pszPathIn
0x1800465c5  call    cs:__imp_PathAllocCombine
0x1800465cb  mov     edi, eax
0x1800465cd  test    eax, eax
0x1800465cf  js      loc_1800469A1
0x1800465d5  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x1800465d9  mov     rcx, [rsp+370h+hMem]; lpFileName
0x1800465de  jz      loc_18004674B
0x1800465e4  xor     r9d, r9d; lpSecurityAttributes
0x1800465e7  mov     [rsp+370h+hTemplateFile], r13; hTemplateFile
0x1800465ec  mov     [rsp+370h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800465f4  mov     edx, 80010000h; dwDesiredAccess
0x1800465f9  mov     [rsp+370h+dwCreationDisposition], 3; int
0x180046601  lea     r8d, [r9+1]; dwShareMode
0x180046605  call    cs:__imp_CreateFileW
0x18004660b  mov     rdi, rax
0x18004660e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046612  jz      loc_180046715
0x180046618  test    rax, rax
0x18004661b  jz      loc_180046715
0x180046621  mov     r9d, 8; dwBufferSize
0x180046627  mov     [rsp+370h+pszPathIn], r13
0x18004662c  lea     r8, [rsp+370h+pszPathIn]; lpFileInformation
0x180046631  mov     rcx, rax; hFile
0x180046634  lea     edx, [r9+1]; FileInformationClass
0x180046638  call    cs:__imp_GetFileInformationByHandleEx
0x18004663e  test    eax, eax
0x180046640  jz      loc_1800466F6
0x180046646  mov     rax, [rsp+370h+pszPathIn]
0x18004664b  test    al, 10h
0x18004664d  jz      loc_1800466F6
0x180046653  mov     ecx, dword ptr [rsp+370h+pszPathIn+4]
0x180046657  bt      eax, 0Ah
0x18004665b  jnb     short loc_18004666F
0x18004665d  bt      ecx, 1Ch
0x180046661  jb      short loc_18004666F
0x180046663  cmp     ecx, 80000018h
0x180046669  jnz     loc_1800466F6
0x18004666f  mov     edx, r12d
0x180046672  mov     [rbp+270h+FindFileData.dwReserved0], ecx
0x180046675  mov     rcx, [rsp+370h+hMem]
0x18004667a  and     edx, 0FFFFFFFEh
0x18004667d  mov     r8, rdi
0x180046680  mov     [rbp+270h+FindFileData.dwFileAttributes], eax
0x180046683  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)
0x180046688  mov     r14d, eax
0x18004668b  test    eax, eax
0x18004668d  jns     loc_18004673B
0x180046693  mov     rcx, [rbp+278h]; this
0x18004669a  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800466a1  mov     r9d, eax; char *
0x1800466a4  mov     edx, 12Ch; void *
0x1800466a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800466ae  mov     rcx, rdi; hObject
0x1800466b1  call    cs:__imp_CloseHandle
0x1800466b7  mov     rcx, [rsp+370h+hMem]; hMem
0x1800466bc  test    rcx, rcx
0x1800466bf  jz      short loc_1800466C7
0x1800466c1  call    cs:__imp_LocalFree
0x1800466c7  mov     rcx, rsi; hFindFile
0x1800466ca  call    cs:__imp_FindClose
0x1800466d0  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x1800466d5  test    rcx, rcx
0x1800466d8  jz      short loc_1800466E0
0x1800466da  call    cs:__imp_LocalFree
0x1800466e0  test    rbx, rbx
0x1800466e3  jz      short loc_1800466EE
0x1800466e5  mov     rcx, rbx; hMem
0x1800466e8  call    cs:__imp_LocalFree
0x1800466ee  mov     eax, r14d
0x1800466f1  jmp     loc_180046A0E
0x1800466f6  call    cs:__imp_GetLastError
0x1800466fc  mov     rcx, rdi; hObject
0x1800466ff  mov     r14d, eax
0x180046702  call    cs:__imp_CloseHandle
0x180046708  mov     ecx, r14d; dwErrCode
0x18004670b  call    cs:__imp_SetLastError
0x180046711  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046715  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x18004671c  jz      loc_180046898
0x180046722  mov     rcx, [rsp+370h+hMem]; lpPathName
0x180046727  call    cs:__imp_RemoveDirectoryW
0x18004672d  test    eax, eax
0x18004672f  jz      loc_18004686A
0x180046735  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180046739  jz      short loc_1800467AC
0x18004673b  test    rdi, rdi
0x18004673e  jz      short loc_1800467AC
0x180046740  mov     rcx, rdi; hObject
0x180046743  call    cs:__imp_CloseHandle
0x180046749  jmp     short loc_1800467AC
0x18004674b  call    cs:__imp_DeleteFileW
0x180046751  test    eax, eax
0x180046753  jnz     short loc_1800467AC
0x180046755  test    r12b, 2
0x180046759  jz      loc_18004694A
0x18004675f  call    cs:__imp_GetLastError
0x180046765  cmp     eax, 5
0x180046768  jnz     loc_18004694A
0x18004676e  mov     rcx, [rsp+370h+hMem]; lpFileName
0x180046773  call    cs:__imp_GetFileAttributesW
0x180046779  test    al, 1
0x18004677b  jz      loc_180046943
0x180046781  and     eax, 0FFFFFFFEh
0x180046784  mov     ecx, 80h
0x180046789  cmovz   eax, ecx
0x18004678c  mov     rcx, [rsp+370h+hMem]; lpFileName
0x180046791  mov     edx, eax; dwFileAttributes
0x180046793  call    cs:__imp_SetFileAttributesW
0x180046799  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18004679e  call    cs:__imp_DeleteFileW
0x1800467a4  test    eax, eax
0x1800467a6  jz      loc_180046910
0x1800467ac  mov     rcx, [rsp+370h+hMem]; hMem
0x1800467b1  test    rcx, rcx
0x1800467b4  jz      short loc_1800467BC
0x1800467b6  call    cs:__imp_LocalFree
0x1800467bc  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x1800467c0  mov     rcx, rsi; hFindFile
0x1800467c3  call    cs:__imp_FindNextFileW
0x1800467c9  test    eax, eax
0x1800467cb  jnz     loc_180046583
0x1800467d1  call    cs:__imp_GetLastError
0x1800467d7  cmp     eax, 12h
0x1800467da  jnz     loc_18004698F
0x1800467e0  test    r12b, 1
0x1800467e4  jnz     loc_1800468E2
0x1800467ea  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800467ee  jz      loc_180046974
0x1800467f4  lea     edi, [rax-0Eh]
0x1800467f7  mov     dword ptr [rsp+370h+hMem], 3
0x1800467ff  mov     r9d, edi; dwBufferSize
0x180046802  lea     r8, [rsp+370h+hMem]; lpFileInformation
0x180046807  lea     edx, [rax+3]; FileInformationClass
0x18004680a  mov     rcx, r15; hFile
0x18004680d  call    cs:__imp_SetFileInformationByHandle
0x180046813  test    eax, eax
0x180046815  jnz     loc_1800468E2
0x18004681b  call    cs:__imp_GetLastError
0x180046821  cmp     eax, 5
0x180046824  jz      loc_180046951
0x18004682a  lea     r9d, [rdi-3]; dwBufferSize
0x18004682e  mov     [rsp+370h+FileInformation], 1
0x180046833  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x180046838  mov     edx, edi; FileInformationClass
0x18004683a  mov     rcx, r15; hFile
0x18004683d  call    cs:__imp_SetFileInformationByHandle
0x180046843  test    eax, eax
0x180046845  jnz     loc_1800468E2
0x18004684b  mov     edx, 171h; void *
0x180046850  mov     rcx, [rbp+278h]; this
0x180046857  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004685e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046863  mov     edi, eax
0x180046865  jmp     loc_1800469E5
0x18004686a  mov     rcx, [rbp+278h]; this
0x180046871  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046878  mov     edx, 131h; void *
0x18004687d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046882  lea     rcx, [rdi-1]
0x180046886  mov     r14d, eax
0x180046889  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004688d  ja      loc_1800466B7
0x180046893  jmp     loc_1800466AE
0x180046898  call    cs:__imp_GetLastError
0x18004689e  test    eax, eax
0x1800468a0  jz      short loc_1800468BF
0x1800468a2  mov     rcx, [rbp+278h]; this
0x1800468a9  lea     r8, aOnecoreInterna_9; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800468b0  mov     r9d, eax; char *
0x1800468b3  mov     edx, 136h; void *
0x1800468b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800468bd  jmp     short loc_180046882
0x1800468bf  lea     rax, [rdi-1]
0x1800468c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800468c7  ja      short loc_1800468D2
0x1800468c9  mov     rcx, rdi; hObject
0x1800468cc  call    cs:__imp_CloseHandle
0x1800468d2  mov     rcx, [rsp+370h+hMem]; hMem
0x1800468d7  test    rcx, rcx
0x1800468da  jz      short loc_1800468E2
0x1800468dc  call    cs:__imp_LocalFree
0x1800468e2  mov     rcx, rsi; hFindFile
0x1800468e5  call    cs:__imp_FindClose
0x1800468eb  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x1800468f0  test    rcx, rcx
0x1800468f3  jz      short loc_1800468FB
0x1800468f5  call    cs:__imp_LocalFree
0x1800468fb  test    rbx, rbx
  ... truncated ...
```
