# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800a97a0`
- end: `0x1800a9cbd`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1309`
- prototype: `__int64 __fastcall(wil *, const unsigned __int16 *, void *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a9364`
- `0x1800a97a0`
- `0x1800a9cd0`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180041c44`
- `0x180056380`
- `0x180069edc`
- `0x1800a91e0`
- `0x1800a925c`
- `0x1800a9410`
- `0x1800a9434`
- `0x1800a97a0`
- `0x1800aa22c`
- `0x1800aa30c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9b2a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a9aae`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a9ade`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a9aae`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a9ade`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a9a64`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a9a64`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a9a39`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a9a39`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a9a19`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a9a19`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a99d2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a9bd4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a99d2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a9bd4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a99f1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a9a44`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a99f1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a9a44`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a98d7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a98d7`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a988f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a9941`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a988f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a9941`

## string_xrefs

- `0x1800a9851`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a98a2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a999c`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9af8`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9b12`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9b3b`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9b8d`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9bc0`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9c22`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a9c69`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const unsigned __int16 *a2, void *a3)
{
  int v4; // r15d
  const WCHAR *v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r9
  ULONG v10; // edi
  int v11; // eax
  HRESULT v12; // eax
  char *FirstFileW; // rdi
  const char *v14; // r9
  HRESULT v15; // eax
  int v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  DWORD FileAttributesW; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  DWORD v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int LastError; // ebx
  unsigned int v32; // [rsp+20h] [rbp-E0h]
  PWSTR v33; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v35; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v35,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v35);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    v6 = pszPathIn;
    if ( !pszPathIn )
    {
      v7 = -2147024882;
      v8 = 260;
      v9 = 2147942414LL;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)v9,
        v32);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            a1,
            &pszPathIn);
    v7 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v8 = 268;
      goto LABEL_7;
    }
    v6 = pszPathIn;
    v10 = 1;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v12 = PathAllocCombine(v6, L"*", v10, &ppszPathOut);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v12,
      v32);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v35 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_34;
    }
    v33 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v33,
      0);
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v33);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v15,
        v32);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v33, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v26 = GetLastError();
        if ( !v26 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)v26,
                v32);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v33) )
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                v17);
LABEL_45:
        v7 = v25;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v33, v4 & 0xFFFFFFFE, hFile);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          (const char *)(unsigned int)v16,
          v32);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_34:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v21 = GetLastError();
      if ( v21 == 18 )
      {
        if ( (v4 & 1) != 0 )
          goto LABEL_59;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v23 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
          return 0;
        }
        LODWORD(hFile) = 3;
        if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
          goto LABEL_59;
        if ( GetLastError() != 5 )
        {
          FileInformation[0] = 1;
          if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
          {
            v23 = 369;
LABEL_42:
            v24 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v23,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                    v22);
LABEL_43:
            v7 = v24;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v28 = 5;
        v29 = 374;
      }
      else
      {
        if ( !v21 )
          goto LABEL_59;
        v28 = v21;
        v29 = 348;
      }
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v29,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v28,
              v32);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v33) )
    goto LABEL_33;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v33);
    if ( (FileAttributesW & 1) == 0 )
    {
      v27 = 325;
      goto LABEL_50;
    }
    v20 = FileAttributesW & 0xFFFFFFFE;
    if ( !v20 )
      v20 = 128;
    SetFileAttributesW(v33, v20);
    if ( !DeleteFileW(v33) )
    {
      v27 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v27 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v27,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
         v18);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x1800a97a0  push    rbp
0x1800a97a2  push    rbx
0x1800a97a3  push    rsi
0x1800a97a4  push    rdi
0x1800a97a5  push    r12
0x1800a97a7  push    r14
0x1800a97a9  push    r15
0x1800a97ab  lea     rbp, [rsp-1C0h]
0x1800a97b3  sub     rsp, 2C0h
0x1800a97ba  mov     rax, cs:__security_cookie
0x1800a97c1  xor     rax, rsp
0x1800a97c4  mov     [rbp+1F0h+var_40], rax
0x1800a97cb  xor     r12d, r12d
0x1800a97ce  mov     r14, r8
0x1800a97d1  mov     [rsp+2F0h+pszPathIn], r12
0x1800a97d6  mov     r15d, edx
0x1800a97d9  mov     rbx, rcx
0x1800a97dc  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x1800a97e1  test    al, al
0x1800a97e3  jz      short loc_1800A982F
0x1800a97e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a97e9  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a97ee  mov     rdx, rbx
0x1800a97f1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a97f6  lea     rdx, [rsp+2F0h+var_2B0]
0x1800a97fb  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800a9800  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a9805  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a980a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a980f  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800a9814  test    rbx, rbx
0x1800a9817  jnz     short loc_1800A9828
0x1800a9819  mov     esi, 8007000Eh
0x1800a981e  mov     edx, 104h
0x1800a9823  mov     r9d, esi
0x1800a9826  jmp     short loc_1800A984A
0x1800a9828  mov     edi, 10h
0x1800a982d  jmp     short loc_1800A986C
0x1800a982f  lea     rdx, [rsp+2F0h+pszPathIn]
0x1800a9834  mov     rcx, rbx
0x1800a9837  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x1800a983c  mov     esi, eax
0x1800a983e  test    eax, eax
0x1800a9840  jns     short loc_1800A9862
0x1800a9842  mov     r9d, eax; char *
0x1800a9845  mov     edx, 10Ch; void *
0x1800a984a  mov     rcx, [rbp+1F8h]; this
0x1800a9851  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a985d  jmp     loc_1800A9C54
0x1800a9862  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800a9867  mov     edi, 1
0x1800a986c  xor     edx, edx
0x1800a986e  mov     [rsp+2F0h+ppszPathOut], r12
0x1800a9873  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800a9878  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a987d  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x1800a9882  mov     r8d, edi; dwFlags
0x1800a9885  lea     rdx, pszMore; "*"
0x1800a988c  mov     rcx, rbx; pszPathIn
0x1800a988f  call    cs:__imp_PathAllocCombine
0x1800a9895  mov     esi, eax
0x1800a9897  test    eax, eax
0x1800a9899  jns     short loc_1800A98BB
0x1800a989b  mov     rcx, [rbp+1F8h]; this
0x1800a98a2  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a98a9  mov     r9d, eax; char *
0x1800a98ac  mov     edx, 111h; void *
0x1800a98b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a98b6  jmp     loc_1800A9C4A
0x1800a98bb  xor     edx, edx; Val
0x1800a98bd  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800a98c2  mov     r8d, 250h; Size
0x1800a98c8  call    memset_0
0x1800a98cd  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x1800a98d2  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800a98d7  call    cs:__imp_FindFirstFileW
0x1800a98dd  mov     rdi, rax
0x1800a98e0  mov     [rsp+2F0h+var_2B0], rax
0x1800a98e5  dec     rax
0x1800a98e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a98ec  ja      loc_1800A9C62
0x1800a98f2  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800a98f7  jz      short loc_1800A991E
0x1800a98f9  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x1800a98fe  jnz     short loc_1800A991E
0x1800a9900  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x1800a9904  test    ax, ax
0x1800a9907  jz      loc_1800A9A5C
0x1800a990d  cmp     ax, 2Eh ; '.'
0x1800a9911  jnz     short loc_1800A991E
0x1800a9913  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x1800a9918  jz      loc_1800A9A5C
0x1800a991e  xor     edx, edx
0x1800a9920  mov     [rsp+2F0h+var_2C0], r12
0x1800a9925  lea     rcx, [rsp+2F0h+var_2C0]
0x1800a992a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a992f  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x1800a9934  mov     r8d, 18h; dwFlags
0x1800a993a  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x1800a993e  mov     rcx, rbx; pszPathIn
0x1800a9941  call    cs:__imp_PathAllocCombine
0x1800a9947  mov     esi, eax
0x1800a9949  test    eax, eax
0x1800a994b  js      loc_1800A9C1B
0x1800a9951  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800a9956  jz      loc_1800A99EC
0x1800a995c  mov     rdx, [rsp+2F0h+var_2C0]
0x1800a9961  lea     r8, [rsp+2F0h+FindFileData]
0x1800a9966  lea     rcx, [rsp+2F0h+hFile]
0x1800a996b  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x1800a9970  mov     r8, [rsp+2F0h+hFile]
0x1800a9975  lea     rax, [r8-1]
0x1800a9979  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a997d  ja      short loc_1800A99BF
0x1800a997f  mov     rcx, [rsp+2F0h+var_2C0]
0x1800a9984  mov     edx, r15d
0x1800a9987  and     edx, 0FFFFFFFEh
0x1800a998a  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x1800a998f  mov     esi, eax
0x1800a9991  test    eax, eax
0x1800a9993  jns     short loc_1800A99E0
0x1800a9995  mov     rcx, [rbp+1F8h]; this
0x1800a999c  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a99a3  mov     r9d, eax; char *
0x1800a99a6  mov     edx, 12Ch; void *
0x1800a99ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a99b0  lea     rcx, [rsp+2F0h+hFile]
0x1800a99b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a99ba  jmp     loc_1800A9C36
0x1800a99bf  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x1800a99c7  jz      loc_1800A9B2A
0x1800a99cd  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x1800a99d2  call    cs:__imp_RemoveDirectoryW
0x1800a99d8  test    eax, eax
0x1800a99da  jz      loc_1800A9B0B
0x1800a99e0  lea     rcx, [rsp+2F0h+hFile]
0x1800a99e5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a99ea  jmp     short loc_1800A9A52
0x1800a99ec  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800a99f1  call    cs:__imp_DeleteFileW
0x1800a99f7  test    eax, eax
0x1800a99f9  jnz     short loc_1800A9A52
0x1800a99fb  test    r15b, 2
0x1800a99ff  jz      loc_1800A9BA7
0x1800a9a05  call    cs:__imp_GetLastError
0x1800a9a0b  cmp     eax, 5
0x1800a9a0e  jnz     loc_1800A9BA7
0x1800a9a14  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800a9a19  call    cs:__imp_GetFileAttributesW
0x1800a9a1f  test    al, 1
0x1800a9a21  jz      loc_1800A9BA0
0x1800a9a27  and     eax, 0FFFFFFFEh
0x1800a9a2a  mov     ecx, 80h
0x1800a9a2f  cmovz   eax, ecx
0x1800a9a32  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800a9a37  mov     edx, eax; dwFileAttributes
0x1800a9a39  call    cs:__imp_SetFileAttributesW
0x1800a9a3f  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800a9a44  call    cs:__imp_DeleteFileW
0x1800a9a4a  test    eax, eax
0x1800a9a4c  jz      loc_1800A9B81
0x1800a9a52  lea     rcx, [rsp+2F0h+var_2C0]
0x1800a9a57  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9a5c  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800a9a61  mov     rcx, rdi; hFindFile
0x1800a9a64  call    cs:__imp_FindNextFileW
0x1800a9a6a  test    eax, eax
0x1800a9a6c  jnz     loc_1800A98F2
0x1800a9a72  call    cs:__imp_GetLastError
0x1800a9a78  cmp     eax, 12h
0x1800a9a7b  jnz     loc_1800A9BE8
0x1800a9a81  test    r15b, 1
0x1800a9a85  jnz     loc_1800A9BF6
0x1800a9a8b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800a9a8f  jz      loc_1800A9BD1
0x1800a9a95  lea     ebx, [rax-0Eh]
0x1800a9a98  mov     dword ptr [rsp+2F0h+hFile], 3
0x1800a9aa0  mov     r9d, ebx; dwBufferSize
0x1800a9aa3  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x1800a9aa8  lea     edx, [rax+3]; FileInformationClass
0x1800a9aab  mov     rcx, r14; hFile
0x1800a9aae  call    cs:__imp_SetFileInformationByHandle
0x1800a9ab4  test    eax, eax
0x1800a9ab6  jnz     loc_1800A9BF6
0x1800a9abc  call    cs:__imp_GetLastError
0x1800a9ac2  cmp     eax, 5
0x1800a9ac5  jz      loc_1800A9BAE
0x1800a9acb  lea     r9d, [rbx-3]; dwBufferSize
0x1800a9acf  mov     [rsp+2F0h+FileInformation], 1
0x1800a9ad4  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1800a9ad9  mov     edx, ebx; FileInformationClass
0x1800a9adb  mov     rcx, r14; hFile
0x1800a9ade  call    cs:__imp_SetFileInformationByHandle
0x1800a9ae4  test    eax, eax
0x1800a9ae6  jnz     loc_1800A9BF6
0x1800a9aec  mov     edx, 171h; void *
0x1800a9af1  mov     rcx, [rbp+1F8h]; this
0x1800a9af8  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9aff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9b04  mov     esi, eax
0x1800a9b06  jmp     loc_1800A9C40
0x1800a9b0b  mov     rcx, [rbp+1F8h]; this
0x1800a9b12  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9b19  mov     edx, 131h; void *
0x1800a9b1e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9b23  mov     esi, eax
0x1800a9b25  jmp     loc_1800A99B0
0x1800a9b2a  call    cs:__imp_GetLastError
0x1800a9b30  test    eax, eax
0x1800a9b32  jz      short loc_1800A9B51
0x1800a9b34  mov     rcx, [rbp+1F8h]; this
0x1800a9b3b  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9b42  mov     r9d, eax; char *
0x1800a9b45  mov     edx, 136h; void *
0x1800a9b4a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a9b4f  jmp     short loc_1800A9B23
0x1800a9b51  lea     rcx, [rsp+2F0h+hFile]
0x1800a9b56  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a9b5b  lea     rcx, [rsp+2F0h+var_2C0]
0x1800a9b60  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9b65  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a9b6a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800a9b6f  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800a9b74  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9b79  mov     esi, r12d
0x1800a9b7c  jmp     loc_1800A9C54
0x1800a9b81  mov     edx, 150h; void *
0x1800a9b86  mov     rcx, [rbp+1F8h]; this
0x1800a9b8d  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9b94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9b99  mov     esi, eax
0x1800a9b9b  jmp     loc_1800A9C36
0x1800a9ba0  mov     edx, 145h
0x1800a9ba5  jmp     short loc_1800A9B86
0x1800a9ba7  mov     edx, 141h
0x1800a9bac  jmp     short loc_1800A9B86
0x1800a9bae  mov     r9d, 5; char *
0x1800a9bb4  mov     edx, 176h; void *
0x1800a9bb9  mov     rcx, [rbp+1F8h]; this
0x1800a9bc0  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9bc7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a9bcc  jmp     loc_1800A9B04
0x1800a9bd1  mov     rcx, rbx; lpPathName
0x1800a9bd4  call    cs:__imp_RemoveDirectoryW
0x1800a9bda  test    eax, eax
0x1800a9bdc  jnz     short loc_1800A9BF6
0x1800a9bde  mov     edx, 17Dh
0x1800a9be3  jmp     loc_1800A9AF1
0x1800a9be8  test    eax, eax
0x1800a9bea  jz      short loc_1800A9BF6
0x1800a9bec  mov     r9d, eax
0x1800a9bef  mov     edx, 15Ch
0x1800a9bf4  jmp     short loc_1800A9BB9
0x1800a9bf6  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a9bfb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800a9c00  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800a9c05  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c0a  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800a9c0f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c14  xor     eax, eax
0x1800a9c16  jmp     loc_1800A9C9C
0x1800a9c1b  mov     rcx, [rbp+1F8h]; this
0x1800a9c22  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9c29  mov     r9d, eax; char *
0x1800a9c2c  mov     edx, 120h; void *
0x1800a9c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9c36  lea     rcx, [rsp+2F0h+var_2C0]
0x1800a9c3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c40  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a9c45  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800a9c4a  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800a9c4f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c54  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800a9c59  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c5e  mov     eax, esi
0x1800a9c60  jmp     short loc_1800A9C9C
0x1800a9c62  mov     rcx, [rbp+1F8h]; this
0x1800a9c69  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a9c70  mov     edx, 115h; void *
0x1800a9c75  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9c7a  lea     rcx, [rsp+2F0h+var_2B0]
0x1800a9c7f  mov     ebx, eax
0x1800a9c81  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800a9c86  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800a9c8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c90  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800a9c95  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a9c9a  mov     eax, ebx
0x1800a9c9c  mov     rcx, [rbp+1F0h+var_40]
0x1800a9ca3  xor     rcx, rsp; StackCookie
0x1800a9ca6  call    __security_check_cookie
0x1800a9cab  add     rsp, 2C0h
0x1800a9cb2  pop     r15
0x1800a9cb4  pop     r14
0x1800a9cb6  pop     r12
0x1800a9cb8  pop     rdi
0x1800a9cb9  pop     rsi
0x1800a9cba  pop     rbx
0x1800a9cbb  pop     rbp
  ... truncated ...
```
