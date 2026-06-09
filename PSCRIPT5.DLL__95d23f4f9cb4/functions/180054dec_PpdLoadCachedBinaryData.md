# PpdLoadCachedBinaryData

- ea: `0x180054dec`
- end: `0x1800550e9`
- name: `PpdLoadCachedBinaryData`
- size: `765`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18005c098`

## callees

- `0x180001ee0`
- `0x180002848`
- `0x1800028d8`
- `0x18002f82c`
- `0x180053f80`
- `0x180054518`
- `0x180054dec`
- `0x18005c434`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f55`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f68`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f80`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f55`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f68`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054f80`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180055034`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180055034`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180054f12`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180054f12`
- `KERNEL32!MapViewOfFile` at `0x180054ee4`
- `KERNEL32!MapViewOfFile` at `0x180054ee4`
- `KERNEL32!CreateFileMappingW` at `0x180054ebd`
- `KERNEL32!CreateFileMappingW` at `0x180054ebd`
- `KERNEL32!GetFileSize` at `0x180054e96`
- `KERNEL32!GetFileSize` at `0x180054e96`
- `KERNEL32!CreateFileW` at `0x180054e7e`
- `KERNEL32!CreateFileW` at `0x180054e7e`
- `KERNEL32!CloseHandle` at `0x180054ef0`
- `KERNEL32!CloseHandle` at `0x1800550a6`
- `KERNEL32!CloseHandle` at `0x1800550b4`
- `KERNEL32!CloseHandle` at `0x180054ef0`
- `KERNEL32!CloseHandle` at `0x1800550a6`
- `KERNEL32!CloseHandle` at `0x1800550b4`
- `KERNEL32!SetLastError` at `0x18005506d`
- `KERNEL32!SetLastError` at `0x18005506d`
- `KERNEL32!LocalFree` at `0x180055081`
- `KERNEL32!LocalFree` at `0x180055094`
- `KERNEL32!LocalFree` at `0x1800550bd`
- `KERNEL32!LocalFree` at `0x180055081`
- `KERNEL32!LocalFree` at `0x180055094`
- `KERNEL32!LocalFree` at `0x1800550bd`
- `KERNEL32!LocalAlloc` at `0x18005504a`
- `KERNEL32!LocalAlloc` at `0x18005504a`
- `KERNEL32!UnmapViewOfFile` at `0x18005509d`
- `KERNEL32!UnmapViewOfFile` at `0x18005509d`

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
  UnmapViewOfFile(v12);
  CloseHandle(v7);
  return v19;
}

```

## disassembly

```asm
0x180054dec  push    rbx
0x180054dee  push    rbp
0x180054def  push    rsi
0x180054df0  push    rdi
0x180054df1  push    r12
0x180054df3  push    r13
0x180054df5  push    r14
0x180054df7  push    r15
0x180054df9  sub     rsp, 478h
0x180054e00  mov     rax, cs:__security_cookie
0x180054e07  xor     rax, rsp
0x180054e0a  mov     [rsp+4B8h+var_58], rax
0x180054e12  mov     rbx, rcx
0x180054e15  xor     edx, edx; Val
0x180054e17  lea     rcx, [rsp+4B8h+szFilePath]; void *
0x180054e1c  mov     r8d, 410h; Size
0x180054e22  call    memset_0
0x180054e27  movsd   xmm0, qword ptr cs:asc_18006B708; "\\\\?\\"
0x180054e2f  mov     rcx, rbx; pszSrc
0x180054e32  movzx   eax, word ptr cs:asc_18006B708+8; ""
0x180054e39  movsd   qword ptr [rsp+4B8h+String2], xmm0
0x180054e3f  mov     [rsp+4B8h+var_470], ax
0x180054e44  call    GenerateFilenameWithExtName
0x180054e49  xor     ebp, ebp
0x180054e4b  mov     r15, rax
0x180054e4e  test    rax, rax
0x180054e51  jz      loc_1800550C3
0x180054e57  mov     [rsp+4B8h+hTemplateFile], rbp; hTemplateFile
0x180054e5c  lea     r12d, [rbp+1]
0x180054e60  mov     r8d, r12d; dwShareMode
0x180054e63  mov     [rsp+4B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180054e6b  xor     r9d, r9d; lpSecurityAttributes
0x180054e6e  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180054e76  mov     edx, 80000000h; dwDesiredAccess
0x180054e7b  mov     rcx, rax; lpFileName
0x180054e7e  call    cs:__imp_CreateFileW
0x180054e84  mov     rsi, rax
0x180054e87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054e8b  jz      loc_1800550BA
0x180054e91  xor     edx, edx; lpFileSizeHigh
0x180054e93  mov     rcx, rax; hFile
0x180054e96  call    cs:__imp_GetFileSize
0x180054e9c  mov     r13d, eax
0x180054e9f  cmp     eax, 0FFFFFFFFh
0x180054ea2  jz      loc_1800550B1
0x180054ea8  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbp; lpName
0x180054ead  lea     r8d, [rbp+2]; flProtect
0x180054eb1  xor     r9d, r9d; dwMaximumSizeHigh
0x180054eb4  mov     [rsp+4B8h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x180054eb8  xor     edx, edx; lpFileMappingAttributes
0x180054eba  mov     rcx, rsi; hFile
0x180054ebd  call    cs:__imp_CreateFileMappingW
0x180054ec3  mov     rbx, rax
0x180054ec6  test    rax, rax
0x180054ec9  jz      loc_1800550B1
0x180054ecf  lea     r14d, [rbp+4]
0x180054ed3  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x180054ed8  mov     edx, r14d; dwDesiredAccess
0x180054edb  xor     r9d, r9d; dwFileOffsetLow
0x180054ede  xor     r8d, r8d; dwFileOffsetHigh
0x180054ee1  mov     rcx, rax; hFileMappingObject
0x180054ee4  call    cs:__imp_MapViewOfFile
0x180054eea  mov     rcx, rbx; hObject
0x180054eed  mov     rdi, rax
0x180054ef0  call    cs:__imp_CloseHandle
0x180054ef6  test    rdi, rdi
0x180054ef9  jz      loc_1800550B1
0x180054eff  mov     ebx, 208h
0x180054f04  lea     rdx, [rsp+4B8h+szFilePath]; lpszFilePath
0x180054f09  mov     r8d, ebx; cchFilePath
0x180054f0c  xor     r9d, r9d; dwFlags
0x180054f0f  mov     rcx, rsi; hFile
0x180054f12  call    cs:__imp_GetFinalPathNameByHandleW
0x180054f18  test    eax, eax
0x180054f1a  jz      loc_180055075
0x180054f20  cmp     eax, ebx
0x180054f22  ja      loc_180055075
0x180054f28  mov     r8d, r14d; MaxCount
0x180054f2b  lea     rdx, [rsp+4B8h+String2]; String2
0x180054f30  mov     rcx, r15; String1
0x180054f33  call    _wcsnicmp
0x180054f38  test    eax, eax
0x180054f3a  jz      short loc_180054F49
0x180054f3c  mov     rcx, r15
0x180054f3f  call    ConvertFullPathToLongUNC
0x180054f44  mov     r14, rax
0x180054f47  jmp     short loc_180054F4F
0x180054f49  mov     r14, r15
0x180054f4c  mov     r12d, ebp
0x180054f4f  mov     rdx, rbx; MaxCount
0x180054f52  mov     rcx, r14; Source
0x180054f55  call    cs:__imp_wcsnlen
0x180054f5b  mov     edx, 208h; MaxCount
0x180054f60  lea     rcx, [rsp+4B8h+szFilePath]; Source
0x180054f65  mov     rbx, rax
0x180054f68  call    cs:__imp_wcsnlen
0x180054f6e  mov     edx, 208h; MaxCount
0x180054f73  lea     rcx, [rsp+4B8h+szFilePath]
0x180054f78  cmp     rax, rbx
0x180054f7b  jb      short loc_180054F80
0x180054f7d  mov     rcx, r14; Source
0x180054f80  call    cs:__imp_wcsnlen
0x180054f86  mov     rdx, r14; String2
0x180054f89  lea     rcx, [rsp+4B8h+szFilePath]; String1
0x180054f8e  mov     r8, rax; MaxCount
0x180054f91  call    _wcsnicmp
0x180054f96  mov     rbx, rbp
0x180054f99  test    eax, eax
0x180054f9b  jnz     loc_18005507E
0x180054fa1  cmp     r13d, 274h
0x180054fa8  jbe     loc_180055068
0x180054fae  cmp     r13d, [rdi]
0x180054fb1  jb      loc_180055068
0x180054fb7  cmp     dword ptr [rdi+8], 1A001Eh
0x180054fbe  jnz     loc_180055068
0x180054fc4  cmp     dword ptr [rdi+4], 50504420h
0x180054fcb  jnz     loc_180055068
0x180054fd1  mov     rcx, rdi
0x180054fd4  call    BIsRawBinaryDataUpToDate
0x180054fd9  test    eax, eax
0x180054fdb  jz      loc_180055068
0x180054fe1  cmp     [rdi+38h], ebp
0x180054fe4  jz      short loc_180054FEE
0x180054fe6  mov     ecx, [rdi+38h]
0x180054fe9  add     rcx, rdi
0x180054fec  jmp     short loc_180054FF1
0x180054fee  mov     rcx, rbp
0x180054ff1  cmp     [rdi+3Ch], ebp
0x180054ff4  jz      short loc_180054FFC
0x180054ff6  mov     ebp, [rdi+3Ch]
0x180054ff9  add     rbp, rdi
0x180054ffc  test    rcx, rcx
0x180054fff  jz      short loc_180055068
0x180055001  test    rbp, rbp
0x180055004  jz      short loc_180055068
0x180055006  mov     edx, [rdi]
0x180055008  lea     rax, [rcx+150h]
0x18005500f  add     rdx, rdi
0x180055012  cmp     rax, rdx
0x180055015  ja      short loc_180055068
0x180055017  lea     rax, [rbp+0E4h]
0x18005501e  cmp     rax, rdx
0x180055021  ja      short loc_180055068
0x180055023  cmp     dword ptr [rcx], 150h
0x180055029  jnz     short loc_180055068
0x18005502b  cmp     dword ptr [rbp+0], 0E4h
0x180055032  jnz     short loc_180055068
0x180055034  call    cs:__imp_GetUserDefaultUILanguage
0x18005503a  movzx   eax, ax
0x18005503d  cmp     [rbp+0DCh], eax
0x180055043  jnz     short loc_180055068
0x180055045  mov     rdx, r13; uBytes
0x180055048  xor     ecx, ecx; uFlags
0x18005504a  call    cs:__imp_LocalAlloc
0x180055050  mov     rbx, rax
0x180055053  test    rax, rax
0x180055056  jz      short loc_180055068
0x180055058  mov     r8, r13; Size
0x18005505b  mov     rdx, rdi; Src
0x18005505e  mov     rcx, rax; void *
0x180055061  call    memcpy_0
0x180055066  jmp     short loc_18005507E
0x180055068  mov     ecx, 0Dh; dwErrCode
0x18005506d  call    cs:__imp_SetLastError
0x180055073  jmp     short loc_18005507E
0x180055075  mov     r14, rbp
0x180055078  mov     r12d, ebp
0x18005507b  mov     rbx, rbp
0x18005507e  mov     rcx, r15; hMem
0x180055081  call    cs:__imp_LocalFree
0x180055087  test    r12d, r12d
0x18005508a  jz      short loc_18005509A
0x18005508c  test    r14, r14
0x18005508f  jz      short loc_18005509A
0x180055091  mov     rcx, r14; hMem
0x180055094  call    cs:__imp_LocalFree
0x18005509a  mov     rcx, rdi; lpBaseAddress
0x18005509d  call    cs:__imp_UnmapViewOfFile
0x1800550a3  mov     rcx, rsi; hObject
0x1800550a6  call    cs:__imp_CloseHandle
0x1800550ac  mov     rax, rbx
0x1800550af  jmp     short loc_1800550C5
0x1800550b1  mov     rcx, rsi; hObject
0x1800550b4  call    cs:__imp_CloseHandle
0x1800550ba  mov     rcx, r15; hMem
0x1800550bd  call    cs:__imp_LocalFree
0x1800550c3  xor     eax, eax
0x1800550c5  mov     rcx, [rsp+4B8h+var_58]
0x1800550cd  xor     rcx, rsp; StackCookie
0x1800550d0  call    __security_check_cookie
0x1800550d5  add     rsp, 478h
0x1800550dc  pop     r15
0x1800550de  pop     r14
0x1800550e0  pop     r13
0x1800550e2  pop     r12
0x1800550e4  pop     rdi
0x1800550e5  pop     rsi
0x1800550e6  pop     rbp
0x1800550e7  pop     rbx
0x1800550e8  retn
```
