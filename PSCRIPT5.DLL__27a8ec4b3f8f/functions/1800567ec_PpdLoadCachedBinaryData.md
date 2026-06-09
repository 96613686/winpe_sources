# PpdLoadCachedBinaryData

- ea: `0x1800567ec`
- end: `0x180056b43`
- name: `PpdLoadCachedBinaryData`
- size: `855`
- prototype: `HLOCAL __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x18005dd18`

## callees

- `0x180001f20`
- `0x1800028a8`
- `0x180002938`
- `0x180030d54`
- `0x180031330`
- `0x180055938`
- `0x180055ed4`
- `0x1800567ec`
- `0x18005e0c4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180056979`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180056992`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800569b0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180056979`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180056992`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800569b0`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180056a6a`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180056a6a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180056930`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180056930`
- `KERNEL32!MapViewOfFile` at `0x1800568f6`
- `KERNEL32!MapViewOfFile` at `0x1800568f6`
- `KERNEL32!CreateFileMappingW` at `0x1800568c9`
- `KERNEL32!CreateFileMappingW` at `0x1800568c9`
- `KERNEL32!GetFileSize` at `0x18005689c`
- `KERNEL32!GetFileSize` at `0x18005689c`
- `KERNEL32!CreateFileW` at `0x18005687e`
- `KERNEL32!CreateFileW` at `0x18005687e`
- `KERNEL32!CloseHandle` at `0x180056908`
- `KERNEL32!CloseHandle` at `0x180056b01`
- `KERNEL32!CloseHandle` at `0x180056908`
- `KERNEL32!CloseHandle` at `0x180056b01`
- `KERNEL32!SetLastError` at `0x180056aaf`
- `KERNEL32!SetLastError` at `0x180056aaf`
- `KERNEL32!LocalFree` at `0x180056ac9`
- `KERNEL32!LocalFree` at `0x180056ae2`
- `KERNEL32!LocalFree` at `0x180056b10`
- `KERNEL32!LocalFree` at `0x180056ac9`
- `KERNEL32!LocalFree` at `0x180056ae2`
- `KERNEL32!LocalFree` at `0x180056b10`
- `KERNEL32!LocalAlloc` at `0x180056a86`
- `KERNEL32!LocalAlloc` at `0x180056a86`

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
0x1800567ec  push    rbx
0x1800567ee  push    rbp
0x1800567ef  push    rsi
0x1800567f0  push    rdi
0x1800567f1  push    r12
0x1800567f3  push    r13
0x1800567f5  push    r14
0x1800567f7  push    r15
0x1800567f9  sub     rsp, 478h
0x180056800  mov     rax, cs:__security_cookie
0x180056807  xor     rax, rsp
0x18005680a  mov     [rsp+4B8h+var_58], rax
0x180056812  mov     rbx, rcx
0x180056815  xor     edx, edx; Val
0x180056817  lea     rcx, [rsp+4B8h+szFilePath]; void *
0x18005681c  mov     r8d, 410h; Size
0x180056822  call    memset_0
0x180056827  movsd   xmm0, qword ptr cs:asc_18006D6D0; "\\\\?\\"
0x18005682f  mov     rcx, rbx; pszSrc
0x180056832  movzx   eax, word ptr cs:asc_18006D6D0+8; ""
0x180056839  movsd   qword ptr [rsp+4B8h+String2], xmm0
0x18005683f  mov     [rsp+4B8h+var_470], ax
0x180056844  call    GenerateFilenameWithExtName
0x180056849  xor     ebp, ebp
0x18005684b  mov     r15, rax
0x18005684e  test    rax, rax
0x180056851  jz      loc_180056B1C
0x180056857  mov     [rsp+4B8h+hTemplateFile], rbp; hTemplateFile
0x18005685c  lea     r12d, [rbp+1]
0x180056860  mov     r8d, r12d; dwShareMode
0x180056863  mov     [rsp+4B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18005686b  xor     r9d, r9d; lpSecurityAttributes
0x18005686e  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180056876  mov     edx, 80000000h; dwDesiredAccess
0x18005687b  mov     rcx, rax; lpFileName
0x18005687e  call    cs:__imp_CreateFileW
0x180056885  nop     dword ptr [rax+rax+00h]
0x18005688a  mov     rsi, rax
0x18005688d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180056891  jz      loc_180056B0D
0x180056897  xor     edx, edx; lpFileSizeHigh
0x180056899  mov     rcx, rax; hFile
0x18005689c  call    cs:__imp_GetFileSize
0x1800568a3  nop     dword ptr [rax+rax+00h]
0x1800568a8  mov     r13d, eax
0x1800568ab  cmp     eax, 0FFFFFFFFh
0x1800568ae  jz      loc_180056AFE
0x1800568b4  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbp; lpName
0x1800568b9  lea     r8d, [rbp+2]; flProtect
0x1800568bd  xor     r9d, r9d; dwMaximumSizeHigh
0x1800568c0  mov     [rsp+4B8h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x1800568c4  xor     edx, edx; lpFileMappingAttributes
0x1800568c6  mov     rcx, rsi; hFile
0x1800568c9  call    cs:__imp_CreateFileMappingW
0x1800568d0  nop     dword ptr [rax+rax+00h]
0x1800568d5  mov     rbx, rax
0x1800568d8  test    rax, rax
0x1800568db  jz      loc_180056AFE
0x1800568e1  lea     r14d, [rbp+4]
0x1800568e5  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x1800568ea  mov     edx, r14d; dwDesiredAccess
0x1800568ed  xor     r9d, r9d; dwFileOffsetLow
0x1800568f0  xor     r8d, r8d; dwFileOffsetHigh
0x1800568f3  mov     rcx, rax; hFileMappingObject
0x1800568f6  call    cs:__imp_MapViewOfFile
0x1800568fd  nop     dword ptr [rax+rax+00h]
0x180056902  mov     rcx, rbx; hObject
0x180056905  mov     rdi, rax
0x180056908  call    cs:__imp_CloseHandle
0x18005690f  nop     dword ptr [rax+rax+00h]
0x180056914  test    rdi, rdi
0x180056917  jz      loc_180056AFE
0x18005691d  mov     ebx, 208h
0x180056922  lea     rdx, [rsp+4B8h+szFilePath]; lpszFilePath
0x180056927  mov     r8d, ebx; cchFilePath
0x18005692a  xor     r9d, r9d; dwFlags
0x18005692d  mov     rcx, rsi; hFile
0x180056930  call    cs:__imp_GetFinalPathNameByHandleW
0x180056937  nop     dword ptr [rax+rax+00h]
0x18005693c  test    eax, eax
0x18005693e  jz      loc_180056ABD
0x180056944  cmp     eax, ebx
0x180056946  ja      loc_180056ABD
0x18005694c  mov     r8d, r14d; MaxCount
0x18005694f  lea     rdx, [rsp+4B8h+String2]; String2
0x180056954  mov     rcx, r15; String1
0x180056957  call    _wcsnicmp
0x18005695c  test    eax, eax
0x18005695e  jz      short loc_18005696D
0x180056960  mov     rcx, r15
0x180056963  call    ConvertFullPathToLongUNC
0x180056968  mov     r14, rax
0x18005696b  jmp     short loc_180056973
0x18005696d  mov     r14, r15
0x180056970  mov     r12d, ebp
0x180056973  mov     rdx, rbx; MaxCount
0x180056976  mov     rcx, r14; Source
0x180056979  call    cs:__imp_wcsnlen
0x180056980  nop     dword ptr [rax+rax+00h]
0x180056985  mov     edx, 208h; MaxCount
0x18005698a  lea     rcx, [rsp+4B8h+szFilePath]; Source
0x18005698f  mov     rbx, rax
0x180056992  call    cs:__imp_wcsnlen
0x180056999  nop     dword ptr [rax+rax+00h]
0x18005699e  mov     edx, 208h; MaxCount
0x1800569a3  lea     rcx, [rsp+4B8h+szFilePath]
0x1800569a8  cmp     rax, rbx
0x1800569ab  jb      short loc_1800569B0
0x1800569ad  mov     rcx, r14; Source
0x1800569b0  call    cs:__imp_wcsnlen
0x1800569b7  nop     dword ptr [rax+rax+00h]
0x1800569bc  mov     rdx, r14; String2
0x1800569bf  lea     rcx, [rsp+4B8h+szFilePath]; String1
0x1800569c4  mov     r8, rax; MaxCount
0x1800569c7  call    _wcsnicmp
0x1800569cc  mov     rbx, rbp
0x1800569cf  test    eax, eax
0x1800569d1  jnz     loc_180056AC6
0x1800569d7  cmp     r13d, 274h
0x1800569de  jbe     loc_180056AAA
0x1800569e4  cmp     r13d, [rdi]
0x1800569e7  jb      loc_180056AAA
0x1800569ed  cmp     dword ptr [rdi+8], 1A001Eh
0x1800569f4  jnz     loc_180056AAA
0x1800569fa  cmp     dword ptr [rdi+4], 50504420h
0x180056a01  jnz     loc_180056AAA
0x180056a07  mov     rcx, rdi
0x180056a0a  call    BIsRawBinaryDataUpToDate
0x180056a0f  test    eax, eax
0x180056a11  jz      loc_180056AAA
0x180056a17  cmp     [rdi+38h], ebp
0x180056a1a  jz      short loc_180056A24
0x180056a1c  mov     ecx, [rdi+38h]
0x180056a1f  add     rcx, rdi
0x180056a22  jmp     short loc_180056A27
0x180056a24  mov     rcx, rbp
0x180056a27  cmp     [rdi+3Ch], ebp
0x180056a2a  jz      short loc_180056A32
0x180056a2c  mov     ebp, [rdi+3Ch]
0x180056a2f  add     rbp, rdi
0x180056a32  test    rcx, rcx
0x180056a35  jz      short loc_180056AAA
0x180056a37  test    rbp, rbp
0x180056a3a  jz      short loc_180056AAA
0x180056a3c  mov     edx, [rdi]
0x180056a3e  lea     rax, [rcx+150h]
0x180056a45  add     rdx, rdi
0x180056a48  cmp     rax, rdx
0x180056a4b  ja      short loc_180056AAA
0x180056a4d  lea     rax, [rbp+0E4h]
0x180056a54  cmp     rax, rdx
0x180056a57  ja      short loc_180056AAA
0x180056a59  cmp     dword ptr [rcx], 150h
0x180056a5f  jnz     short loc_180056AAA
0x180056a61  cmp     dword ptr [rbp+0], 0E4h
0x180056a68  jnz     short loc_180056AAA
0x180056a6a  call    cs:__imp_GetUserDefaultUILanguage
0x180056a71  nop     dword ptr [rax+rax+00h]
0x180056a76  movzx   eax, ax
0x180056a79  cmp     [rbp+0DCh], eax
0x180056a7f  jnz     short loc_180056AAA
0x180056a81  mov     rdx, r13; uBytes
0x180056a84  xor     ecx, ecx; uFlags
0x180056a86  call    cs:__imp_LocalAlloc
0x180056a8d  nop     dword ptr [rax+rax+00h]
0x180056a92  mov     rbx, rax
0x180056a95  test    rax, rax
0x180056a98  jz      short loc_180056AAA
0x180056a9a  mov     r8, r13; Size
0x180056a9d  mov     rdx, rdi; Src
0x180056aa0  mov     rcx, rax; void *
0x180056aa3  call    memcpy_0
0x180056aa8  jmp     short loc_180056AC6
0x180056aaa  mov     ecx, 0Dh; dwErrCode
0x180056aaf  call    cs:__imp_SetLastError
0x180056ab6  nop     dword ptr [rax+rax+00h]
0x180056abb  jmp     short loc_180056AC6
0x180056abd  mov     r14, rbp
0x180056ac0  mov     r12d, ebp
0x180056ac3  mov     rbx, rbp
0x180056ac6  mov     rcx, r15; hMem
0x180056ac9  call    cs:__imp_LocalFree
0x180056ad0  nop     dword ptr [rax+rax+00h]
0x180056ad5  test    r12d, r12d
0x180056ad8  jz      short loc_180056AEE
0x180056ada  test    r14, r14
0x180056add  jz      short loc_180056AEE
0x180056adf  mov     rcx, r14; hMem
0x180056ae2  call    cs:__imp_LocalFree
0x180056ae9  nop     dword ptr [rax+rax+00h]
0x180056aee  mov     rdx, rsi
0x180056af1  mov     rcx, rdi
0x180056af4  call    UnmapFileFromMemory
0x180056af9  mov     rax, rbx
0x180056afc  jmp     short loc_180056B1E
0x180056afe  mov     rcx, rsi; hObject
0x180056b01  call    cs:__imp_CloseHandle
0x180056b08  nop     dword ptr [rax+rax+00h]
0x180056b0d  mov     rcx, r15; hMem
0x180056b10  call    cs:__imp_LocalFree
0x180056b17  nop     dword ptr [rax+rax+00h]
0x180056b1c  xor     eax, eax
0x180056b1e  mov     rcx, [rsp+4B8h+var_58]
0x180056b26  xor     rcx, rsp; StackCookie
0x180056b29  call    __security_check_cookie
0x180056b2e  add     rsp, 478h
0x180056b35  pop     r15
0x180056b37  pop     r14
0x180056b39  pop     r13
0x180056b3b  pop     r12
0x180056b3d  pop     rdi
0x180056b3e  pop     rsi
0x180056b3f  pop     rbp
0x180056b40  pop     rbx
0x180056b41  retn
```
