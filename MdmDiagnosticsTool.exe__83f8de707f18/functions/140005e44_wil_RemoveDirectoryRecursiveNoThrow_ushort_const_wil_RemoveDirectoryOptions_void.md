# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x140005e44`
- end: `0x1400063b7`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005e44`
- `0x140008694`

## callees

- `0x140002338`
- `0x140002ee4`
- `0x1400033f8`
- `0x140003424`
- `0x140003450`
- `0x1400036c0`
- `0x140005e44`
- `0x1400065c4`
- `0x1400065e4`
- `0x14000660c`
- `0x140006d38`
- `0x1400080e4`
- `0x140008294`
- `0x140009cc6`
- `0x140009d00`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400060e4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400060e4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000610a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000610a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140005f81`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140005f81`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140006197`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400061d3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140006197`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400061d3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400060b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000611b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400060b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000611b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140006088`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400062c7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140006088`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400062c7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140006141`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140006141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400061ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400061ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006225`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005f33`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005ff1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005f33`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140005ff1`

## string_xrefs

- `0x140005ef5`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140005f4c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140006052`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1400061f3`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x14000620d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140006287`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x14000631b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x140006362`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x140005e44  push    rbp
0x140005e46  push    rbx
0x140005e47  push    rsi
0x140005e48  push    rdi
0x140005e49  push    r12
0x140005e4b  push    r14
0x140005e4d  push    r15
0x140005e4f  lea     rbp, [rsp-1C0h]
0x140005e57  sub     rsp, 2C0h
0x140005e5e  mov     rax, cs:__security_cookie
0x140005e65  xor     rax, rsp
0x140005e68  mov     [rbp+1F0h+var_40], rax
0x140005e6f  xor     r12d, r12d
0x140005e72  mov     r14, r8
0x140005e75  mov     [rsp+2F0h+pszPathIn], r12
0x140005e7a  mov     r15d, edx
0x140005e7d  mov     rbx, rcx
0x140005e80  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x140005e85  test    al, al
0x140005e87  jz      short loc_140005ED3
0x140005e89  or      r8, 0FFFFFFFFFFFFFFFFh
0x140005e8d  lea     rcx, [rsp+2F0h+var_2B0]
0x140005e92  mov     rdx, rbx
0x140005e95  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140005e9a  lea     rdx, [rsp+2F0h+var_2B0]
0x140005e9f  lea     rcx, [rsp+2F0h+pszPathIn]
0x140005ea4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140005ea9  lea     rcx, [rsp+2F0h+var_2B0]
0x140005eae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005eb3  mov     rbx, [rsp+2F0h+pszPathIn]
0x140005eb8  test    rbx, rbx
0x140005ebb  jnz     short loc_140005ECC
0x140005ebd  mov     esi, 8007000Eh
0x140005ec2  mov     edx, 104h
0x140005ec7  mov     r9d, esi
0x140005eca  jmp     short loc_140005EEE
0x140005ecc  mov     edi, 10h
0x140005ed1  jmp     short loc_140005F10
0x140005ed3  lea     rdx, [rsp+2F0h+pszPathIn]
0x140005ed8  mov     rcx, rbx
0x140005edb  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x140005ee0  mov     esi, eax
0x140005ee2  test    eax, eax
0x140005ee4  jns     short loc_140005F06
0x140005ee6  mov     r9d, eax; char *
0x140005ee9  mov     edx, 10Ch; void *
0x140005eee  mov     rcx, [rbp+1F8h]; this
0x140005ef5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f01  jmp     loc_14000634D
0x140005f06  mov     rbx, [rsp+2F0h+pszPathIn]
0x140005f0b  mov     edi, 1
0x140005f10  xor     edx, edx
0x140005f12  mov     [rsp+2F0h+ppszPathOut], r12
0x140005f17  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140005f1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140005f21  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x140005f26  mov     r8d, edi; dwFlags
0x140005f29  lea     rdx, pszMore; "*"
0x140005f30  mov     rcx, rbx; pszPathIn
0x140005f33  call    cs:__imp_PathAllocCombine
0x140005f3a  nop     dword ptr [rax+rax+00h]
0x140005f3f  mov     esi, eax
0x140005f41  test    eax, eax
0x140005f43  jns     short loc_140005F65
0x140005f45  mov     rcx, [rbp+1F8h]; this
0x140005f4c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005f53  mov     r9d, eax; char *
0x140005f56  mov     edx, 111h; void *
0x140005f5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f60  jmp     loc_140006343
0x140005f65  xor     edx, edx; Val
0x140005f67  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x140005f6c  mov     r8d, 250h; Size
0x140005f72  call    memset_0
0x140005f77  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x140005f7c  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x140005f81  call    cs:__imp_FindFirstFileW
0x140005f88  nop     dword ptr [rax+rax+00h]
0x140005f8d  mov     rdi, rax
0x140005f90  mov     [rsp+2F0h+var_2B0], rax
0x140005f95  dec     rax
0x140005f98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005f9c  ja      loc_14000635B
0x140005fa2  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x140005fa7  jz      short loc_140005FCE
0x140005fa9  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x140005fae  jnz     short loc_140005FCE
0x140005fb0  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x140005fb4  test    ax, ax
0x140005fb7  jz      loc_140006139
0x140005fbd  cmp     ax, 2Eh ; '.'
0x140005fc1  jnz     short loc_140005FCE
0x140005fc3  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x140005fc8  jz      loc_140006139
0x140005fce  xor     edx, edx
0x140005fd0  mov     [rsp+2F0h+var_2C0], r12
0x140005fd5  lea     rcx, [rsp+2F0h+var_2C0]
0x140005fda  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140005fdf  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x140005fe4  mov     r8d, 18h; dwFlags
0x140005fea  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x140005fee  mov     rcx, rbx; pszPathIn
0x140005ff1  call    cs:__imp_PathAllocCombine
0x140005ff8  nop     dword ptr [rax+rax+00h]
0x140005ffd  mov     esi, eax
0x140005fff  test    eax, eax
0x140006001  js      loc_140006314
0x140006007  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x14000600c  jz      loc_1400060AB
0x140006012  mov     rdx, [rsp+2F0h+var_2C0]
0x140006017  lea     r8, [rsp+2F0h+FindFileData]
0x14000601c  lea     rcx, [rsp+2F0h+hFile]
0x140006021  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x140006026  mov     r8, [rsp+2F0h+hFile]
0x14000602b  lea     rax, [r8-1]
0x14000602f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006033  ja      short loc_140006075
0x140006035  mov     rcx, [rsp+2F0h+var_2C0]
0x14000603a  mov     edx, r15d
0x14000603d  and     edx, 0FFFFFFFEh
0x140006040  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x140006045  mov     esi, eax
0x140006047  test    eax, eax
0x140006049  jns     short loc_14000609C
0x14000604b  mov     rcx, [rbp+1F8h]; this
0x140006052  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006059  mov     r9d, eax; char *
0x14000605c  mov     edx, 12Ch; void *
0x140006061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006066  lea     rcx, [rsp+2F0h+hFile]
0x14000606b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140006070  jmp     loc_14000632F
0x140006075  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x14000607d  jz      loc_140006225
0x140006083  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x140006088  call    cs:__imp_RemoveDirectoryW
0x14000608f  nop     dword ptr [rax+rax+00h]
0x140006094  test    eax, eax
0x140006096  jz      loc_140006206
0x14000609c  lea     rcx, [rsp+2F0h+hFile]
0x1400060a1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400060a6  jmp     loc_14000612F
0x1400060ab  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1400060b0  call    cs:__imp_DeleteFileW
0x1400060b7  nop     dword ptr [rax+rax+00h]
0x1400060bc  test    eax, eax
0x1400060be  jnz     short loc_14000612F
0x1400060c0  test    r15b, 2
0x1400060c4  jz      loc_1400062A1
0x1400060ca  call    cs:__imp_GetLastError
0x1400060d1  nop     dword ptr [rax+rax+00h]
0x1400060d6  cmp     eax, 5
0x1400060d9  jnz     loc_1400062A1
0x1400060df  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1400060e4  call    cs:__imp_GetFileAttributesW
0x1400060eb  nop     dword ptr [rax+rax+00h]
0x1400060f0  test    al, 1
0x1400060f2  jz      loc_14000629A
0x1400060f8  and     eax, 0FFFFFFFEh
0x1400060fb  mov     ecx, 80h
0x140006100  cmovz   eax, ecx
0x140006103  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x140006108  mov     edx, eax; dwFileAttributes
0x14000610a  call    cs:__imp_SetFileAttributesW
0x140006111  nop     dword ptr [rax+rax+00h]
0x140006116  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x14000611b  call    cs:__imp_DeleteFileW
0x140006122  nop     dword ptr [rax+rax+00h]
0x140006127  test    eax, eax
0x140006129  jz      loc_14000627B
0x14000612f  lea     rcx, [rsp+2F0h+var_2C0]
0x140006134  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006139  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x14000613e  mov     rcx, rdi; hFindFile
0x140006141  call    cs:__imp_FindNextFileW
0x140006148  nop     dword ptr [rax+rax+00h]
0x14000614d  test    eax, eax
0x14000614f  jnz     loc_140005FA2
0x140006155  call    cs:__imp_GetLastError
0x14000615c  nop     dword ptr [rax+rax+00h]
0x140006161  cmp     eax, 12h
0x140006164  jnz     loc_1400062E1
0x14000616a  test    r15b, 1
0x14000616e  jnz     loc_1400062EF
0x140006174  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140006178  jz      loc_1400062C4
0x14000617e  lea     ebx, [rax-0Eh]
0x140006181  mov     dword ptr [rsp+2F0h+hFile], 3
0x140006189  mov     r9d, ebx; dwBufferSize
0x14000618c  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x140006191  lea     edx, [rax+3]; FileInformationClass
0x140006194  mov     rcx, r14; hFile
0x140006197  call    cs:__imp_SetFileInformationByHandle
0x14000619e  nop     dword ptr [rax+rax+00h]
0x1400061a3  test    eax, eax
0x1400061a5  jnz     loc_1400062EF
0x1400061ab  call    cs:__imp_GetLastError
0x1400061b2  nop     dword ptr [rax+rax+00h]
0x1400061b7  cmp     eax, 5
0x1400061ba  jz      loc_1400062A8
0x1400061c0  lea     r9d, [rbx-3]; dwBufferSize
0x1400061c4  mov     [rsp+2F0h+FileInformation], 1
0x1400061c9  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1400061ce  mov     edx, ebx; FileInformationClass
0x1400061d0  mov     rcx, r14; hFile
0x1400061d3  call    cs:__imp_SetFileInformationByHandle
0x1400061da  nop     dword ptr [rax+rax+00h]
0x1400061df  test    eax, eax
0x1400061e1  jnz     loc_1400062EF
0x1400061e7  mov     edx, 171h; void *
0x1400061ec  mov     rcx, [rbp+1F8h]; this
0x1400061f3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400061fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400061ff  mov     esi, eax
0x140006201  jmp     loc_140006339
0x140006206  mov     rcx, [rbp+1F8h]; this
0x14000620d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006214  mov     edx, 131h; void *
0x140006219  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000621e  mov     esi, eax
0x140006220  jmp     loc_140006066
0x140006225  call    cs:__imp_GetLastError
0x14000622c  nop     dword ptr [rax+rax+00h]
0x140006231  test    eax, eax
0x140006233  jz      short loc_14000624B
0x140006235  mov     rcx, [rbp+1F8h]; this
0x14000623c  mov     r9d, eax; char *
0x14000623f  mov     edx, 136h; void *
0x140006244  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140006249  jmp     short loc_14000621E
0x14000624b  lea     rcx, [rsp+2F0h+hFile]
0x140006250  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140006255  lea     rcx, [rsp+2F0h+var_2C0]
0x14000625a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000625f  lea     rcx, [rsp+2F0h+var_2B0]
0x140006264  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140006269  lea     rcx, [rsp+2F0h+ppszPathOut]
0x14000626e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006273  mov     esi, r12d
0x140006276  jmp     loc_14000634D
0x14000627b  mov     edx, 150h; void *
0x140006280  mov     rcx, [rbp+1F8h]; this
0x140006287  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000628e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006293  mov     esi, eax
0x140006295  jmp     loc_14000632F
0x14000629a  mov     edx, 145h
0x14000629f  jmp     short loc_140006280
0x1400062a1  mov     edx, 141h
0x1400062a6  jmp     short loc_140006280
0x1400062a8  mov     edx, 176h; void *
0x1400062ad  mov     r9d, 5; char *
0x1400062b3  mov     rcx, [rbp+1F8h]; this
0x1400062ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400062bf  jmp     loc_1400061FF
0x1400062c4  mov     rcx, rbx; lpPathName
0x1400062c7  call    cs:__imp_RemoveDirectoryW
0x1400062ce  nop     dword ptr [rax+rax+00h]
0x1400062d3  test    eax, eax
0x1400062d5  jnz     short loc_1400062EF
0x1400062d7  mov     edx, 17Dh
0x1400062dc  jmp     loc_1400061EC
0x1400062e1  test    eax, eax
0x1400062e3  jz      short loc_1400062EF
0x1400062e5  mov     r9d, eax
0x1400062e8  mov     edx, 15Ch
0x1400062ed  jmp     short loc_1400062B3
0x1400062ef  lea     rcx, [rsp+2F0h+var_2B0]
0x1400062f4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1400062f9  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1400062fe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006303  lea     rcx, [rsp+2F0h+pszPathIn]
0x140006308  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000630d  xor     eax, eax
0x14000630f  jmp     loc_140006395
0x140006314  mov     rcx, [rbp+1F8h]; this
0x14000631b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006322  mov     r9d, eax; char *
0x140006325  mov     edx, 120h; void *
0x14000632a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000632f  lea     rcx, [rsp+2F0h+var_2C0]
0x140006334  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006339  lea     rcx, [rsp+2F0h+var_2B0]
0x14000633e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x140006343  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140006348  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000634d  lea     rcx, [rsp+2F0h+pszPathIn]
0x140006352  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140006357  mov     eax, esi
0x140006359  jmp     short loc_140006395
0x14000635b  mov     rcx, [rbp+1F8h]; this
0x140006362  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006369  mov     edx, 115h; void *
0x14000636e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006373  lea     rcx, [rsp+2F0h+var_2B0]
0x140006378  mov     ebx, eax
0x14000637a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14000637f  lea     rcx, [rsp+2F0h+ppszPathOut]
0x140006384  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
