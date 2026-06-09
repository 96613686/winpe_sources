# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x18002c258`
- end: `0x18002c775`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1309`
- prototype: `__int64 __fastcall(wil *, const unsigned __int16 *, void *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b714`
- `0x18002b7a4`
- `0x18002b9c0`
- `0x18002c258`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18001fb04`
- `0x18002ad0c`
- `0x18002b088`
- `0x18002b1fc`
- `0x18002b220`
- `0x18002b27c`
- `0x18002c258`
- `0x18002c898`
- `0x18002cac4`
- `0x18002cb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5e2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c48a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c68c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c48a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c68c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c51c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c51c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c4a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c4fc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c4a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c4fc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c4f1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c4f1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c4d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c4d1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c38f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c38f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c566`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c596`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c566`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c596`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c347`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c3f9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c347`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c3f9`

## string_xrefs

- `0x18002c309`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c35a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c454`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c5b0`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c5ca`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c5f3`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c645`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c678`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c6da`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18002c721`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
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
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
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
0x18002c258  push    rbp
0x18002c25a  push    rbx
0x18002c25b  push    rsi
0x18002c25c  push    rdi
0x18002c25d  push    r12
0x18002c25f  push    r14
0x18002c261  push    r15
0x18002c263  lea     rbp, [rsp-1C0h]
0x18002c26b  sub     rsp, 2C0h
0x18002c272  mov     rax, cs:__security_cookie
0x18002c279  xor     rax, rsp
0x18002c27c  mov     [rbp+1F0h+var_40], rax
0x18002c283  xor     r12d, r12d
0x18002c286  mov     r14, r8
0x18002c289  mov     [rsp+2F0h+pszPathIn], r12
0x18002c28e  mov     r15d, edx
0x18002c291  mov     rbx, rcx
0x18002c294  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x18002c299  test    al, al
0x18002c29b  jz      short loc_18002C2E7
0x18002c29d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c2a1  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c2a6  mov     rdx, rbx
0x18002c2a9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002c2ae  lea     rdx, [rsp+2F0h+var_2B0]
0x18002c2b3  lea     rcx, [rsp+2F0h+pszPathIn]
0x18002c2b8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002c2bd  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c2c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c2c7  mov     rbx, [rsp+2F0h+pszPathIn]
0x18002c2cc  test    rbx, rbx
0x18002c2cf  jnz     short loc_18002C2E0
0x18002c2d1  mov     esi, 8007000Eh
0x18002c2d6  mov     edx, 104h
0x18002c2db  mov     r9d, esi
0x18002c2de  jmp     short loc_18002C302
0x18002c2e0  mov     edi, 10h
0x18002c2e5  jmp     short loc_18002C324
0x18002c2e7  lea     rdx, [rsp+2F0h+pszPathIn]
0x18002c2ec  mov     rcx, rbx
0x18002c2ef  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18002c2f4  mov     esi, eax
0x18002c2f6  test    eax, eax
0x18002c2f8  jns     short loc_18002C31A
0x18002c2fa  mov     r9d, eax; char *
0x18002c2fd  mov     edx, 10Ch; void *
0x18002c302  mov     rcx, [rbp+1F8h]; this
0x18002c309  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c315  jmp     loc_18002C70C
0x18002c31a  mov     rbx, [rsp+2F0h+pszPathIn]
0x18002c31f  mov     edi, 1
0x18002c324  xor     edx, edx
0x18002c326  mov     [rsp+2F0h+ppszPathOut], r12
0x18002c32b  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18002c330  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c335  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x18002c33a  mov     r8d, edi; dwFlags
0x18002c33d  lea     rdx, pszMore; "*"
0x18002c344  mov     rcx, rbx; pszPathIn
0x18002c347  call    cs:__imp_PathAllocCombine
0x18002c34d  mov     esi, eax
0x18002c34f  test    eax, eax
0x18002c351  jns     short loc_18002C373
0x18002c353  mov     rcx, [rbp+1F8h]; this
0x18002c35a  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c361  mov     r9d, eax; char *
0x18002c364  mov     edx, 111h; void *
0x18002c369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c36e  jmp     loc_18002C702
0x18002c373  xor     edx, edx; Val
0x18002c375  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18002c37a  mov     r8d, 250h; Size
0x18002c380  call    memset_0
0x18002c385  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x18002c38a  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18002c38f  call    cs:__imp_FindFirstFileW
0x18002c395  mov     rdi, rax
0x18002c398  mov     [rsp+2F0h+var_2B0], rax
0x18002c39d  dec     rax
0x18002c3a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c3a4  ja      loc_18002C71A
0x18002c3aa  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18002c3af  jz      short loc_18002C3D6
0x18002c3b1  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x18002c3b6  jnz     short loc_18002C3D6
0x18002c3b8  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x18002c3bc  test    ax, ax
0x18002c3bf  jz      loc_18002C514
0x18002c3c5  cmp     ax, 2Eh ; '.'
0x18002c3c9  jnz     short loc_18002C3D6
0x18002c3cb  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x18002c3d0  jz      loc_18002C514
0x18002c3d6  xor     edx, edx
0x18002c3d8  mov     [rsp+2F0h+var_2C0], r12
0x18002c3dd  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c3e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c3e7  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x18002c3ec  mov     r8d, 18h; dwFlags
0x18002c3f2  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x18002c3f6  mov     rcx, rbx; pszPathIn
0x18002c3f9  call    cs:__imp_PathAllocCombine
0x18002c3ff  mov     esi, eax
0x18002c401  test    eax, eax
0x18002c403  js      loc_18002C6D3
0x18002c409  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18002c40e  jz      loc_18002C4A4
0x18002c414  mov     rdx, [rsp+2F0h+var_2C0]
0x18002c419  lea     r8, [rsp+2F0h+FindFileData]
0x18002c41e  lea     rcx, [rsp+2F0h+hFile]
0x18002c423  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18002c428  mov     r8, [rsp+2F0h+hFile]
0x18002c42d  lea     rax, [r8-1]
0x18002c431  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c435  ja      short loc_18002C477
0x18002c437  mov     rcx, [rsp+2F0h+var_2C0]
0x18002c43c  mov     edx, r15d
0x18002c43f  and     edx, 0FFFFFFFEh
0x18002c442  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18002c447  mov     esi, eax
0x18002c449  test    eax, eax
0x18002c44b  jns     short loc_18002C498
0x18002c44d  mov     rcx, [rbp+1F8h]; this
0x18002c454  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c45b  mov     r9d, eax; char *
0x18002c45e  mov     edx, 12Ch; void *
0x18002c463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c468  lea     rcx, [rsp+2F0h+hFile]
0x18002c46d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c472  jmp     loc_18002C6EE
0x18002c477  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x18002c47f  jz      loc_18002C5E2
0x18002c485  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x18002c48a  call    cs:__imp_RemoveDirectoryW
0x18002c490  test    eax, eax
0x18002c492  jz      loc_18002C5C3
0x18002c498  lea     rcx, [rsp+2F0h+hFile]
0x18002c49d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c4a2  jmp     short loc_18002C50A
0x18002c4a4  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18002c4a9  call    cs:__imp_DeleteFileW
0x18002c4af  test    eax, eax
0x18002c4b1  jnz     short loc_18002C50A
0x18002c4b3  test    r15b, 2
0x18002c4b7  jz      loc_18002C65F
0x18002c4bd  call    cs:__imp_GetLastError
0x18002c4c3  cmp     eax, 5
0x18002c4c6  jnz     loc_18002C65F
0x18002c4cc  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18002c4d1  call    cs:__imp_GetFileAttributesW
0x18002c4d7  test    al, 1
0x18002c4d9  jz      loc_18002C658
0x18002c4df  and     eax, 0FFFFFFFEh
0x18002c4e2  mov     ecx, 80h
0x18002c4e7  cmovz   eax, ecx
0x18002c4ea  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18002c4ef  mov     edx, eax; dwFileAttributes
0x18002c4f1  call    cs:__imp_SetFileAttributesW
0x18002c4f7  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18002c4fc  call    cs:__imp_DeleteFileW
0x18002c502  test    eax, eax
0x18002c504  jz      loc_18002C639
0x18002c50a  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c50f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c514  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18002c519  mov     rcx, rdi; hFindFile
0x18002c51c  call    cs:__imp_FindNextFileW
0x18002c522  test    eax, eax
0x18002c524  jnz     loc_18002C3AA
0x18002c52a  call    cs:__imp_GetLastError
0x18002c530  cmp     eax, 12h
0x18002c533  jnz     loc_18002C6A0
0x18002c539  test    r15b, 1
0x18002c53d  jnz     loc_18002C6AE
0x18002c543  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c547  jz      loc_18002C689
0x18002c54d  lea     ebx, [rax-0Eh]
0x18002c550  mov     dword ptr [rsp+2F0h+hFile], 3
0x18002c558  mov     r9d, ebx; dwBufferSize
0x18002c55b  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x18002c560  lea     edx, [rax+3]; FileInformationClass
0x18002c563  mov     rcx, r14; hFile
0x18002c566  call    cs:__imp_SetFileInformationByHandle
0x18002c56c  test    eax, eax
0x18002c56e  jnz     loc_18002C6AE
0x18002c574  call    cs:__imp_GetLastError
0x18002c57a  cmp     eax, 5
0x18002c57d  jz      loc_18002C666
0x18002c583  lea     r9d, [rbx-3]; dwBufferSize
0x18002c587  mov     [rsp+2F0h+FileInformation], 1
0x18002c58c  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x18002c591  mov     edx, ebx; FileInformationClass
0x18002c593  mov     rcx, r14; hFile
0x18002c596  call    cs:__imp_SetFileInformationByHandle
0x18002c59c  test    eax, eax
0x18002c59e  jnz     loc_18002C6AE
0x18002c5a4  mov     edx, 171h; void *
0x18002c5a9  mov     rcx, [rbp+1F8h]; this
0x18002c5b0  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c5b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c5bc  mov     esi, eax
0x18002c5be  jmp     loc_18002C6F8
0x18002c5c3  mov     rcx, [rbp+1F8h]; this
0x18002c5ca  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c5d1  mov     edx, 131h; void *
0x18002c5d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c5db  mov     esi, eax
0x18002c5dd  jmp     loc_18002C468
0x18002c5e2  call    cs:__imp_GetLastError
0x18002c5e8  test    eax, eax
0x18002c5ea  jz      short loc_18002C609
0x18002c5ec  mov     rcx, [rbp+1F8h]; this
0x18002c5f3  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c5fa  mov     r9d, eax; char *
0x18002c5fd  mov     edx, 136h; void *
0x18002c602  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c607  jmp     short loc_18002C5DB
0x18002c609  lea     rcx, [rsp+2F0h+hFile]
0x18002c60e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c613  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c618  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c61d  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c622  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002c627  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18002c62c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c631  mov     esi, r12d
0x18002c634  jmp     loc_18002C70C
0x18002c639  mov     edx, 150h; void *
0x18002c63e  mov     rcx, [rbp+1F8h]; this
0x18002c645  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c64c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c651  mov     esi, eax
0x18002c653  jmp     loc_18002C6EE
0x18002c658  mov     edx, 145h
0x18002c65d  jmp     short loc_18002C63E
0x18002c65f  mov     edx, 141h
0x18002c664  jmp     short loc_18002C63E
0x18002c666  mov     r9d, 5; char *
0x18002c66c  mov     edx, 176h; void *
0x18002c671  mov     rcx, [rbp+1F8h]; this
0x18002c678  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c67f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c684  jmp     loc_18002C5BC
0x18002c689  mov     rcx, rbx; lpPathName
0x18002c68c  call    cs:__imp_RemoveDirectoryW
0x18002c692  test    eax, eax
0x18002c694  jnz     short loc_18002C6AE
0x18002c696  mov     edx, 17Dh
0x18002c69b  jmp     loc_18002C5A9
0x18002c6a0  test    eax, eax
0x18002c6a2  jz      short loc_18002C6AE
0x18002c6a4  mov     r9d, eax
0x18002c6a7  mov     edx, 15Ch
0x18002c6ac  jmp     short loc_18002C671
0x18002c6ae  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c6b3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002c6b8  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18002c6bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6c2  lea     rcx, [rsp+2F0h+pszPathIn]
0x18002c6c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6cc  xor     eax, eax
0x18002c6ce  jmp     loc_18002C754
0x18002c6d3  mov     rcx, [rbp+1F8h]; this
0x18002c6da  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c6e1  mov     r9d, eax; char *
0x18002c6e4  mov     edx, 120h; void *
0x18002c6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6ee  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c6f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6f8  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c6fd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002c702  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18002c707  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c70c  lea     rcx, [rsp+2F0h+pszPathIn]
0x18002c711  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c716  mov     eax, esi
0x18002c718  jmp     short loc_18002C754
0x18002c71a  mov     rcx, [rbp+1F8h]; this
0x18002c721  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c728  mov     edx, 115h; void *
0x18002c72d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c732  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c737  mov     ebx, eax
0x18002c739  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002c73e  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18002c743  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c748  lea     rcx, [rsp+2F0h+pszPathIn]
0x18002c74d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c752  mov     eax, ebx
0x18002c754  mov     rcx, [rbp+1F0h+var_40]
0x18002c75b  xor     rcx, rsp; StackCookie
0x18002c75e  call    __security_check_cookie
0x18002c763  add     rsp, 2C0h
0x18002c76a  pop     r15
0x18002c76c  pop     r14
0x18002c76e  pop     r12
0x18002c770  pop     rdi
0x18002c771  pop     rsi
0x18002c772  pop     rbx
0x18002c773  pop     rbp
  ... truncated ...
```
