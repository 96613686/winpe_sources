# PpdLoadCachedBinaryData

- ea: `0x1801ae478`
- end: `0x1801ae7cf`
- name: `PpdLoadCachedBinaryData`
- size: `855`
- prototype: `HLOCAL __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x1801add54`

## callees

- `0x180003400`
- `0x180004414`
- `0x180004558`
- `0x1801501fc`
- `0x180150854`
- `0x1801ace00`
- `0x1801ad39c`
- `0x1801ae478`
- `0x1801b56bc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae605`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae61e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae63c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae605`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae61e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ae63c`
- `KERNEL32!CreateFileMappingW` at `0x1801ae555`
- `KERNEL32!CreateFileMappingW` at `0x1801ae555`
- `KERNEL32!MapViewOfFile` at `0x1801ae582`
- `KERNEL32!MapViewOfFile` at `0x1801ae582`
- `KERNEL32!GetFileSize` at `0x1801ae528`
- `KERNEL32!GetFileSize` at `0x1801ae528`
- `KERNEL32!CreateFileW` at `0x1801ae50a`
- `KERNEL32!CreateFileW` at `0x1801ae50a`
- `KERNEL32!CloseHandle` at `0x1801ae594`
- `KERNEL32!CloseHandle` at `0x1801ae78d`
- `KERNEL32!CloseHandle` at `0x1801ae594`
- `KERNEL32!CloseHandle` at `0x1801ae78d`
- `KERNEL32!SetLastError` at `0x1801ae73b`
- `KERNEL32!SetLastError` at `0x1801ae73b`
- `KERNEL32!LocalFree` at `0x1801ae755`
- `KERNEL32!LocalFree` at `0x1801ae76e`
- `KERNEL32!LocalFree` at `0x1801ae79c`
- `KERNEL32!LocalFree` at `0x1801ae755`
- `KERNEL32!LocalFree` at `0x1801ae76e`
- `KERNEL32!LocalFree` at `0x1801ae79c`
- `KERNEL32!LocalAlloc` at `0x1801ae712`
- `KERNEL32!LocalAlloc` at `0x1801ae712`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801ae5bc`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801ae5bc`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801ae6f6`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801ae6f6`

## pseudocode

```c
HLOCAL __fastcall PpdLoadCachedBinaryData(STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *FilenameWithExtName; // rax
  _DWORD *v3; // rbp
  wchar_t *v4; // r15
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
  FilenameWithExtName = GenerateFilenameWithExtName(pszSrc);
  v3 = 0;
  v4 = FilenameWithExtName;
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
      v14 = ConvertFullPathToLongUNC(v4);
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
        || !(unsigned int)BIsRawBinaryDataUpToDate((__int64)v12) )
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
0x1801ae478  push    rbx
0x1801ae47a  push    rbp
0x1801ae47b  push    rsi
0x1801ae47c  push    rdi
0x1801ae47d  push    r12
0x1801ae47f  push    r13
0x1801ae481  push    r14
0x1801ae483  push    r15
0x1801ae485  sub     rsp, 478h
0x1801ae48c  mov     rax, cs:__security_cookie
0x1801ae493  xor     rax, rsp
0x1801ae496  mov     [rsp+4B8h+var_58], rax
0x1801ae49e  mov     rbx, rcx
0x1801ae4a1  xor     edx, edx; Val
0x1801ae4a3  lea     rcx, [rsp+4B8h+szFilePath]; void *
0x1801ae4a8  mov     r8d, 410h; Size
0x1801ae4ae  call    memset_0
0x1801ae4b3  movsd   xmm0, qword ptr cs:asc_180229F28; "\\\\?\\"
0x1801ae4bb  mov     rcx, rbx; pszSrc
0x1801ae4be  movzx   eax, word ptr cs:asc_180229F28+8; ""
0x1801ae4c5  movsd   qword ptr [rsp+4B8h+String2], xmm0
0x1801ae4cb  mov     [rsp+4B8h+var_470], ax
0x1801ae4d0  call    GenerateFilenameWithExtName
0x1801ae4d5  xor     ebp, ebp
0x1801ae4d7  mov     r15, rax
0x1801ae4da  test    rax, rax
0x1801ae4dd  jz      loc_1801AE7A8
0x1801ae4e3  mov     [rsp+4B8h+hTemplateFile], rbp; hTemplateFile
0x1801ae4e8  lea     r12d, [rbp+1]
0x1801ae4ec  mov     r8d, r12d; dwShareMode
0x1801ae4ef  mov     [rsp+4B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1801ae4f7  xor     r9d, r9d; lpSecurityAttributes
0x1801ae4fa  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1801ae502  mov     edx, 80000000h; dwDesiredAccess
0x1801ae507  mov     rcx, rax; lpFileName
0x1801ae50a  call    cs:__imp_CreateFileW
0x1801ae511  nop     dword ptr [rax+rax+00h]
0x1801ae516  mov     rsi, rax
0x1801ae519  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ae51d  jz      loc_1801AE799
0x1801ae523  xor     edx, edx; lpFileSizeHigh
0x1801ae525  mov     rcx, rax; hFile
0x1801ae528  call    cs:__imp_GetFileSize
0x1801ae52f  nop     dword ptr [rax+rax+00h]
0x1801ae534  mov     r13d, eax
0x1801ae537  cmp     eax, 0FFFFFFFFh
0x1801ae53a  jz      loc_1801AE78A
0x1801ae540  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbp; lpName
0x1801ae545  lea     r8d, [rbp+2]; flProtect
0x1801ae549  xor     r9d, r9d; dwMaximumSizeHigh
0x1801ae54c  mov     [rsp+4B8h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x1801ae550  xor     edx, edx; lpFileMappingAttributes
0x1801ae552  mov     rcx, rsi; hFile
0x1801ae555  call    cs:__imp_CreateFileMappingW
0x1801ae55c  nop     dword ptr [rax+rax+00h]
0x1801ae561  mov     rbx, rax
0x1801ae564  test    rax, rax
0x1801ae567  jz      loc_1801AE78A
0x1801ae56d  lea     r14d, [rbp+4]
0x1801ae571  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x1801ae576  mov     edx, r14d; dwDesiredAccess
0x1801ae579  xor     r9d, r9d; dwFileOffsetLow
0x1801ae57c  xor     r8d, r8d; dwFileOffsetHigh
0x1801ae57f  mov     rcx, rax; hFileMappingObject
0x1801ae582  call    cs:__imp_MapViewOfFile
0x1801ae589  nop     dword ptr [rax+rax+00h]
0x1801ae58e  mov     rcx, rbx; hObject
0x1801ae591  mov     rdi, rax
0x1801ae594  call    cs:__imp_CloseHandle
0x1801ae59b  nop     dword ptr [rax+rax+00h]
0x1801ae5a0  test    rdi, rdi
0x1801ae5a3  jz      loc_1801AE78A
0x1801ae5a9  mov     ebx, 208h
0x1801ae5ae  lea     rdx, [rsp+4B8h+szFilePath]; lpszFilePath
0x1801ae5b3  mov     r8d, ebx; cchFilePath
0x1801ae5b6  xor     r9d, r9d; dwFlags
0x1801ae5b9  mov     rcx, rsi; hFile
0x1801ae5bc  call    cs:__imp_GetFinalPathNameByHandleW
0x1801ae5c3  nop     dword ptr [rax+rax+00h]
0x1801ae5c8  test    eax, eax
0x1801ae5ca  jz      loc_1801AE749
0x1801ae5d0  cmp     eax, ebx
0x1801ae5d2  ja      loc_1801AE749
0x1801ae5d8  mov     r8d, r14d; MaxCount
0x1801ae5db  lea     rdx, [rsp+4B8h+String2]; String2
0x1801ae5e0  mov     rcx, r15; String1
0x1801ae5e3  call    _wcsnicmp
0x1801ae5e8  test    eax, eax
0x1801ae5ea  jz      short loc_1801AE5F9
0x1801ae5ec  mov     rcx, r15
0x1801ae5ef  call    ConvertFullPathToLongUNC
0x1801ae5f4  mov     r14, rax
0x1801ae5f7  jmp     short loc_1801AE5FF
0x1801ae5f9  mov     r14, r15
0x1801ae5fc  mov     r12d, ebp
0x1801ae5ff  mov     rdx, rbx; MaxCount
0x1801ae602  mov     rcx, r14; Source
0x1801ae605  call    cs:__imp_wcsnlen
0x1801ae60c  nop     dword ptr [rax+rax+00h]
0x1801ae611  mov     edx, 208h; MaxCount
0x1801ae616  lea     rcx, [rsp+4B8h+szFilePath]; Source
0x1801ae61b  mov     rbx, rax
0x1801ae61e  call    cs:__imp_wcsnlen
0x1801ae625  nop     dword ptr [rax+rax+00h]
0x1801ae62a  mov     edx, 208h; MaxCount
0x1801ae62f  lea     rcx, [rsp+4B8h+szFilePath]
0x1801ae634  cmp     rax, rbx
0x1801ae637  jb      short loc_1801AE63C
0x1801ae639  mov     rcx, r14; Source
0x1801ae63c  call    cs:__imp_wcsnlen
0x1801ae643  nop     dword ptr [rax+rax+00h]
0x1801ae648  mov     rdx, r14; String2
0x1801ae64b  lea     rcx, [rsp+4B8h+szFilePath]; String1
0x1801ae650  mov     r8, rax; MaxCount
0x1801ae653  call    _wcsnicmp
0x1801ae658  mov     rbx, rbp
0x1801ae65b  test    eax, eax
0x1801ae65d  jnz     loc_1801AE752
0x1801ae663  cmp     r13d, 274h
0x1801ae66a  jbe     loc_1801AE736
0x1801ae670  cmp     r13d, [rdi]
0x1801ae673  jb      loc_1801AE736
0x1801ae679  cmp     dword ptr [rdi+8], 1A001Eh
0x1801ae680  jnz     loc_1801AE736
0x1801ae686  cmp     dword ptr [rdi+4], 50504420h
0x1801ae68d  jnz     loc_1801AE736
0x1801ae693  mov     rcx, rdi
0x1801ae696  call    BIsRawBinaryDataUpToDate
0x1801ae69b  test    eax, eax
0x1801ae69d  jz      loc_1801AE736
0x1801ae6a3  cmp     [rdi+38h], ebp
0x1801ae6a6  jz      short loc_1801AE6B0
0x1801ae6a8  mov     ecx, [rdi+38h]
0x1801ae6ab  add     rcx, rdi
0x1801ae6ae  jmp     short loc_1801AE6B3
0x1801ae6b0  mov     rcx, rbp
0x1801ae6b3  cmp     [rdi+3Ch], ebp
0x1801ae6b6  jz      short loc_1801AE6BE
0x1801ae6b8  mov     ebp, [rdi+3Ch]
0x1801ae6bb  add     rbp, rdi
0x1801ae6be  test    rcx, rcx
0x1801ae6c1  jz      short loc_1801AE736
0x1801ae6c3  test    rbp, rbp
0x1801ae6c6  jz      short loc_1801AE736
0x1801ae6c8  mov     edx, [rdi]
0x1801ae6ca  lea     rax, [rcx+150h]
0x1801ae6d1  add     rdx, rdi
0x1801ae6d4  cmp     rax, rdx
0x1801ae6d7  ja      short loc_1801AE736
0x1801ae6d9  lea     rax, [rbp+0E4h]
0x1801ae6e0  cmp     rax, rdx
0x1801ae6e3  ja      short loc_1801AE736
0x1801ae6e5  cmp     dword ptr [rcx], 150h
0x1801ae6eb  jnz     short loc_1801AE736
0x1801ae6ed  cmp     dword ptr [rbp+0], 0E4h
0x1801ae6f4  jnz     short loc_1801AE736
0x1801ae6f6  call    cs:__imp_GetUserDefaultUILanguage
0x1801ae6fd  nop     dword ptr [rax+rax+00h]
0x1801ae702  movzx   eax, ax
0x1801ae705  cmp     [rbp+0DCh], eax
0x1801ae70b  jnz     short loc_1801AE736
0x1801ae70d  mov     rdx, r13; uBytes
0x1801ae710  xor     ecx, ecx; uFlags
0x1801ae712  call    cs:__imp_LocalAlloc
0x1801ae719  nop     dword ptr [rax+rax+00h]
0x1801ae71e  mov     rbx, rax
0x1801ae721  test    rax, rax
0x1801ae724  jz      short loc_1801AE736
0x1801ae726  mov     r8, r13; Size
0x1801ae729  mov     rdx, rdi; Src
0x1801ae72c  mov     rcx, rax; void *
0x1801ae72f  call    memcpy_0
0x1801ae734  jmp     short loc_1801AE752
0x1801ae736  mov     ecx, 0Dh; dwErrCode
0x1801ae73b  call    cs:__imp_SetLastError
0x1801ae742  nop     dword ptr [rax+rax+00h]
0x1801ae747  jmp     short loc_1801AE752
0x1801ae749  mov     r14, rbp
0x1801ae74c  mov     r12d, ebp
0x1801ae74f  mov     rbx, rbp
0x1801ae752  mov     rcx, r15; hMem
0x1801ae755  call    cs:__imp_LocalFree
0x1801ae75c  nop     dword ptr [rax+rax+00h]
0x1801ae761  test    r12d, r12d
0x1801ae764  jz      short loc_1801AE77A
0x1801ae766  test    r14, r14
0x1801ae769  jz      short loc_1801AE77A
0x1801ae76b  mov     rcx, r14; hMem
0x1801ae76e  call    cs:__imp_LocalFree
0x1801ae775  nop     dword ptr [rax+rax+00h]
0x1801ae77a  mov     rdx, rsi
0x1801ae77d  mov     rcx, rdi
0x1801ae780  call    UnmapFileFromMemory
0x1801ae785  mov     rax, rbx
0x1801ae788  jmp     short loc_1801AE7AA
0x1801ae78a  mov     rcx, rsi; hObject
0x1801ae78d  call    cs:__imp_CloseHandle
0x1801ae794  nop     dword ptr [rax+rax+00h]
0x1801ae799  mov     rcx, r15; hMem
0x1801ae79c  call    cs:__imp_LocalFree
0x1801ae7a3  nop     dword ptr [rax+rax+00h]
0x1801ae7a8  xor     eax, eax
0x1801ae7aa  mov     rcx, [rsp+4B8h+var_58]
0x1801ae7b2  xor     rcx, rsp; StackCookie
0x1801ae7b5  call    __security_check_cookie
0x1801ae7ba  add     rsp, 478h
0x1801ae7c1  pop     r15
0x1801ae7c3  pop     r14
0x1801ae7c5  pop     r13
0x1801ae7c7  pop     r12
0x1801ae7c9  pop     rdi
0x1801ae7ca  pop     rsi
0x1801ae7cb  pop     rbp
0x1801ae7cc  pop     rbx
0x1801ae7cd  retn
```
