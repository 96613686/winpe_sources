# WaasMedic::CopyDirectory(ushort const *,ushort const *)

- ea: `0x18002a600`
- end: `0x18002a868`
- name: `?CopyDirectory@WaasMedic@@YAJPEBG0@Z`
- size: `616`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18002a600`
- `0x18002f0e8`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x18000a5d0`
- `0x18002543c`
- `0x18002a600`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a6eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a705`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a6eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7bf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a839`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a839`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a7ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a7ff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a6d6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a6d6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a64a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a64a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002a7b5`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002a7b5`

## string_xrefs

- `0x18002a673`: `Failed to create directory %s! hr=0x%08x`
- `0x18002a818`: `Format string print for copying source directory %s failed! hr = 0x%08x`
- `0x18002a7a4`: `CopyDirectory for %s to %s failed! hr = 0x%08x`
- `0x18002a80f`: `Format string print for copying destination directory %s failed! hr = 0x%08x`
- `0x18002a7eb`: `CopyFile for %s to %s failed! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CopyDirectory(WaasMedic *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // eax
  HANDLE FirstFileW; // rsi
  int v9; // eax
  int v10; // eax
  const unsigned __int16 *v11; // r8
  int v12; // eax
  signed int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR FileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !CreateDirectoryW(a2, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 183 )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to create directory %s! hr=0x%08x", a2, v6);
      return v6;
    }
  }
  v7 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", this);
  v6 = v7;
  if ( v7 < 0 )
  {
    LogLevelW(2u, L"Format string print for search string failed! hr = 0x%08x", (unsigned int)v7);
    return v6;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  while ( 1 )
  {
    if ( !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
      || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..") )
    {
      goto LABEL_20;
    }
    v9 = StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\%s", this, FindFileData.cFileName);
    v6 = v9;
    if ( v9 < 0 )
      break;
    v10 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
    v6 = v10;
    if ( v10 < 0 )
    {
      LogLevelW(
        2u,
        L"Format string print for copying destination directory %s failed! hr = 0x%08x",
        FindFileData.cFileName,
        (unsigned int)v10);
      goto LABEL_24;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v12 = WaasMedic::CopyDirectory((WaasMedic *)ExistingFileName, PathName, v11);
      v6 = v12;
      if ( v12 < 0 )
      {
        LODWORD(v15) = v12;
        LogLevelW(2u, L"CopyDirectory for %s to %s failed! hr = 0x%08x", ExistingFileName, PathName, v15);
        goto LABEL_24;
      }
    }
    else if ( !CopyFileW(ExistingFileName, PathName, 0) )
    {
      v13 = GetLastError();
      v6 = v13;
      if ( v13 > 0 )
        v6 = (unsigned __int16)v13 | 0x80070000;
      LODWORD(v15) = v6;
      LogLevelW(2u, L"CopyFile for %s to %s failed! hr = 0x%08x", ExistingFileName, PathName, v15);
    }
LABEL_20:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_24;
  }
  LogLevelW(
    2u,
    L"Format string print for copying source directory %s failed! hr = 0x%08x",
    FindFileData.cFileName,
    (unsigned int)v9);
LABEL_24:
  if ( FirstFileW )
    FindClose(FirstFileW);
  return v6;
}

```

## disassembly

```asm
0x18002a600  mov     [rsp-8+arg_10], rbx
0x18002a605  push    rbp
0x18002a606  push    rsi
0x18002a607  push    r12
0x18002a609  push    r14
0x18002a60b  push    r15
0x18002a60d  lea     rbp, [rsp-7C0h]
0x18002a615  sub     rsp, 8C0h
0x18002a61c  mov     rax, cs:__security_cookie
0x18002a623  xor     rax, rsp
0x18002a626  mov     [rbp+7E0h+var_30], rax
0x18002a62d  mov     r14, rdx
0x18002a630  mov     r15, rcx
0x18002a633  xor     edx, edx; Val
0x18002a635  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x18002a63a  mov     r8d, 250h; Size
0x18002a640  call    memset_0
0x18002a645  xor     edx, edx; lpSecurityAttributes
0x18002a647  mov     rcx, r14; lpPathName
0x18002a64a  call    cs:__imp_CreateDirectoryW
0x18002a650  test    eax, eax
0x18002a652  jnz     short loc_18002A68C
0x18002a654  call    cs:__imp_GetLastError
0x18002a65a  mov     ebx, eax
0x18002a65c  cmp     eax, 0B7h
0x18002a661  jz      short loc_18002A68C
0x18002a663  test    eax, eax
0x18002a665  jle     short loc_18002A670
0x18002a667  movzx   ebx, ax
0x18002a66a  or      ebx, 80070000h
0x18002a670  mov     r9d, ebx
0x18002a673  lea     rdx, aFailedToCreate_3; "Failed to create directory %s! hr=0x%08"...
0x18002a67a  mov     r8, r14
0x18002a67d  mov     ecx, 2; unsigned __int8
0x18002a682  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a687  jmp     loc_18002A83F
0x18002a68c  mov     r12d, 104h
0x18002a692  lea     r8, aS; "%s\\*.*"
0x18002a699  mov     edx, r12d; unsigned __int64
0x18002a69c  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x18002a6a3  mov     r9, r15
0x18002a6a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a6ab  mov     ebx, eax
0x18002a6ad  test    eax, eax
0x18002a6af  jns     short loc_18002A6CA
0x18002a6b1  mov     r8d, eax
0x18002a6b4  lea     rdx, aFormatStringPr; "Format string print for search string f"...
0x18002a6bb  mov     ecx, 2; unsigned __int8
0x18002a6c0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a6c5  jmp     loc_18002A83F
0x18002a6ca  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18002a6cf  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x18002a6d6  call    cs:__imp_FindFirstFileW
0x18002a6dc  mov     rsi, rax
0x18002a6df  lea     rdx, asc_18006E874; "."
0x18002a6e6  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x18002a6eb  call    cs:__imp__o__wcsicmp
0x18002a6f1  test    eax, eax
0x18002a6f3  jz      loc_18002A7F7
0x18002a6f9  lea     rdx, asc_18006E2B0; ".."
0x18002a700  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x18002a705  call    cs:__imp__o__wcsicmp
0x18002a70b  test    eax, eax
0x18002a70d  jz      loc_18002A7F7
0x18002a713  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x18002a718  mov     r9, r15
0x18002a71b  lea     r8, aSS; "%s\\%s"
0x18002a722  mov     [rsp+8E0h+var_8C0], rax
0x18002a727  mov     rdx, r12; unsigned __int64
0x18002a72a  lea     rcx, [rbp+7E0h+ExistingFileName]; unsigned __int16 *
0x18002a731  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a736  mov     ebx, eax
0x18002a738  test    eax, eax
0x18002a73a  js      loc_18002A818
0x18002a740  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x18002a745  mov     r9, r14
0x18002a748  lea     r8, aSS; "%s\\%s"
0x18002a74f  mov     [rsp+8E0h+var_8C0], rax
0x18002a754  mov     rdx, r12; unsigned __int64
0x18002a757  lea     rcx, [rbp+7E0h+PathName]; unsigned __int16 *
0x18002a75e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a763  mov     ebx, eax
0x18002a765  test    eax, eax
0x18002a767  js      loc_18002A80F
0x18002a76d  test    byte ptr [rsp+8E0h+FindFileData.dwFileAttributes], 10h
0x18002a772  lea     rdx, [rbp+7E0h+PathName]; unsigned __int16 *
0x18002a779  lea     rcx, [rbp+7E0h+ExistingFileName]; this
0x18002a780  jz      short loc_18002A7B2
0x18002a782  call    ?CopyDirectory@WaasMedic@@YAJPEBG0@Z; WaasMedic::CopyDirectory(ushort const *,ushort const *)
0x18002a787  mov     ebx, eax
0x18002a789  test    eax, eax
0x18002a78b  jns     short loc_18002A7F7
0x18002a78d  lea     r9, [rbp+7E0h+PathName]
0x18002a794  mov     dword ptr [rsp+8E0h+var_8C0], eax
0x18002a798  lea     r8, [rbp+7E0h+ExistingFileName]
0x18002a79f  mov     ecx, 2; unsigned __int8
0x18002a7a4  lea     rdx, aCopydirectoryF; "CopyDirectory for %s to %s failed! hr ="...
0x18002a7ab  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a7b0  jmp     short loc_18002A831
0x18002a7b2  xor     r8d, r8d; bFailIfExists
0x18002a7b5  call    cs:__imp_CopyFileW
0x18002a7bb  test    eax, eax
0x18002a7bd  jnz     short loc_18002A7F7
0x18002a7bf  call    cs:__imp_GetLastError
0x18002a7c5  mov     ebx, eax
0x18002a7c7  test    eax, eax
0x18002a7c9  jle     short loc_18002A7D4
0x18002a7cb  movzx   ebx, ax
0x18002a7ce  or      ebx, 80070000h
0x18002a7d4  lea     r9, [rbp+7E0h+PathName]
0x18002a7db  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x18002a7df  lea     r8, [rbp+7E0h+ExistingFileName]
0x18002a7e6  mov     ecx, 2; unsigned __int8
0x18002a7eb  lea     rdx, aCopyfileForSTo_0; "CopyFile for %s to %s failed! hr = 0x%0"...
0x18002a7f2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a7f7  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18002a7fc  mov     rcx, rsi; hFindFile
0x18002a7ff  call    cs:__imp_FindNextFileW
0x18002a805  test    eax, eax
0x18002a807  jnz     loc_18002A6DF
0x18002a80d  jmp     short loc_18002A831
0x18002a80f  lea     rdx, aFormatStringPr_0; "Format string print for copying destina"...
0x18002a816  jmp     short loc_18002A81F
0x18002a818  lea     rdx, aFormatStringPr_1; "Format string print for copying source "...
0x18002a81f  mov     r9d, eax
0x18002a822  lea     r8, [rsp+8E0h+FindFileData.cFileName]
0x18002a827  mov     ecx, 2; unsigned __int8
0x18002a82c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a831  test    rsi, rsi
0x18002a834  jz      short loc_18002A83F
0x18002a836  mov     rcx, rsi; hFindFile
0x18002a839  call    cs:__imp_FindClose
0x18002a83f  mov     eax, ebx
0x18002a841  mov     rcx, [rbp+7E0h+var_30]
0x18002a848  xor     rcx, rsp; StackCookie
0x18002a84b  call    __security_check_cookie
0x18002a850  mov     rbx, [rsp+8E0h+arg_10]
0x18002a858  add     rsp, 8C0h
0x18002a85f  pop     r15
0x18002a861  pop     r14
0x18002a863  pop     r12
0x18002a865  pop     rsi
0x18002a866  pop     rbp
0x18002a867  retn
```
