# CopyFiles(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18001b980`
- end: `0x18001ba97`
- name: `?CopyFiles@@YAJPEBG0KPEAPEAG@Z`
- size: `279`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpPathName, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x180008700`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x18001b980`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18001b9d3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18001b9d3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18001ba3d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18001ba3d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001b9be`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001ba4f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001b9be`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001ba4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba59`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b9e9`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b9e9`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18001ba0d`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18001ba0d`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001ba26`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18001ba26`

## pseudocode

```c
__int64 __fastcall CopyFiles(LPCWSTR lpExistingFileName, LPCWSTR lpPathName, __int64 a3, unsigned __int16 **a4)
{
  int Extension; // ebx
  signed int LastError; // eax
  LPWSTR ppwsz; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR ppszExt; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR TempFileName[264]; // [rsp+30h] [rbp-D0h] BYREF

  ppwsz = 0;
  Extension = SHStrDupW(lpExistingFileName, &ppwsz);
  if ( Extension >= 0 )
  {
    PathStripPathW(ppwsz);
    if ( GetTempFileNameW(lpPathName, ppwsz, 0, TempFileName) )
    {
      ppszExt = 0;
      Extension = PathCchFindExtension(lpExistingFileName, 0x104u, &ppszExt);
      if ( Extension < 0 )
        goto LABEL_9;
      Extension = PathCchRenameExtension(TempFileName, 0x104u, ppszExt);
      if ( Extension < 0 )
        goto LABEL_9;
      if ( CopyFileW(lpExistingFileName, TempFileName, 0) )
      {
        Extension = SHStrDupW(TempFileName, a4);
        goto LABEL_9;
      }
    }
    LastError = GetLastError();
    Extension = LastError;
    if ( LastError > 0 )
      Extension = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_9:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppwsz);
  return (unsigned int)Extension;
}

```

## disassembly

```asm
0x18001b980  push    rbp
0x18001b982  push    rbx
0x18001b983  push    rsi
0x18001b984  push    rdi
0x18001b985  push    r14
0x18001b987  lea     rbp, [rsp-150h]
0x18001b98f  sub     rsp, 250h
0x18001b996  mov     rax, cs:__security_cookie
0x18001b99d  xor     rax, rsp
0x18001b9a0  mov     [rbp+170h+var_30], rax
0x18001b9a7  mov     r14, rdx
0x18001b9aa  mov     [rsp+270h+ppwsz], 0
0x18001b9b3  lea     rdx, [rsp+270h+ppwsz]; ppwsz
0x18001b9b8  mov     rsi, r9
0x18001b9bb  mov     rdi, rcx
0x18001b9be  call    cs:__imp_SHStrDupW
0x18001b9c4  mov     ebx, eax
0x18001b9c6  test    eax, eax
0x18001b9c8  js      loc_18001BA6E
0x18001b9ce  mov     rcx, [rsp+270h+ppwsz]; pszPath
0x18001b9d3  call    cs:__imp_PathStripPathW
0x18001b9d9  mov     rdx, [rsp+270h+ppwsz]; lpPrefixString
0x18001b9de  lea     r9, [rsp+270h+TempFileName]; lpTempFileName
0x18001b9e3  xor     r8d, r8d; uUnique
0x18001b9e6  mov     rcx, r14; lpPathName
0x18001b9e9  call    cs:__imp_GetTempFileNameW
0x18001b9ef  test    eax, eax
0x18001b9f1  jz      short loc_18001BA59
0x18001b9f3  mov     r14d, 104h
0x18001b9f9  mov     [rsp+270h+ppszExt], 0
0x18001ba02  mov     edx, r14d; cchPath
0x18001ba05  lea     r8, [rsp+270h+ppszExt]; ppszExt
0x18001ba0a  mov     rcx, rdi; pszPath
0x18001ba0d  call    cs:__imp_PathCchFindExtension
0x18001ba13  mov     ebx, eax
0x18001ba15  test    eax, eax
0x18001ba17  js      short loc_18001BA6E
0x18001ba19  mov     r8, [rsp+270h+ppszExt]; pszExt
0x18001ba1e  lea     rcx, [rsp+270h+TempFileName]; pszPath
0x18001ba23  mov     edx, r14d; cchPath
0x18001ba26  call    cs:__imp_PathCchRenameExtension
0x18001ba2c  mov     ebx, eax
0x18001ba2e  test    eax, eax
0x18001ba30  js      short loc_18001BA6E
0x18001ba32  xor     r8d, r8d; bFailIfExists
0x18001ba35  lea     rdx, [rsp+270h+TempFileName]; lpNewFileName
0x18001ba3a  mov     rcx, rdi; lpExistingFileName
0x18001ba3d  call    cs:__imp_CopyFileW
0x18001ba43  test    eax, eax
0x18001ba45  jz      short loc_18001BA59
0x18001ba47  mov     rdx, rsi; ppwsz
0x18001ba4a  lea     rcx, [rsp+270h+TempFileName]; psz
0x18001ba4f  call    cs:__imp_SHStrDupW
0x18001ba55  mov     ebx, eax
0x18001ba57  jmp     short loc_18001BA6E
0x18001ba59  call    cs:__imp_GetLastError
0x18001ba5f  mov     ebx, eax
0x18001ba61  test    eax, eax
0x18001ba63  jle     short loc_18001BA6E
0x18001ba65  movzx   ebx, ax
0x18001ba68  or      ebx, 80070000h
0x18001ba6e  lea     rcx, [rsp+270h+ppwsz]
0x18001ba73  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ba78  mov     eax, ebx
0x18001ba7a  mov     rcx, [rbp+170h+var_30]
0x18001ba81  xor     rcx, rsp; StackCookie
0x18001ba84  call    __security_check_cookie
0x18001ba89  add     rsp, 250h
0x18001ba90  pop     r14
0x18001ba92  pop     rdi
0x18001ba93  pop     rsi
0x18001ba94  pop     rbx
0x18001ba95  pop     rbp
0x18001ba96  retn
```
