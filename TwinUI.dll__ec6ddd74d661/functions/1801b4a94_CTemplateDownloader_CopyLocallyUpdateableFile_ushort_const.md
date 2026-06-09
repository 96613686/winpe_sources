# CTemplateDownloader::CopyLocallyUpdateableFile(ushort const *)

- ea: `0x1801b4a94`
- end: `0x1801b4e40`
- name: `?CopyLocallyUpdateableFile@CTemplateDownloader@@QEAAXPEBG@Z`
- size: `940`
- prototype: `void(CTemplateDownloader *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b646c`

## callees

- `0x180041d1c`
- `0x180041f54`
- `0x18006a010`
- `0x180076bec`
- `0x18008a384`
- `0x180142e10`
- `0x180143a7c`
- `0x1801b4a94`
- `0x1801b5810`
- `0x1801b590c`
- `0x1801b6944`
- `0x1801b69d8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4bc4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4ca1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4d5a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4bc4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4ca1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b4d5a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b4dd8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b4dd8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801b4dbf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801b4dbf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801b4ce7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801b4ce7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801b4b97`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801b4b97`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b4d71`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b4d71`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801b4c04`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801b4c04`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801b4c4f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801b4c4f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801b4d81`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801b4d81`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x1801b4af8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x1801b4af8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b4d37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b4d37`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801b4b82`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801b4b82`

## string_xrefs

- `0x1801b4c67`: `%s*.dll`
- `0x1801b4d0f`: `%s.dll`

## pseudocode

```c
void __fastcall CTemplateDownloader::CopyLocallyUpdateableFile(CTemplateDownloader *this, const unsigned __int16 *a2)
{
  unsigned __int64 i; // rbx
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  unsigned __int16 **v7; // r8
  unsigned __int16 **v8; // rdx
  const WCHAR *v9; // rsi
  __int64 v10; // r8
  HANDLE FirstFile; // rax
  const unsigned __int16 *v12; // r8
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+48h] [rbp-B8h]
  LPCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR pszStr2[3]; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR pszMore[4]; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPathOut[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR FileName[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR v29[264]; // [rsp+730h] [rbp+630h] BYREF

  for ( i = 0; i < *((_QWORD *)this + 7); ++i )
  {
    v5 = -1;
    v6 = *(const WCHAR **)(*((_QWORD *)this + 6) + 8 * i);
    do
      ++v5;
    while ( v6[v5] );
    if ( !StrCmpNIW(v6, a2, v5) )
    {
      lpExistingFileName = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpExistingFileName);
      v21 = -1;
      v22 = -1;
      if ( (int)TemplateDownloadHelpers::GetFilePathForDownloadedTemplate(
                  a2,
                  (const unsigned __int16 *)&lpExistingFileName,
                  v7) >= 0 )
      {
        pszPath = 0;
        v18 = 0;
        v19 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
        v18 = -1;
        v19 = -1;
        if ( (int)TemplateDownloadHelpers::GetLocalDirectoryPath((TemplateDownloadHelpers *)&pszPath, v8) >= 0 )
        {
          v9 = pszPath;
          if ( (PathIsDirectoryW(pszPath) || CreateDirectoryW(v9, 0))
            && PathCchCombine(pszPathOut, 0x104u, v9, *(PCWSTR *)(*((_QWORD *)this + 6) + 8 * i)) >= 0
            && StringCchCatW(pszPathOut, 0x104u, L".dll") >= 0
            && CopyFileW(lpExistingFileName, pszPathOut, 0) )
          {
            ppszPath = 0;
            v15 = 0;
            v16 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
            v15 = -1;
            v16 = -1;
            if ( SHGetKnownFolderPath(&FOLDERID_SearchTemplates, 0x8000u, 0, &ppszPath) >= 0 )
            {
              v10 = *((_QWORD *)this + 6);
              memset(pszMore, 0, 24);
              if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                          pszMore,
                          L"%s*.dll",
                          *(_QWORD *)(v10 + 8 * i)) >= 0
                && PathCchCombine(FileName, 0x104u, ppszPath, pszMore[0]) >= 0 )
              {
                memset_0(&FindFileData, 0, sizeof(FindFileData));
                hFindFile = 0;
                FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
                if ( (int)ResultFromWin32Handle(FirstFile, &hFindFile) >= 0 )
                {
                  memset(pszStr2, 0, sizeof(pszStr2));
                  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                              pszStr2,
                              L"%s.dll",
                              a2) >= 0 )
                  {
                    do
                    {
                      if ( StrCmpICW(FindFileData.cFileName, pszStr2[0]) )
                      {
                        if ( PathCchCombine(v29, 0x104u, ppszPath, FindFileData.cFileName) >= 0 )
                        {
                          DeleteFileW(v29);
                          PathRemoveExtensionW(FindFileData.cFileName);
                          wil::AcquireSRWLockExclusive(v23, (char *)this + 168);
                          TemplateDownloadHelpers::RemoveTemplateFromArray(
                            (CTemplateDownloader *)((char *)this + 176),
                            (struct CSimpleCaseInsensitiveOrdinalStringArray *)FindFileData.cFileName,
                            v12);
                          Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v23);
                        }
                      }
                    }
                    while ( FindNextFileW(hFindFile, &FindFileData) );
                  }
                  FindClose(hFindFile);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszStr2);
                }
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszMore);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpExistingFileName);
      return;
    }
  }
}

```

## disassembly

```asm
0x1801b4a94  mov     [rsp-8+arg_10], rbx
0x1801b4a99  mov     [rsp-8+arg_18], rsi
0x1801b4a9e  push    rbp
0x1801b4a9f  push    rdi
0x1801b4aa0  push    r12
0x1801b4aa2  push    r14
0x1801b4aa4  push    r15
0x1801b4aa6  lea     rbp, [rsp-850h]
0x1801b4aae  sub     rsp, 950h
0x1801b4ab5  mov     rax, cs:__security_cookie
0x1801b4abc  xor     rax, rsp
0x1801b4abf  mov     [rbp+870h+var_30], rax
0x1801b4ac6  xor     r15d, r15d
0x1801b4ac9  mov     r14, rdx
0x1801b4acc  mov     ebx, r15d
0x1801b4acf  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801b4ad3  mov     rdi, rcx
0x1801b4ad6  cmp     rbx, [rdi+38h]
0x1801b4ada  jnb     loc_1801B4E14
0x1801b4ae0  mov     rax, [rdi+30h]
0x1801b4ae4  mov     r8, r12
0x1801b4ae7  mov     rcx, [rax+rbx*8]; psz1
0x1801b4aeb  inc     r8; nChar
0x1801b4aee  cmp     [rcx+r8*2], r15w
0x1801b4af3  jnz     short loc_1801B4AEB
0x1801b4af5  mov     rdx, r14; psz2
0x1801b4af8  call    cs:__imp_StrCmpNIW
0x1801b4aff  nop     dword ptr [rax+rax+00h]
0x1801b4b04  test    eax, eax
0x1801b4b06  jz      short loc_1801B4B0D
0x1801b4b08  inc     rbx
0x1801b4b0b  jmp     short loc_1801B4AD6
0x1801b4b0d  lea     rcx, [rsp+970h+lpExistingFileName]
0x1801b4b12  mov     [rsp+970h+lpExistingFileName], r15
0x1801b4b17  mov     [rsp+970h+var_900], r15
0x1801b4b1c  mov     [rsp+970h+var_8F8], r15
0x1801b4b21  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4b26  lea     rdx, [rsp+970h+lpExistingFileName]; unsigned __int16 *
0x1801b4b2b  mov     [rsp+970h+var_900], r12
0x1801b4b30  mov     rcx, r14; pszMore
0x1801b4b33  mov     [rsp+970h+var_8F8], r12
0x1801b4b38  call    ?GetFilePathForDownloadedTemplate@TemplateDownloadHelpers@@YAJPEBGPEAPEAG@Z; TemplateDownloadHelpers::GetFilePathForDownloadedTemplate(ushort const *,ushort * *)
0x1801b4b3d  test    eax, eax
0x1801b4b3f  js      loc_1801B4E0A
0x1801b4b45  lea     rcx, [rsp+970h+pszPath]
0x1801b4b4a  mov     [rsp+970h+pszPath], r15
0x1801b4b4f  mov     [rsp+970h+var_918], r15
0x1801b4b54  mov     [rsp+970h+var_910], r15
0x1801b4b59  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4b5e  lea     rcx, [rsp+970h+pszPath]; this
0x1801b4b63  mov     [rsp+970h+var_918], r12
0x1801b4b68  mov     [rsp+970h+var_910], r12
0x1801b4b6d  call    ?GetLocalDirectoryPath@TemplateDownloadHelpers@@YAJPEAPEAG@Z; TemplateDownloadHelpers::GetLocalDirectoryPath(ushort * *)
0x1801b4b72  test    eax, eax
0x1801b4b74  js      loc_1801B4E00
0x1801b4b7a  mov     rsi, [rsp+970h+pszPath]
0x1801b4b7f  mov     rcx, rsi; pszPath
0x1801b4b82  call    cs:__imp_PathIsDirectoryW
0x1801b4b89  nop     dword ptr [rax+rax+00h]
0x1801b4b8e  test    eax, eax
0x1801b4b90  jnz     short loc_1801B4BAB
0x1801b4b92  xor     edx, edx; lpSecurityAttributes
0x1801b4b94  mov     rcx, rsi; lpPathName
0x1801b4b97  call    cs:__imp_CreateDirectoryW
0x1801b4b9e  nop     dword ptr [rax+rax+00h]
0x1801b4ba3  test    eax, eax
0x1801b4ba5  jz      loc_1801B4E00
0x1801b4bab  mov     r9, [rdi+30h]
0x1801b4baf  lea     rcx, [rbp+870h+pszPathOut]; pszPathOut
0x1801b4bb6  mov     r8, rsi; pszPathIn
0x1801b4bb9  mov     esi, 104h
0x1801b4bbe  mov     edx, esi; cchPathOut
0x1801b4bc0  mov     r9, [r9+rbx*8]; pszMore
0x1801b4bc4  call    cs:__imp_PathCchCombine
0x1801b4bcb  nop     dword ptr [rax+rax+00h]
0x1801b4bd0  test    eax, eax
0x1801b4bd2  js      loc_1801B4E00
0x1801b4bd8  lea     r8, aDll_0; ".dll"
0x1801b4bdf  mov     edx, esi; unsigned __int64
0x1801b4be1  lea     rcx, [rbp+870h+pszPathOut]; unsigned __int16 *
0x1801b4be8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b4bed  test    eax, eax
0x1801b4bef  js      loc_1801B4E00
0x1801b4bf5  mov     rcx, [rsp+970h+lpExistingFileName]; lpExistingFileName
0x1801b4bfa  lea     rdx, [rbp+870h+pszPathOut]; lpNewFileName
0x1801b4c01  xor     r8d, r8d; bFailIfExists
0x1801b4c04  call    cs:__imp_CopyFileW
0x1801b4c0b  nop     dword ptr [rax+rax+00h]
0x1801b4c10  test    eax, eax
0x1801b4c12  jz      loc_1801B4E00
0x1801b4c18  lea     rcx, [rsp+970h+ppszPath]
0x1801b4c1d  mov     [rsp+970h+ppszPath], r15
0x1801b4c22  mov     [rsp+970h+var_930], r15
0x1801b4c27  mov     [rsp+970h+var_928], r15
0x1801b4c2c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4c31  lea     r9, [rsp+970h+ppszPath]; ppszPath
0x1801b4c36  mov     [rsp+970h+var_930], r12
0x1801b4c3b  xor     r8d, r8d; hToken
0x1801b4c3e  mov     [rsp+970h+var_928], r12
0x1801b4c43  mov     edx, 8000h; dwFlags
0x1801b4c48  lea     rcx, FOLDERID_SearchTemplates; rfid
0x1801b4c4f  call    cs:__imp_SHGetKnownFolderPath
0x1801b4c56  nop     dword ptr [rax+rax+00h]
0x1801b4c5b  test    eax, eax
0x1801b4c5d  js      loc_1801B4DF6
0x1801b4c63  mov     r8, [rdi+30h]
0x1801b4c67  lea     rdx, aSDll; "%s*.dll"
0x1801b4c6e  lea     rcx, [rbp+870h+pszMore]
0x1801b4c72  mov     [rbp+870h+pszMore], r15
0x1801b4c76  mov     [rbp+870h+var_8C8], r15
0x1801b4c7a  mov     [rbp+870h+var_8C0], r15
0x1801b4c7e  mov     r8, [r8+rbx*8]
0x1801b4c82  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801b4c87  test    eax, eax
0x1801b4c89  js      loc_1801B4DED
0x1801b4c8f  mov     r9, [rbp+870h+pszMore]; pszMore
0x1801b4c93  lea     rcx, [rbp+870h+FileName]; pszPathOut
0x1801b4c9a  mov     r8, [rsp+970h+ppszPath]; pszPathIn
0x1801b4c9f  mov     edx, esi; cchPathOut
0x1801b4ca1  call    cs:__imp_PathCchCombine
0x1801b4ca8  nop     dword ptr [rax+rax+00h]
0x1801b4cad  test    eax, eax
0x1801b4caf  js      loc_1801B4DED
0x1801b4cb5  xor     edx, edx; Val
0x1801b4cb7  lea     rcx, [rbp+870h+FindFileData]; void *
0x1801b4cbb  mov     r8d, 250h; Size
0x1801b4cc1  call    memset_0
0x1801b4cc6  xor     r9d, r9d; fSearchOp
0x1801b4cc9  mov     [rsp+970h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x1801b4cce  lea     r8, [rbp+870h+FindFileData]; lpFindFileData
0x1801b4cd2  mov     [rsp+970h+hFindFile], r15
0x1801b4cd7  lea     rcx, [rbp+870h+FileName]; lpFileName
0x1801b4cde  mov     [rsp+970h+lpSearchFilter], r15; lpSearchFilter
0x1801b4ce3  lea     edx, [r9+1]; fInfoLevelId
0x1801b4ce7  call    cs:__imp_FindFirstFileExW
0x1801b4cee  nop     dword ptr [rax+rax+00h]
0x1801b4cf3  mov     rcx, rax; void *
0x1801b4cf6  lea     rdx, [rsp+970h+hFindFile]; void **
0x1801b4cfb  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801b4d00  test    eax, eax
0x1801b4d02  js      loc_1801B4DED
0x1801b4d08  mov     r8, r14
0x1801b4d0b  mov     [rbp+870h+pszStr2], r15
0x1801b4d0f  lea     rdx, aSDll_0; "%s.dll"
0x1801b4d16  mov     [rbp+870h+var_8E0], r15
0x1801b4d1a  lea     rcx, [rbp+870h+pszStr2]
0x1801b4d1e  mov     [rbp+870h+var_8D8], r15
0x1801b4d22  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801b4d27  test    eax, eax
0x1801b4d29  js      loc_1801B4DD3
0x1801b4d2f  mov     rdx, [rbp+870h+pszStr2]; pszStr2
0x1801b4d33  lea     rcx, [rbp+870h+pszStr1]; pszStr1
0x1801b4d37  call    cs:__imp_StrCmpICW
0x1801b4d3e  nop     dword ptr [rax+rax+00h]
0x1801b4d43  test    eax, eax
0x1801b4d45  jz      short loc_1801B4DB6
0x1801b4d47  mov     r8, [rsp+970h+ppszPath]; pszPathIn
0x1801b4d4c  lea     r9, [rbp+870h+pszStr1]; pszMore
0x1801b4d50  mov     rdx, rsi; cchPathOut
0x1801b4d53  lea     rcx, [rbp+870h+var_240]; pszPathOut
0x1801b4d5a  call    cs:__imp_PathCchCombine
0x1801b4d61  nop     dword ptr [rax+rax+00h]
0x1801b4d66  test    eax, eax
0x1801b4d68  js      short loc_1801B4DB6
0x1801b4d6a  lea     rcx, [rbp+870h+var_240]; lpFileName
0x1801b4d71  call    cs:__imp_DeleteFileW
0x1801b4d78  nop     dword ptr [rax+rax+00h]
0x1801b4d7d  lea     rcx, [rbp+870h+pszStr1]; pszPath
0x1801b4d81  call    cs:__imp_PathRemoveExtensionW
0x1801b4d88  nop     dword ptr [rax+rax+00h]
0x1801b4d8d  lea     rdx, [rdi+0A8h]
0x1801b4d94  lea     rcx, [rbp+870h+var_8F0]
0x1801b4d98  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b4d9d  lea     rcx, [rdi+0B0h]; this
0x1801b4da4  lea     rdx, [rbp+870h+pszStr1]; struct CSimpleCaseInsensitiveOrdinalStringArray *
0x1801b4da8  call    ?RemoveTemplateFromArray@TemplateDownloadHelpers@@YAJAEAVCSimpleCaseInsensitiveOrdinalStringArray@@PEBG@Z; TemplateDownloadHelpers::RemoveTemplateFromArray(CSimpleCaseInsensitiveOrdinalStringArray &,ushort const *)
0x1801b4dad  lea     rcx, [rbp+870h+var_8F0]; this
0x1801b4db1  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b4db6  mov     rcx, [rsp+970h+hFindFile]; hFindFile
0x1801b4dbb  lea     rdx, [rbp+870h+FindFileData]; lpFindFileData
0x1801b4dbf  call    cs:__imp_FindNextFileW
0x1801b4dc6  nop     dword ptr [rax+rax+00h]
0x1801b4dcb  test    eax, eax
0x1801b4dcd  jnz     loc_1801B4D2F
0x1801b4dd3  mov     rcx, [rsp+970h+hFindFile]; hFindFile
0x1801b4dd8  call    cs:__imp_FindClose
0x1801b4ddf  nop     dword ptr [rax+rax+00h]
0x1801b4de4  lea     rcx, [rbp+870h+pszStr2]
0x1801b4de8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4ded  lea     rcx, [rbp+870h+pszMore]
0x1801b4df1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4df6  lea     rcx, [rsp+970h+ppszPath]
0x1801b4dfb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4e00  lea     rcx, [rsp+970h+pszPath]
0x1801b4e05  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4e0a  lea     rcx, [rsp+970h+lpExistingFileName]
0x1801b4e0f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b4e14  mov     rcx, [rbp+870h+var_30]
0x1801b4e1b  xor     rcx, rsp; StackCookie
0x1801b4e1e  call    __security_check_cookie
0x1801b4e23  lea     r11, [rsp+970h+var_20]
0x1801b4e2b  mov     rbx, [r11+40h]
0x1801b4e2f  mov     rsi, [r11+48h]
0x1801b4e33  mov     rsp, r11
0x1801b4e36  pop     r15
0x1801b4e38  pop     r14
0x1801b4e3a  pop     r12
0x1801b4e3c  pop     rdi
0x1801b4e3d  pop     rbp
0x1801b4e3e  retn
```
