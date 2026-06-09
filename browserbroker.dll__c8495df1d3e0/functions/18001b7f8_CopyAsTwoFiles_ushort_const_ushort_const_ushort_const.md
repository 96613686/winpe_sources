# CopyAsTwoFiles(ushort const *,ushort const *,ushort const *)

- ea: `0x18001b7f8`
- end: `0x18001b97a`
- name: `?CopyAsTwoFiles@@YAJPEBG00@Z`
- size: `386`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001baa0`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x18001b7f8`
- `0x18001be88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001b860`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001b860`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18001b90b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18001b90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b935`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b87e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b87e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b92f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b972`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b92f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b972`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x18001b8ca`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x18001b8ca`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18001b844`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18001b844`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001b8fa`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001b924`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001b8fa`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001b924`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001b89e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001b89e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CopyAsTwoFiles(LPCWSTR lpExistingFileName, PCWSTR pszPathIn, const unsigned __int16 *a3)
{
  HRESULT Extension; // ebx
  signed int LastError; // eax
  PCWSTR ppszExt; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR TempFileName[264]; // [rsp+450h] [rbp+350h] BYREF

  ppszExt = 0;
  Extension = PathCchFindExtension(lpExistingFileName, 0x104u, &ppszExt);
  if ( Extension < 0 || (unsigned int)_o__wcsicmp(ppszExt, L".url") )
    return (unsigned int)Extension;
  if ( !GetTempFileNameW(pszPathIn, a3, 0, TempFileName) )
    goto LABEL_8;
  Extension = PathCchCombine(pszPathOut, 0x104u, pszPathIn, TempFileName);
  if ( Extension >= 0 )
  {
    StringCchCopyW(pszPath, 0x104u, a3);
    PathCchRemoveExtension(pszPath, 0x104u);
    Extension = WriteStringToFile(pszPathOut, pszPath);
    if ( Extension < 0 )
    {
      DeleteFileW(pszPathOut);
      return (unsigned int)Extension;
    }
    PathCchRenameExtension(pszPathOut, 0x104u, L"url");
    if ( !CopyFileW(lpExistingFileName, pszPathOut, 0) )
    {
      PathCchRenameExtension(pszPathOut, 0x104u, L"tmp");
      DeleteFileW(pszPathOut);
LABEL_8:
      LastError = GetLastError();
      Extension = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)Extension;
}

```

## disassembly

```asm
0x18001b7f8  mov     [rsp-8+arg_18], rbx
0x18001b7fd  push    rbp
0x18001b7fe  push    rsi
0x18001b7ff  push    rdi
0x18001b800  push    r14
0x18001b802  push    r15
0x18001b804  lea     rbp, [rsp-570h]
0x18001b80c  sub     rsp, 670h
0x18001b813  mov     rax, cs:__security_cookie
0x18001b81a  xor     rax, rsp
0x18001b81d  mov     [rbp+590h+var_30], rax
0x18001b824  mov     rsi, r8
0x18001b827  mov     [rsp+690h+ppszExt], 0
0x18001b830  mov     rdi, rdx
0x18001b833  lea     r8, [rsp+690h+ppszExt]; ppszExt
0x18001b838  mov     r15d, 104h
0x18001b83e  mov     r14, rcx
0x18001b841  mov     edx, r15d; cchPath
0x18001b844  call    cs:__imp_PathCchFindExtension
0x18001b84a  mov     ebx, eax
0x18001b84c  test    eax, eax
0x18001b84e  js      loc_18001B94A
0x18001b854  mov     rcx, [rsp+690h+ppszExt]
0x18001b859  lea     rdx, aUrl; ".url"
0x18001b860  call    cs:__imp__o__wcsicmp
0x18001b866  test    eax, eax
0x18001b868  jnz     loc_18001B94A
0x18001b86e  lea     r9, [rbp+590h+TempFileName]; lpTempFileName
0x18001b875  xor     r8d, r8d; uUnique
0x18001b878  mov     rdx, rsi; lpPrefixString
0x18001b87b  mov     rcx, rdi; lpPathName
0x18001b87e  call    cs:__imp_GetTempFileNameW
0x18001b884  test    eax, eax
0x18001b886  jz      loc_18001B935
0x18001b88c  lea     r9, [rbp+590h+TempFileName]; pszMore
0x18001b893  mov     r8, rdi; pszPathIn
0x18001b896  mov     edx, r15d; cchPathOut
0x18001b899  lea     rcx, [rsp+690h+pszPathOut]; pszPathOut
0x18001b89e  call    cs:__imp_PathCchCombine
0x18001b8a4  mov     ebx, eax
0x18001b8a6  test    eax, eax
0x18001b8a8  js      loc_18001B94A
0x18001b8ae  mov     r8, rsi; unsigned __int16 *
0x18001b8b1  lea     rcx, [rbp+590h+pszPath]; unsigned __int16 *
0x18001b8b8  mov     edx, r15d; unsigned __int64
0x18001b8bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b8c0  mov     edx, r15d; cchPath
0x18001b8c3  lea     rcx, [rbp+590h+pszPath]; pszPath
0x18001b8ca  call    cs:__imp_PathCchRemoveExtension
0x18001b8d0  lea     rdx, [rbp+590h+pszPath]; unsigned __int16 *
0x18001b8d7  lea     rcx, [rsp+690h+pszPathOut]; unsigned __int16 *
0x18001b8dc  call    ?WriteStringToFile@@YAJPEBG0@Z; WriteStringToFile(ushort const *,ushort const *)
0x18001b8e1  lea     rcx, [rsp+690h+pszPathOut]; lpFileName
0x18001b8e6  mov     ebx, eax
0x18001b8e8  test    eax, eax
0x18001b8ea  js      loc_18001B972
0x18001b8f0  lea     r8, pszExt; "url"
0x18001b8f7  mov     edx, r15d; cchPath
0x18001b8fa  call    cs:__imp_PathCchRenameExtension
0x18001b900  xor     r8d, r8d; bFailIfExists
0x18001b903  lea     rdx, [rsp+690h+pszPathOut]; lpNewFileName
0x18001b908  mov     rcx, r14; lpExistingFileName
0x18001b90b  call    cs:__imp_CopyFileW
0x18001b911  test    eax, eax
0x18001b913  jnz     short loc_18001B94A
0x18001b915  lea     r8, aTmp; "tmp"
0x18001b91c  mov     edx, r15d; cchPath
0x18001b91f  lea     rcx, [rsp+690h+pszPathOut]; pszPath
0x18001b924  call    cs:__imp_PathCchRenameExtension
0x18001b92a  lea     rcx, [rsp+690h+pszPathOut]; lpFileName
0x18001b92f  call    cs:__imp_DeleteFileW
0x18001b935  call    cs:__imp_GetLastError
0x18001b93b  mov     ebx, eax
0x18001b93d  test    eax, eax
0x18001b93f  jle     short loc_18001B94A
0x18001b941  movzx   ebx, ax
0x18001b944  or      ebx, 80070000h
0x18001b94a  mov     eax, ebx
0x18001b94c  mov     rcx, [rbp+590h+var_30]
0x18001b953  xor     rcx, rsp; StackCookie
0x18001b956  call    __security_check_cookie
0x18001b95b  mov     rbx, [rsp+690h+arg_18]
0x18001b963  add     rsp, 670h
0x18001b96a  pop     r15
0x18001b96c  pop     r14
0x18001b96e  pop     rdi
0x18001b96f  pop     rsi
0x18001b970  pop     rbp
0x18001b971  retn
0x18001b972  call    cs:__imp_DeleteFileW
0x18001b978  jmp     short loc_18001B94A
```
