# PpdLoadCachedBinaryData

- ea: `0x1801a6bb0`
- end: `0x1801a6ea6`
- name: `PpdLoadCachedBinaryData`
- size: `758`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x1801a64c8`

## callees

- `0x1800032e0`
- `0x1800042d4`
- `0x180004418`
- `0x1801494dc`
- `0x180149ae8`
- `0x1801a55a0`
- `0x1801a5b38`
- `0x1801a6bb0`
- `0x1801adb4c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d19`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d2c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d44`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d19`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d2c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801a6d44`
- `KERNEL32!CreateFileMappingW` at `0x1801a6c81`
- `KERNEL32!CreateFileMappingW` at `0x1801a6c81`
- `KERNEL32!MapViewOfFile` at `0x1801a6ca8`
- `KERNEL32!MapViewOfFile` at `0x1801a6ca8`
- `KERNEL32!GetFileSize` at `0x1801a6c5a`
- `KERNEL32!GetFileSize` at `0x1801a6c5a`
- `KERNEL32!CreateFileW` at `0x1801a6c42`
- `KERNEL32!CreateFileW` at `0x1801a6c42`
- `KERNEL32!CloseHandle` at `0x1801a6cb4`
- `KERNEL32!CloseHandle` at `0x1801a6e71`
- `KERNEL32!CloseHandle` at `0x1801a6cb4`
- `KERNEL32!CloseHandle` at `0x1801a6e71`
- `KERNEL32!SetLastError` at `0x1801a6e31`
- `KERNEL32!SetLastError` at `0x1801a6e31`
- `KERNEL32!LocalFree` at `0x1801a6e45`
- `KERNEL32!LocalFree` at `0x1801a6e58`
- `KERNEL32!LocalFree` at `0x1801a6e7a`
- `KERNEL32!LocalFree` at `0x1801a6e45`
- `KERNEL32!LocalFree` at `0x1801a6e58`
- `KERNEL32!LocalFree` at `0x1801a6e7a`
- `KERNEL32!LocalAlloc` at `0x1801a6e0e`
- `KERNEL32!LocalAlloc` at `0x1801a6e0e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801a6cd6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801a6cd6`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801a6df8`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801a6df8`

## pseudocode

```c
HLOCAL __fastcall PpdLoadCachedBinaryData(STRSAFE_LPCWSTR pszSrc)
{
  const WCHAR *FilenameWithExtName; // rax
  _DWORD *v3; // rbp
  WCHAR *v4; // r15
  int v5; // r12d
  HANDLE FileW; // rax
  void *v7; // rsi
  DWORD FileSize; // eax
  size_t v9; // r13
  HANDLE FileMappingW; // rax
  void *v11; // rbx
  unsigned int *v12; // rdi
  DWORD FinalPathNameByHandleW; // eax
  wchar_t *v14; // r14
  size_t v15; // rbx
  size_t v16; // rax
  WCHAR *v17; // rcx
  size_t v18; // rax
  HLOCAL v19; // rbx
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rdx
  HLOCAL v22; // rax
  wchar_t String2[8]; // [rsp+40h] [rbp-478h] BYREF
  WCHAR szFilePath[520]; // [rsp+50h] [rbp-468h] BYREF

  memset_0(szFilePath, 0, sizeof(szFilePath));
  wcscpy(String2, L"\\\\?\\");
  FilenameWithExtName = (const WCHAR *)GenerateFilenameWithExtName(pszSrc);
  v3 = 0;
  v4 = (WCHAR *)FilenameWithExtName;
  if ( !FilenameWithExtName )
    return 0;
  v5 = 1;
  FileW = CreateFileW(FilenameWithExtName, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_40:
    LocalFree(v4);
    return 0;
  }
  FileSize = GetFileSize(FileW, 0);
  v9 = FileSize;
  if ( FileSize == -1
    || (FileMappingW = CreateFileMappingW(v7, 0, 2u, 0, 0, 0), (v11 = FileMappingW) == 0)
    || (v12 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v11), !v12) )
  {
    CloseHandle(v7);
    goto LABEL_40;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(v7, szFilePath, 0x208u, 0);
  if ( FinalPathNameByHandleW && FinalPathNameByHandleW <= 0x208 )
  {
    if ( wcsnicmp(v4, String2, 4u) )
    {
      v14 = (wchar_t *)ConvertFullPathToLongUNC(v4);
    }
    else
    {
      v14 = v4;
      v5 = 0;
    }
    v15 = wcsnlen(v14, 0x208u);
    v16 = wcsnlen(szFilePath, 0x208u);
    v17 = szFilePath;
    if ( v16 >= v15 )
      v17 = v14;
    v18 = wcsnlen(v17, 0x208u);
    v19 = 0;
    if ( !wcsnicmp(szFilePath, v14, v18) )
    {
      if ( (unsigned int)v9 <= 0x274
        || (unsigned int)v9 < *v12
        || v12[2] != 1703966
        || v12[1] != 1347437600
        || !(unsigned int)BIsRawBinaryDataUpToDate(v12) )
      {
        goto LABEL_33;
      }
      if ( v12[14] )
        v20 = (unsigned int *)((char *)v12 + v12[14]);
      else
        v20 = 0;
      if ( v12[15] )
        v3 = (unsigned int *)((char *)v12 + v12[15]);
      if ( v20
        && v3
        && (v21 = (unsigned __int64)v12 + *v12, (unsigned __int64)(v20 + 84) <= v21)
        && (unsigned __int64)(v3 + 57) <= v21
        && *v20 == 336
        && *v3 == 228
        && v3[55] == GetUserDefaultUILanguage()
        && (v22 = LocalAlloc(0, v9), (v19 = v22) != 0) )
      {
        memcpy_0(v22, v12, v9);
      }
      else
      {
LABEL_33:
        SetLastError(0xDu);
      }
    }
  }
  else
  {
    v14 = 0;
    v5 = 0;
    v19 = 0;
  }
  LocalFree(v4);
  if ( v5 )
  {
    if ( v14 )
      LocalFree(v14);
  }
  UnmapFileFromMemory(v12, v7);
  return v19;
}

```

## disassembly

```asm
0x1801a6bb0  push    rbx
0x1801a6bb2  push    rbp
0x1801a6bb3  push    rsi
0x1801a6bb4  push    rdi
0x1801a6bb5  push    r12
0x1801a6bb7  push    r13
0x1801a6bb9  push    r14
0x1801a6bbb  push    r15
0x1801a6bbd  sub     rsp, 478h
0x1801a6bc4  mov     rax, cs:__security_cookie
0x1801a6bcb  xor     rax, rsp
0x1801a6bce  mov     [rsp+4B8h+var_58], rax
0x1801a6bd6  mov     rbx, rcx
0x1801a6bd9  xor     edx, edx; Val
0x1801a6bdb  lea     rcx, [rsp+4B8h+szFilePath]; void *
0x1801a6be0  mov     r8d, 410h; Size
0x1801a6be6  call    memset_0
0x1801a6beb  movsd   xmm0, qword ptr cs:asc_180222260; "\\\\?\\"
0x1801a6bf3  mov     rcx, rbx; pszSrc
0x1801a6bf6  movzx   eax, word ptr cs:asc_180222260+8; ""
0x1801a6bfd  movsd   qword ptr [rsp+4B8h+String2], xmm0
0x1801a6c03  mov     [rsp+4B8h+var_470], ax
0x1801a6c08  call    GenerateFilenameWithExtName
0x1801a6c0d  xor     ebp, ebp
0x1801a6c0f  mov     r15, rax
0x1801a6c12  test    rax, rax
0x1801a6c15  jz      loc_1801A6E80
0x1801a6c1b  mov     [rsp+4B8h+hTemplateFile], rbp; hTemplateFile
0x1801a6c20  lea     r12d, [rbp+1]
0x1801a6c24  mov     r8d, r12d; dwShareMode
0x1801a6c27  mov     [rsp+4B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1801a6c2f  xor     r9d, r9d; lpSecurityAttributes
0x1801a6c32  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1801a6c3a  mov     edx, 80000000h; dwDesiredAccess
0x1801a6c3f  mov     rcx, rax; lpFileName
0x1801a6c42  call    cs:__imp_CreateFileW
0x1801a6c48  mov     rsi, rax
0x1801a6c4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a6c4f  jz      loc_1801A6E77
0x1801a6c55  xor     edx, edx; lpFileSizeHigh
0x1801a6c57  mov     rcx, rax; hFile
0x1801a6c5a  call    cs:__imp_GetFileSize
0x1801a6c60  mov     r13d, eax
0x1801a6c63  cmp     eax, 0FFFFFFFFh
0x1801a6c66  jz      loc_1801A6E6E
0x1801a6c6c  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbp; lpName
0x1801a6c71  lea     r8d, [rbp+2]; flProtect
0x1801a6c75  xor     r9d, r9d; dwMaximumSizeHigh
0x1801a6c78  mov     [rsp+4B8h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x1801a6c7c  xor     edx, edx; lpFileMappingAttributes
0x1801a6c7e  mov     rcx, rsi; hFile
0x1801a6c81  call    cs:__imp_CreateFileMappingW
0x1801a6c87  mov     rbx, rax
0x1801a6c8a  test    rax, rax
0x1801a6c8d  jz      loc_1801A6E6E
0x1801a6c93  lea     r14d, [rbp+4]
0x1801a6c97  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x1801a6c9c  mov     edx, r14d; dwDesiredAccess
0x1801a6c9f  xor     r9d, r9d; dwFileOffsetLow
0x1801a6ca2  xor     r8d, r8d; dwFileOffsetHigh
0x1801a6ca5  mov     rcx, rax; hFileMappingObject
0x1801a6ca8  call    cs:__imp_MapViewOfFile
0x1801a6cae  mov     rcx, rbx; hObject
0x1801a6cb1  mov     rdi, rax
0x1801a6cb4  call    cs:__imp_CloseHandle
0x1801a6cba  test    rdi, rdi
0x1801a6cbd  jz      loc_1801A6E6E
0x1801a6cc3  mov     ebx, 208h
0x1801a6cc8  lea     rdx, [rsp+4B8h+szFilePath]; lpszFilePath
0x1801a6ccd  mov     r8d, ebx; cchFilePath
0x1801a6cd0  xor     r9d, r9d; dwFlags
0x1801a6cd3  mov     rcx, rsi; hFile
0x1801a6cd6  call    cs:__imp_GetFinalPathNameByHandleW
0x1801a6cdc  test    eax, eax
0x1801a6cde  jz      loc_1801A6E39
0x1801a6ce4  cmp     eax, ebx
0x1801a6ce6  ja      loc_1801A6E39
0x1801a6cec  mov     r8d, r14d; MaxCount
0x1801a6cef  lea     rdx, [rsp+4B8h+String2]; String2
0x1801a6cf4  mov     rcx, r15; String1
0x1801a6cf7  call    _wcsnicmp
0x1801a6cfc  test    eax, eax
0x1801a6cfe  jz      short loc_1801A6D0D
0x1801a6d00  mov     rcx, r15
0x1801a6d03  call    ConvertFullPathToLongUNC
0x1801a6d08  mov     r14, rax
0x1801a6d0b  jmp     short loc_1801A6D13
0x1801a6d0d  mov     r14, r15
0x1801a6d10  mov     r12d, ebp
0x1801a6d13  mov     rdx, rbx; MaxCount
0x1801a6d16  mov     rcx, r14; Source
0x1801a6d19  call    cs:__imp_wcsnlen
0x1801a6d1f  mov     edx, 208h; MaxCount
0x1801a6d24  lea     rcx, [rsp+4B8h+szFilePath]; Source
0x1801a6d29  mov     rbx, rax
0x1801a6d2c  call    cs:__imp_wcsnlen
0x1801a6d32  mov     edx, 208h; MaxCount
0x1801a6d37  lea     rcx, [rsp+4B8h+szFilePath]
0x1801a6d3c  cmp     rax, rbx
0x1801a6d3f  jb      short loc_1801A6D44
0x1801a6d41  mov     rcx, r14; Source
0x1801a6d44  call    cs:__imp_wcsnlen
0x1801a6d4a  mov     rdx, r14; String2
0x1801a6d4d  lea     rcx, [rsp+4B8h+szFilePath]; String1
0x1801a6d52  mov     r8, rax; MaxCount
0x1801a6d55  call    _wcsnicmp
0x1801a6d5a  mov     rbx, rbp
0x1801a6d5d  test    eax, eax
0x1801a6d5f  jnz     loc_1801A6E42
0x1801a6d65  cmp     r13d, 274h
0x1801a6d6c  jbe     loc_1801A6E2C
0x1801a6d72  cmp     r13d, [rdi]
0x1801a6d75  jb      loc_1801A6E2C
0x1801a6d7b  cmp     dword ptr [rdi+8], 1A001Eh
0x1801a6d82  jnz     loc_1801A6E2C
0x1801a6d88  cmp     dword ptr [rdi+4], 50504420h
0x1801a6d8f  jnz     loc_1801A6E2C
0x1801a6d95  mov     rcx, rdi
0x1801a6d98  call    BIsRawBinaryDataUpToDate
0x1801a6d9d  test    eax, eax
0x1801a6d9f  jz      loc_1801A6E2C
0x1801a6da5  cmp     [rdi+38h], ebp
0x1801a6da8  jz      short loc_1801A6DB2
0x1801a6daa  mov     ecx, [rdi+38h]
0x1801a6dad  add     rcx, rdi
0x1801a6db0  jmp     short loc_1801A6DB5
0x1801a6db2  mov     rcx, rbp
0x1801a6db5  cmp     [rdi+3Ch], ebp
0x1801a6db8  jz      short loc_1801A6DC0
0x1801a6dba  mov     ebp, [rdi+3Ch]
0x1801a6dbd  add     rbp, rdi
0x1801a6dc0  test    rcx, rcx
0x1801a6dc3  jz      short loc_1801A6E2C
0x1801a6dc5  test    rbp, rbp
0x1801a6dc8  jz      short loc_1801A6E2C
0x1801a6dca  mov     edx, [rdi]
0x1801a6dcc  lea     rax, [rcx+150h]
0x1801a6dd3  add     rdx, rdi
0x1801a6dd6  cmp     rax, rdx
0x1801a6dd9  ja      short loc_1801A6E2C
0x1801a6ddb  lea     rax, [rbp+0E4h]
0x1801a6de2  cmp     rax, rdx
0x1801a6de5  ja      short loc_1801A6E2C
0x1801a6de7  cmp     dword ptr [rcx], 150h
0x1801a6ded  jnz     short loc_1801A6E2C
0x1801a6def  cmp     dword ptr [rbp+0], 0E4h
0x1801a6df6  jnz     short loc_1801A6E2C
0x1801a6df8  call    cs:__imp_GetUserDefaultUILanguage
0x1801a6dfe  movzx   eax, ax
0x1801a6e01  cmp     [rbp+0DCh], eax
0x1801a6e07  jnz     short loc_1801A6E2C
0x1801a6e09  mov     rdx, r13; uBytes
0x1801a6e0c  xor     ecx, ecx; uFlags
0x1801a6e0e  call    cs:__imp_LocalAlloc
0x1801a6e14  mov     rbx, rax
0x1801a6e17  test    rax, rax
0x1801a6e1a  jz      short loc_1801A6E2C
0x1801a6e1c  mov     r8, r13; Size
0x1801a6e1f  mov     rdx, rdi; Src
0x1801a6e22  mov     rcx, rax; void *
0x1801a6e25  call    memcpy_0
0x1801a6e2a  jmp     short loc_1801A6E42
0x1801a6e2c  mov     ecx, 0Dh; dwErrCode
0x1801a6e31  call    cs:__imp_SetLastError
0x1801a6e37  jmp     short loc_1801A6E42
0x1801a6e39  mov     r14, rbp
0x1801a6e3c  mov     r12d, ebp
0x1801a6e3f  mov     rbx, rbp
0x1801a6e42  mov     rcx, r15; hMem
0x1801a6e45  call    cs:__imp_LocalFree
0x1801a6e4b  test    r12d, r12d
0x1801a6e4e  jz      short loc_1801A6E5E
0x1801a6e50  test    r14, r14
0x1801a6e53  jz      short loc_1801A6E5E
0x1801a6e55  mov     rcx, r14; hMem
0x1801a6e58  call    cs:__imp_LocalFree
0x1801a6e5e  mov     rdx, rsi
0x1801a6e61  mov     rcx, rdi
0x1801a6e64  call    UnmapFileFromMemory
0x1801a6e69  mov     rax, rbx
0x1801a6e6c  jmp     short loc_1801A6E82
0x1801a6e6e  mov     rcx, rsi; hObject
0x1801a6e71  call    cs:__imp_CloseHandle
0x1801a6e77  mov     rcx, r15; hMem
0x1801a6e7a  call    cs:__imp_LocalFree
0x1801a6e80  xor     eax, eax
0x1801a6e82  mov     rcx, [rsp+4B8h+var_58]
0x1801a6e8a  xor     rcx, rsp; StackCookie
0x1801a6e8d  call    __security_check_cookie
0x1801a6e92  add     rsp, 478h
0x1801a6e99  pop     r15
0x1801a6e9b  pop     r14
0x1801a6e9d  pop     r13
0x1801a6e9f  pop     r12
0x1801a6ea1  pop     rdi
0x1801a6ea2  pop     rsi
0x1801a6ea3  pop     rbp
0x1801a6ea4  pop     rbx
0x1801a6ea5  retn
```
