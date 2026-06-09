# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800109d4`
- end: `0x180010ee3`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ee40`
- `0x1800109d4`

## callees

- `0x18000b5f4`
- `0x18000dcd4`
- `0x18000e568`
- `0x18000e8bc`
- `0x18000e8e0`
- `0x18000e9c4`
- `0x1800109d4`
- `0x180010f34`
- `0x180010f54`
- `0x180010f78`
- `0x1800114fc`
- `0x180012790`
- `0x1800127fc`
- `0x18002120a`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d5e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010c4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010c4d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180010c98`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180010c98`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180010c6d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180010c6d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010b0b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010b0b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180010c06`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180010dfa`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180010c06`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180010dfa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c25`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c78`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c25`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c78`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180010ce2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180010d12`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180010ce2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180010d12`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180010ac3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180010b75`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180010ac3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180010b75`

## string_xrefs

- `0x180010a85`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010ad6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010bd0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010d2c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010d46`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010dba`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010e48`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180010e8f`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
  void *v37; // [rsp+40h] [rbp-C0h] BYREF
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
    auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v37);
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
            (__int64)a1,
            (__int64)&pszPathIn);
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
    auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&ppszPathOut);
    auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&pszPathIn);
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
          auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v35);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
          auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&ppszPathOut);
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
    auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v35);
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
          auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&ppszPathOut);
          auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&pszPathIn);
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
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v35);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
LABEL_63:
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&ppszPathOut);
LABEL_64:
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x1800109d4  push    rbp
0x1800109d6  push    rbx
0x1800109d7  push    rsi
0x1800109d8  push    rdi
0x1800109d9  push    r12
0x1800109db  push    r14
0x1800109dd  push    r15
0x1800109df  lea     rbp, [rsp-1C0h]
0x1800109e7  sub     rsp, 2C0h
0x1800109ee  mov     rax, cs:__security_cookie
0x1800109f5  xor     rax, rsp
0x1800109f8  mov     [rbp+1F0h+var_40], rax
0x1800109ff  xor     r12d, r12d
0x180010a02  mov     r14, r8
0x180010a05  mov     [rsp+2F0h+pszPathIn], r12
0x180010a0a  mov     r15d, edx
0x180010a0d  mov     rbx, rcx
0x180010a10  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180010a15  test    al, al
0x180010a17  jz      short loc_180010A63
0x180010a19  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010a1d  lea     rcx, [rsp+2F0h+var_2B0]
0x180010a22  mov     rdx, rbx
0x180010a25  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180010a2a  lea     rdx, [rsp+2F0h+var_2B0]
0x180010a2f  lea     rcx, [rsp+2F0h+pszPathIn]
0x180010a34  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180010a39  lea     rcx, [rsp+2F0h+var_2B0]
0x180010a3e  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010a43  mov     rbx, [rsp+2F0h+pszPathIn]
0x180010a48  test    rbx, rbx
0x180010a4b  jnz     short loc_180010A5C
0x180010a4d  mov     esi, 8007000Eh
0x180010a52  mov     edx, 104h
0x180010a57  mov     r9d, esi
0x180010a5a  jmp     short loc_180010A7E
0x180010a5c  mov     edi, 10h
0x180010a61  jmp     short loc_180010AA0
0x180010a63  lea     rdx, [rsp+2F0h+pszPathIn]
0x180010a68  mov     rcx, rbx
0x180010a6b  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x180010a70  mov     esi, eax
0x180010a72  test    eax, eax
0x180010a74  jns     short loc_180010A96
0x180010a76  mov     r9d, eax; char *
0x180010a79  mov     edx, 10Ch; void *
0x180010a7e  mov     rcx, [rbp+1F8h]; this
0x180010a85  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a91  jmp     loc_180010E7A
0x180010a96  mov     rbx, [rsp+2F0h+pszPathIn]
0x180010a9b  mov     edi, 1
0x180010aa0  xor     edx, edx
0x180010aa2  mov     [rsp+2F0h+ppszPathOut], r12
0x180010aa7  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180010aac  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010ab1  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x180010ab6  mov     r8d, edi; dwFlags
0x180010ab9  lea     rdx, pszMore; "*"
0x180010ac0  mov     rcx, rbx; pszPathIn
0x180010ac3  call    cs:__imp_PathAllocCombine
0x180010ac9  mov     esi, eax
0x180010acb  test    eax, eax
0x180010acd  jns     short loc_180010AEF
0x180010acf  mov     rcx, [rbp+1F8h]; this
0x180010ad6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010add  mov     r9d, eax; char *
0x180010ae0  mov     edx, 111h; void *
0x180010ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010aea  jmp     loc_180010E70
0x180010aef  xor     edx, edx; Val
0x180010af1  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180010af6  mov     r8d, 250h; Size
0x180010afc  call    memset_0
0x180010b01  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x180010b06  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180010b0b  call    cs:__imp_FindFirstFileW
0x180010b11  mov     rdi, rax
0x180010b14  mov     [rsp+2F0h+var_2B0], rax
0x180010b19  dec     rax
0x180010b1c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010b20  ja      loc_180010E88
0x180010b26  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180010b2b  jz      short loc_180010B52
0x180010b2d  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x180010b32  jnz     short loc_180010B52
0x180010b34  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x180010b38  test    ax, ax
0x180010b3b  jz      loc_180010C90
0x180010b41  cmp     ax, 2Eh ; '.'
0x180010b45  jnz     short loc_180010B52
0x180010b47  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x180010b4c  jz      loc_180010C90
0x180010b52  xor     edx, edx
0x180010b54  mov     [rsp+2F0h+var_2C0], r12
0x180010b59  lea     rcx, [rsp+2F0h+var_2C0]
0x180010b5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010b63  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x180010b68  mov     r8d, 18h; dwFlags
0x180010b6e  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x180010b72  mov     rcx, rbx; pszPathIn
0x180010b75  call    cs:__imp_PathAllocCombine
0x180010b7b  mov     esi, eax
0x180010b7d  test    eax, eax
0x180010b7f  js      loc_180010E41
0x180010b85  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180010b8a  jz      loc_180010C20
0x180010b90  mov     rdx, [rsp+2F0h+var_2C0]
0x180010b95  lea     r8, [rsp+2F0h+FindFileData]
0x180010b9a  lea     rcx, [rsp+2F0h+hFile]
0x180010b9f  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180010ba4  mov     r8, [rsp+2F0h+hFile]
0x180010ba9  lea     rax, [r8-1]
0x180010bad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010bb1  ja      short loc_180010BF3
0x180010bb3  mov     rcx, [rsp+2F0h+var_2C0]
0x180010bb8  mov     edx, r15d
0x180010bbb  and     edx, 0FFFFFFFEh
0x180010bbe  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180010bc3  mov     esi, eax
0x180010bc5  test    eax, eax
0x180010bc7  jns     short loc_180010C14
0x180010bc9  mov     rcx, [rbp+1F8h]; this
0x180010bd0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010bd7  mov     r9d, eax; char *
0x180010bda  mov     edx, 12Ch; void *
0x180010bdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010be4  lea     rcx, [rsp+2F0h+hFile]
0x180010be9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010bee  jmp     loc_180010E5C
0x180010bf3  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x180010bfb  jz      loc_180010D5E
0x180010c01  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x180010c06  call    cs:__imp_RemoveDirectoryW
0x180010c0c  test    eax, eax
0x180010c0e  jz      loc_180010D3F
0x180010c14  lea     rcx, [rsp+2F0h+hFile]
0x180010c19  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010c1e  jmp     short loc_180010C86
0x180010c20  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180010c25  call    cs:__imp_DeleteFileW
0x180010c2b  test    eax, eax
0x180010c2d  jnz     short loc_180010C86
0x180010c2f  test    r15b, 2
0x180010c33  jz      loc_180010DD4
0x180010c39  call    cs:__imp_GetLastError
0x180010c3f  cmp     eax, 5
0x180010c42  jnz     loc_180010DD4
0x180010c48  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180010c4d  call    cs:__imp_GetFileAttributesW
0x180010c53  test    al, 1
0x180010c55  jz      loc_180010DCD
0x180010c5b  and     eax, 0FFFFFFFEh
0x180010c5e  mov     ecx, 80h
0x180010c63  cmovz   eax, ecx
0x180010c66  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180010c6b  mov     edx, eax; dwFileAttributes
0x180010c6d  call    cs:__imp_SetFileAttributesW
0x180010c73  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180010c78  call    cs:__imp_DeleteFileW
0x180010c7e  test    eax, eax
0x180010c80  jz      loc_180010DAE
0x180010c86  lea     rcx, [rsp+2F0h+var_2C0]
0x180010c8b  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010c90  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180010c95  mov     rcx, rdi; hFindFile
0x180010c98  call    cs:__imp_FindNextFileW
0x180010c9e  test    eax, eax
0x180010ca0  jnz     loc_180010B26
0x180010ca6  call    cs:__imp_GetLastError
0x180010cac  cmp     eax, 12h
0x180010caf  jnz     loc_180010E0E
0x180010cb5  test    r15b, 1
0x180010cb9  jnz     loc_180010E1C
0x180010cbf  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180010cc3  jz      loc_180010DF7
0x180010cc9  lea     ebx, [rax-0Eh]
0x180010ccc  mov     dword ptr [rsp+2F0h+hFile], 3
0x180010cd4  mov     r9d, ebx; dwBufferSize
0x180010cd7  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x180010cdc  lea     edx, [rax+3]; FileInformationClass
0x180010cdf  mov     rcx, r14; hFile
0x180010ce2  call    cs:__imp_SetFileInformationByHandle
0x180010ce8  test    eax, eax
0x180010cea  jnz     loc_180010E1C
0x180010cf0  call    cs:__imp_GetLastError
0x180010cf6  cmp     eax, 5
0x180010cf9  jz      loc_180010DDB
0x180010cff  lea     r9d, [rbx-3]; dwBufferSize
0x180010d03  mov     [rsp+2F0h+FileInformation], 1
0x180010d08  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x180010d0d  mov     edx, ebx; FileInformationClass
0x180010d0f  mov     rcx, r14; hFile
0x180010d12  call    cs:__imp_SetFileInformationByHandle
0x180010d18  test    eax, eax
0x180010d1a  jnz     loc_180010E1C
0x180010d20  mov     edx, 171h; void *
0x180010d25  mov     rcx, [rbp+1F8h]; this
0x180010d2c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010d33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010d38  mov     esi, eax
0x180010d3a  jmp     loc_180010E66
0x180010d3f  mov     rcx, [rbp+1F8h]; this
0x180010d46  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010d4d  mov     edx, 131h; void *
0x180010d52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010d57  mov     esi, eax
0x180010d59  jmp     loc_180010BE4
0x180010d5e  call    cs:__imp_GetLastError
0x180010d64  test    eax, eax
0x180010d66  jz      short loc_180010D7E
0x180010d68  mov     rcx, [rbp+1F8h]; this
0x180010d6f  mov     r9d, eax; char *
0x180010d72  mov     edx, 136h; void *
0x180010d77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010d7c  jmp     short loc_180010D57
0x180010d7e  lea     rcx, [rsp+2F0h+hFile]
0x180010d83  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010d88  lea     rcx, [rsp+2F0h+var_2C0]
0x180010d8d  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010d92  lea     rcx, [rsp+2F0h+var_2B0]
0x180010d97  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180010d9c  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180010da1  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010da6  mov     esi, r12d
0x180010da9  jmp     loc_180010E7A
0x180010dae  mov     edx, 150h; void *
0x180010db3  mov     rcx, [rbp+1F8h]; this
0x180010dba  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010dc1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010dc6  mov     esi, eax
0x180010dc8  jmp     loc_180010E5C
0x180010dcd  mov     edx, 145h
0x180010dd2  jmp     short loc_180010DB3
0x180010dd4  mov     edx, 141h
0x180010dd9  jmp     short loc_180010DB3
0x180010ddb  mov     edx, 176h; void *
0x180010de0  mov     r9d, 5; char *
0x180010de6  mov     rcx, [rbp+1F8h]; this
0x180010ded  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010df2  jmp     loc_180010D38
0x180010df7  mov     rcx, rbx; lpPathName
0x180010dfa  call    cs:__imp_RemoveDirectoryW
0x180010e00  test    eax, eax
0x180010e02  jnz     short loc_180010E1C
0x180010e04  mov     edx, 17Dh
0x180010e09  jmp     loc_180010D25
0x180010e0e  test    eax, eax
0x180010e10  jz      short loc_180010E1C
0x180010e12  mov     r9d, eax
0x180010e15  mov     edx, 15Ch
0x180010e1a  jmp     short loc_180010DE6
0x180010e1c  lea     rcx, [rsp+2F0h+var_2B0]
0x180010e21  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180010e26  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180010e2b  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010e30  lea     rcx, [rsp+2F0h+pszPathIn]
0x180010e35  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010e3a  xor     eax, eax
0x180010e3c  jmp     loc_180010EC2
0x180010e41  mov     rcx, [rbp+1F8h]; this
0x180010e48  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010e4f  mov     r9d, eax; char *
0x180010e52  mov     edx, 120h; void *
0x180010e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e5c  lea     rcx, [rsp+2F0h+var_2C0]
0x180010e61  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010e66  lea     rcx, [rsp+2F0h+var_2B0]
0x180010e6b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180010e70  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180010e75  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010e7a  lea     rcx, [rsp+2F0h+pszPathIn]
0x180010e7f  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010e84  mov     eax, esi
0x180010e86  jmp     short loc_180010EC2
0x180010e88  mov     rcx, [rbp+1F8h]; this
0x180010e8f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010e96  mov     edx, 115h; void *
0x180010e9b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010ea0  lea     rcx, [rsp+2F0h+var_2B0]
0x180010ea5  mov     ebx, eax
0x180010ea7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180010eac  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180010eb1  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010eb6  lea     rcx, [rsp+2F0h+pszPathIn]
0x180010ebb  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180010ec0  mov     eax, ebx
0x180010ec2  mov     rcx, [rbp+1F0h+var_40]
0x180010ec9  xor     rcx, rsp; StackCookie
0x180010ecc  call    __security_check_cookie
0x180010ed1  add     rsp, 2C0h
0x180010ed8  pop     r15
0x180010eda  pop     r14
0x180010edc  pop     r12
0x180010ede  pop     rdi
0x180010edf  pop     rsi
0x180010ee0  pop     rbx
0x180010ee1  pop     rbp
0x180010ee2  retn
```
