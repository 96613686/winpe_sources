# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x140005b1c`
- end: `0x14000602b`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1295`
- prototype: `__int64 __fastcall(wil *, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005b1c`
- `0x140008130`

## callees

- `0x1400022e4`
- `0x140002e60`
- `0x1400033b0`
- `0x1400033d4`
- `0x1400033f8`
- `0x14000362c`
- `0x140005b1c`
- `0x140006224`
- `0x140006244`
- `0x140006268`
- `0x140006930`
- `0x140007cb0`
- `0x140007e64`
- `0x140009696`
- `0x1400096d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140005d95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140005d95`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005db5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005db5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140005c53`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140005c53`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140005e2a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140005e5a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140005e2a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140005e5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140005d6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140005dc0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140005d6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140005dc0`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140005d4e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140005f42`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140005d4e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140005f42`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140005de0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140005de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ea6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005c0b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005cbd`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005c0b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005cbd`

## string_xrefs

- `0x140005bcd`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005c1e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005d18`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005e74`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005e8e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005f02`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005f90`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005fd7`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned int LastError; // ebx
  unsigned int v34; // [rsp+20h] [rbp-E0h]
  PWSTR v35; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v37; // [rsp+40h] [rbp-C0h] BYREF
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
      &v37,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)v9,
        v34);
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v12,
      v34);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v37 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
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
    v35 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v35,
      0);
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v35);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v15,
        v34);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v35, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v27 = GetLastError();
        if ( !v27 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v26 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x136, v28, (const char *)v27, v34);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v35) )
      {
        v26 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v17);
LABEL_45:
        v7 = v26;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v35, v4 & 0xFFFFFFFE, hFile);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v16,
          v34);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
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
            v24 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
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
            v24 = 369;
LABEL_42:
            v25 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v23);
LABEL_43:
            v7 = v25;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v30 = 374;
        v31 = 5;
      }
      else
      {
        if ( !v21 )
          goto LABEL_59;
        v31 = v21;
        v30 = 348;
      }
      v25 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v30, v22, (const char *)v31, v34);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v35) )
    goto LABEL_33;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v35);
    if ( (FileAttributesW & 1) == 0 )
    {
      v29 = 325;
      goto LABEL_50;
    }
    v20 = FileAttributesW & 0xFFFFFFFE;
    if ( !v20 )
      v20 = 128;
    SetFileAttributesW(v35, v20);
    if ( !DeleteFileW(v35) )
    {
      v29 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v29 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v29,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v18);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x140005b1c  push    rbp
0x140005b1e  push    rbx
0x140005b1f  push    rsi
0x140005b20  push    rdi
0x140005b21  push    r12
0x140005b23  push    r14
0x140005b25  push    r15
0x140005b27  lea     rbp, [rsp-1C0h]
0x140005b2f  sub     rsp, 2C0h
0x140005b36  mov     rax, cs:__security_cookie
0x140005b3d  xor     rax, rsp
0x140005b40  mov     [rbp+1F0h+var_40], rax
0x140005b47  xor     r12d, r12d
0x140005b4a  mov     r14, r8
0x140005b4d  mov     [rsp+2F0h+pszPathIn], r12
0x140005b52  mov     r15d, edx
0x140005b55  mov     rbx, rcx
0x140005b58  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x140005b5d  test    al, al
0x140005b5f  jz      short loc_140005BAB
0x140005b61  or      r8, 0FFFFFFFFFFFFFFFFh
0x140005b65  lea     rcx, [rsp+2F0h+var_2B0]
0x140005b6a  mov     rdx, rbx
0x140005b6d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140005b72  lea     rdx, [rsp+2F0h+var_2B0]
0x140005b77  lea     rcx, [rsp+2F0h+pszPathIn]
0x140005b7c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140005b81  lea     rcx, [rsp+2F0h+var_2B0]
0x140005b86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005b8b  mov     rbx, [rsp+2F0h+pszPathIn]
0x140005b90  test    rbx, rbx
0x140005b93  jnz     short loc_140005BA4
0x140005b95  mov     esi, 8007000Eh
0x140005b9a  mov     edx, 104h
0x140005b9f  mov     r9d, esi
0x140005ba2  jmp     short loc_140005BC6
0x140005ba4  mov     edi, 10h
0x140005ba9  jmp     short loc_140005BE8
0x140005bab  lea     rdx, [rsp+2F0h+pszPathIn]
0x140005bb0  mov     rcx, rbx
0x140005bb3  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x140005bb8  mov     esi, eax
0x140005bba  test    eax, eax
0x140005bbc  jns     short loc_140005BDE
0x140005bbe  mov     r9d, eax; char *
0x140005bc1  mov     edx, 10Ch; void *
0x140005bc6  mov     rcx, [rbp+1F8h]; this
0x140005bcd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005bd9  jmp     loc_140005FC2
0x140005bde  mov     rbx, [rsp+2F0h+pszPathIn]
0x140005be3  mov     edi, 1
0x140005be8  xor     edx, edx
0x140005bea  mov     [rsp+2F0h+ppszPathOut], r12
0x140005bef  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005bf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140005bf9  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x140005bfe  mov     r8d, edi; dwFlags
0x140005c01  lea     rdx, pszMore; "*"
0x140005c08  mov     rcx, rbx; pszPathIn
0x140005c0b  call    cs:__imp_PathAllocCombine
0x140005c11  mov     esi, eax
0x140005c13  test    eax, eax
0x140005c15  jns     short loc_140005C37
0x140005c17  mov     rcx, [rbp+1F8h]; this
0x140005c1e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005c25  mov     r9d, eax; char *
0x140005c28  mov     edx, 111h; void *
0x140005c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c32  jmp     loc_140005FB8
0x140005c37  xor     edx, edx; Val
0x140005c39  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x140005c3e  mov     r8d, 250h; Size
0x140005c44  call    memset_0
0x140005c49  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x140005c4e  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x140005c53  call    cs:__imp_FindFirstFileW
0x140005c59  mov     rdi, rax
0x140005c5c  mov     [rsp+2F0h+var_2B0], rax
0x140005c61  dec     rax
0x140005c64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005c68  ja      loc_140005FD0
0x140005c6e  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x140005c73  jz      short loc_140005C9A
0x140005c75  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x140005c7a  jnz     short loc_140005C9A
0x140005c7c  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x140005c80  test    ax, ax
0x140005c83  jz      loc_140005DD8
0x140005c89  cmp     ax, 2Eh ; '.'
0x140005c8d  jnz     short loc_140005C9A
0x140005c8f  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x140005c94  jz      loc_140005DD8
0x140005c9a  xor     edx, edx
0x140005c9c  mov     [rsp+2F0h+var_2C0], r12
0x140005ca1  lea     rcx, [rsp+2F0h+var_2C0]
0x140005ca6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140005cab  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x140005cb0  mov     r8d, 18h; dwFlags
0x140005cb6  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x140005cba  mov     rcx, rbx; pszPathIn
0x140005cbd  call    cs:__imp_PathAllocCombine
0x140005cc3  mov     esi, eax
0x140005cc5  test    eax, eax
0x140005cc7  js      loc_140005F89
0x140005ccd  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x140005cd2  jz      loc_140005D68
0x140005cd8  mov     rdx, [rsp+2F0h+var_2C0]
0x140005cdd  lea     r8, [rsp+2F0h+FindFileData]
0x140005ce2  lea     rcx, [rsp+2F0h+hFile]
0x140005ce7  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x140005cec  mov     r8, [rsp+2F0h+hFile]
0x140005cf1  lea     rax, [r8-1]
0x140005cf5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005cf9  ja      short loc_140005D3B
0x140005cfb  mov     rcx, [rsp+2F0h+var_2C0]
0x140005d00  mov     edx, r15d
0x140005d03  and     edx, 0FFFFFFFEh
0x140005d06  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x140005d0b  mov     esi, eax
0x140005d0d  test    eax, eax
0x140005d0f  jns     short loc_140005D5C
0x140005d11  mov     rcx, [rbp+1F8h]; this
0x140005d18  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005d1f  mov     r9d, eax; char *
0x140005d22  mov     edx, 12Ch; void *
0x140005d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005d2c  lea     rcx, [rsp+2F0h+hFile]
0x140005d31  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140005d36  jmp     loc_140005FA4
0x140005d3b  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x140005d43  jz      loc_140005EA6
0x140005d49  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x140005d4e  call    cs:__imp_RemoveDirectoryW
0x140005d54  test    eax, eax
0x140005d56  jz      loc_140005E87
0x140005d5c  lea     rcx, [rsp+2F0h+hFile]
0x140005d61  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140005d66  jmp     short loc_140005DCE
0x140005d68  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x140005d6d  call    cs:__imp_DeleteFileW
0x140005d73  test    eax, eax
0x140005d75  jnz     short loc_140005DCE
0x140005d77  test    r15b, 2
0x140005d7b  jz      loc_140005F1C
0x140005d81  call    cs:__imp_GetLastError
0x140005d87  cmp     eax, 5
0x140005d8a  jnz     loc_140005F1C
0x140005d90  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x140005d95  call    cs:__imp_GetFileAttributesW
0x140005d9b  test    al, 1
0x140005d9d  jz      loc_140005F15
0x140005da3  and     eax, 0FFFFFFFEh
0x140005da6  mov     ecx, 80h
0x140005dab  cmovz   eax, ecx
0x140005dae  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x140005db3  mov     edx, eax; dwFileAttributes
0x140005db5  call    cs:__imp_SetFileAttributesW
0x140005dbb  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x140005dc0  call    cs:__imp_DeleteFileW
0x140005dc6  test    eax, eax
0x140005dc8  jz      loc_140005EF6
0x140005dce  lea     rcx, [rsp+2F0h+var_2C0]
0x140005dd3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005dd8  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x140005ddd  mov     rcx, rdi; hFindFile
0x140005de0  call    cs:__imp_FindNextFileW
0x140005de6  test    eax, eax
0x140005de8  jnz     loc_140005C6E
0x140005dee  call    cs:__imp_GetLastError
0x140005df4  cmp     eax, 12h
0x140005df7  jnz     loc_140005F56
0x140005dfd  test    r15b, 1
0x140005e01  jnz     loc_140005F64
0x140005e07  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140005e0b  jz      loc_140005F3F
0x140005e11  lea     ebx, [rax-0Eh]
0x140005e14  mov     dword ptr [rsp+2F0h+hFile], 3
0x140005e1c  mov     r9d, ebx; dwBufferSize
0x140005e1f  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x140005e24  lea     edx, [rax+3]; FileInformationClass
0x140005e27  mov     rcx, r14; hFile
0x140005e2a  call    cs:__imp_SetFileInformationByHandle
0x140005e30  test    eax, eax
0x140005e32  jnz     loc_140005F64
0x140005e38  call    cs:__imp_GetLastError
0x140005e3e  cmp     eax, 5
0x140005e41  jz      loc_140005F23
0x140005e47  lea     r9d, [rbx-3]; dwBufferSize
0x140005e4b  mov     [rsp+2F0h+FileInformation], 1
0x140005e50  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x140005e55  mov     edx, ebx; FileInformationClass
0x140005e57  mov     rcx, r14; hFile
0x140005e5a  call    cs:__imp_SetFileInformationByHandle
0x140005e60  test    eax, eax
0x140005e62  jnz     loc_140005F64
0x140005e68  mov     edx, 171h; void *
0x140005e6d  mov     rcx, [rbp+1F8h]; this
0x140005e74  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005e7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005e80  mov     esi, eax
0x140005e82  jmp     loc_140005FAE
0x140005e87  mov     rcx, [rbp+1F8h]; this
0x140005e8e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005e95  mov     edx, 131h; void *
0x140005e9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005e9f  mov     esi, eax
0x140005ea1  jmp     loc_140005D2C
0x140005ea6  call    cs:__imp_GetLastError
0x140005eac  test    eax, eax
0x140005eae  jz      short loc_140005EC6
0x140005eb0  mov     rcx, [rbp+1F8h]; this
0x140005eb7  mov     r9d, eax; char *
0x140005eba  mov     edx, 136h; void *
0x140005ebf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140005ec4  jmp     short loc_140005E9F
0x140005ec6  lea     rcx, [rsp+2F0h+hFile]
0x140005ecb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140005ed0  lea     rcx, [rsp+2F0h+var_2C0]
0x140005ed5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005eda  lea     rcx, [rsp+2F0h+var_2B0]
0x140005edf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140005ee4  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005ee9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005eee  mov     esi, r12d
0x140005ef1  jmp     loc_140005FC2
0x140005ef6  mov     edx, 150h; void *
0x140005efb  mov     rcx, [rbp+1F8h]; this
0x140005f02  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005f09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005f0e  mov     esi, eax
0x140005f10  jmp     loc_140005FA4
0x140005f15  mov     edx, 145h
0x140005f1a  jmp     short loc_140005EFB
0x140005f1c  mov     edx, 141h
0x140005f21  jmp     short loc_140005EFB
0x140005f23  mov     edx, 176h; void *
0x140005f28  mov     r9d, 5; char *
0x140005f2e  mov     rcx, [rbp+1F8h]; this
0x140005f35  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140005f3a  jmp     loc_140005E80
0x140005f3f  mov     rcx, rbx; lpPathName
0x140005f42  call    cs:__imp_RemoveDirectoryW
0x140005f48  test    eax, eax
0x140005f4a  jnz     short loc_140005F64
0x140005f4c  mov     edx, 17Dh
0x140005f51  jmp     loc_140005E6D
0x140005f56  test    eax, eax
0x140005f58  jz      short loc_140005F64
0x140005f5a  mov     r9d, eax
0x140005f5d  mov     edx, 15Ch
0x140005f62  jmp     short loc_140005F2E
0x140005f64  lea     rcx, [rsp+2F0h+var_2B0]
0x140005f69  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140005f6e  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005f73  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005f78  lea     rcx, [rsp+2F0h+pszPathIn]
0x140005f7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005f82  xor     eax, eax
0x140005f84  jmp     loc_14000600A
0x140005f89  mov     rcx, [rbp+1F8h]; this
0x140005f90  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005f97  mov     r9d, eax; char *
0x140005f9a  mov     edx, 120h; void *
0x140005f9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005fa4  lea     rcx, [rsp+2F0h+var_2C0]
0x140005fa9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005fae  lea     rcx, [rsp+2F0h+var_2B0]
0x140005fb3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140005fb8  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005fbd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005fc2  lea     rcx, [rsp+2F0h+pszPathIn]
0x140005fc7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005fcc  mov     eax, esi
0x140005fce  jmp     short loc_14000600A
0x140005fd0  mov     rcx, [rbp+1F8h]; this
0x140005fd7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005fde  mov     edx, 115h; void *
0x140005fe3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005fe8  lea     rcx, [rsp+2F0h+var_2B0]
0x140005fed  mov     ebx, eax
0x140005fef  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140005ff4  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005ff9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005ffe  lea     rcx, [rsp+2F0h+pszPathIn]
0x140006003  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006008  mov     eax, ebx
0x14000600a  mov     rcx, [rbp+1F0h+var_40]
0x140006011  xor     rcx, rsp; StackCookie
0x140006014  call    __security_check_cookie
0x140006019  add     rsp, 2C0h
0x140006020  pop     r15
0x140006022  pop     r14
0x140006024  pop     r12
0x140006026  pop     rdi
0x140006027  pop     rsi
0x140006028  pop     rbx
0x140006029  pop     rbp
0x14000602a  retn
```
