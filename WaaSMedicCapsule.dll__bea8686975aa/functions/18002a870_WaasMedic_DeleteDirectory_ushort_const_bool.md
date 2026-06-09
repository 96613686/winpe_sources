# WaasMedic::DeleteDirectory(ushort const *,bool)

- ea: `0x18002a870`
- end: `0x18002aa6e`
- name: `?DeleteDirectory@WaasMedic@@YAJPEBG_N@Z`
- size: `510`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18002a870`
- `0x18002aa74`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x18000a5d0`
- `0x18002543c`
- `0x18002a870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a946`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a960`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a946`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9ff`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a8af`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a9f5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a8af`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a9f5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a9c5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a9c5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002aa30`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002aa30`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a9e4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a9e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a9d6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a9d6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a931`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a931`

## string_xrefs

- `0x18002aa5b`: `Format string print for copying source directory %s failed! hr = 0x%08x`
- `0x18002a8cb`: `Failed to find directory %s..Considering success!`
- `0x18002aa17`: `Failed to remove directory after emptying it's contents! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::DeleteDirectory(WaasMedic *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  DWORD LastError; // eax
  int v5; // eax
  HANDLE FirstFileW; // rsi
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  bool v9; // r8
  signed int v10; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF

  v3 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !RemoveDirectoryW((LPCWSTR)this) )
  {
    LastError = GetLastError();
    if ( LastError == 2 )
    {
      v3 = 1;
      LogLevelW(4u, L"Failed to find directory %s..Considering success!", this);
    }
    else if ( LastError == 145 )
    {
      v5 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", this);
      v3 = v5;
      if ( v5 >= 0 )
      {
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        do
        {
          if ( (unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
            && (unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..") )
          {
            v7 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", this, FindFileData.cFileName);
            v3 = v7;
            if ( v7 < 0 )
            {
              LogLevelW(
                2u,
                L"Format string print for copying source directory %s failed! hr = 0x%08x",
                FindFileData.cFileName,
                (unsigned int)v7);
              goto LABEL_21;
            }
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              LOBYTE(v8) = 1;
              WaasMedic::DeleteDirectory((WaasMedic *)PathName, v8, v9);
              v3 = 0;
            }
            else if ( (FindFileData.dwFileAttributes & 1) == 0 || SetFileAttributesW(PathName, 0x20u) )
            {
              DeleteFileW(PathName);
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( !RemoveDirectoryW((LPCWSTR)this) )
        {
          v10 = GetLastError();
          v3 = v10;
          if ( v10 > 0 )
            v3 = (unsigned __int16)v10 | 0x80070000;
          LogLevelW(4u, L"Failed to remove directory after emptying it's contents! hr = 0x%08x", v3);
        }
LABEL_21:
        if ( FirstFileW )
          FindClose(FirstFileW);
      }
      else
      {
        LogLevelW(2u, L"Format string print for search string failed! hr = 0x%08x", (unsigned int)v5);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002a870  push    rbp
0x18002a872  push    rbx
0x18002a873  push    rsi
0x18002a874  push    rdi
0x18002a875  lea     rbp, [rsp-5B8h]
0x18002a87d  sub     rsp, 6B8h
0x18002a884  mov     rax, cs:__security_cookie
0x18002a88b  xor     rax, rsp
0x18002a88e  mov     [rbp+5D0h+var_30], rax
0x18002a895  mov     rdi, rcx
0x18002a898  xor     edx, edx; Val
0x18002a89a  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x18002a89f  mov     r8d, 250h; Size
0x18002a8a5  xor     ebx, ebx
0x18002a8a7  call    memset_0
0x18002a8ac  mov     rcx, rdi; lpPathName
0x18002a8af  call    cs:__imp_RemoveDirectoryW
0x18002a8b5  test    eax, eax
0x18002a8b7  jnz     loc_18002AA36
0x18002a8bd  call    cs:__imp_GetLastError
0x18002a8c3  cmp     eax, 2
0x18002a8c6  jnz     short loc_18002A8E2
0x18002a8c8  mov     r8, rdi
0x18002a8cb  lea     rdx, aFailedToFindDi; "Failed to find directory %s..Considerin"...
0x18002a8d2  lea     ecx, [rax+2]; unsigned __int8
0x18002a8d5  lea     ebx, [rax-1]
0x18002a8d8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a8dd  jmp     loc_18002AA36
0x18002a8e2  cmp     eax, 91h
0x18002a8e7  jnz     loc_18002AA36
0x18002a8ed  mov     r9, rdi
0x18002a8f0  lea     r8, aS; "%s\\*.*"
0x18002a8f7  lea     edx, [rax+73h]; unsigned __int64
0x18002a8fa  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18002a901  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a906  mov     ebx, eax
0x18002a908  test    eax, eax
0x18002a90a  jns     short loc_18002A925
0x18002a90c  mov     r8d, eax
0x18002a90f  lea     rdx, aFormatStringPr; "Format string print for search string f"...
0x18002a916  mov     ecx, 2; unsigned __int8
0x18002a91b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a920  jmp     loc_18002AA36
0x18002a925  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x18002a92a  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x18002a931  call    cs:__imp_FindFirstFileW
0x18002a937  mov     rsi, rax
0x18002a93a  lea     rdx, asc_18006E874; "."
0x18002a941  lea     rcx, [rsp+6D0h+FindFileData.cFileName]
0x18002a946  call    cs:__imp__o__wcsicmp
0x18002a94c  test    eax, eax
0x18002a94e  jz      loc_18002A9DC
0x18002a954  lea     rdx, asc_18006E2B0; ".."
0x18002a95b  lea     rcx, [rsp+6D0h+FindFileData.cFileName]
0x18002a960  call    cs:__imp__o__wcsicmp
0x18002a966  test    eax, eax
0x18002a968  jz      short loc_18002A9DC
0x18002a96a  lea     rax, [rsp+6D0h+FindFileData.cFileName]
0x18002a96f  mov     r9, rdi
0x18002a972  lea     r8, aSS; "%s\\%s"
0x18002a979  mov     [rsp+6D0h+var_6B0], rax
0x18002a97e  mov     edx, 104h; unsigned __int64
0x18002a983  lea     rcx, [rbp+5D0h+PathName]; unsigned __int16 *
0x18002a98a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a98f  mov     ebx, eax
0x18002a991  test    eax, eax
0x18002a993  js      loc_18002AA53
0x18002a999  test    byte ptr [rsp+6D0h+FindFileData.dwFileAttributes], 10h
0x18002a99e  jz      short loc_18002A9B2
0x18002a9a0  mov     dl, 1; unsigned __int16 *
0x18002a9a2  lea     rcx, [rbp+5D0h+PathName]; this
0x18002a9a9  call    ?DeleteDirectory@WaasMedic@@YAJPEBG_N@Z; WaasMedic::DeleteDirectory(ushort const *,bool)
0x18002a9ae  xor     ebx, ebx
0x18002a9b0  jmp     short loc_18002A9DC
0x18002a9b2  test    byte ptr [rsp+6D0h+FindFileData.dwFileAttributes], 1
0x18002a9b7  jz      short loc_18002A9CF
0x18002a9b9  mov     edx, 20h ; ' '; dwFileAttributes
0x18002a9be  lea     rcx, [rbp+5D0h+PathName]; lpFileName
0x18002a9c5  call    cs:__imp_SetFileAttributesW
0x18002a9cb  test    eax, eax
0x18002a9cd  jz      short loc_18002A9DC
0x18002a9cf  lea     rcx, [rbp+5D0h+PathName]; lpFileName
0x18002a9d6  call    cs:__imp_DeleteFileW
0x18002a9dc  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x18002a9e1  mov     rcx, rsi; hFindFile
0x18002a9e4  call    cs:__imp_FindNextFileW
0x18002a9ea  test    eax, eax
0x18002a9ec  jnz     loc_18002A93A
0x18002a9f2  mov     rcx, rdi; lpPathName
0x18002a9f5  call    cs:__imp_RemoveDirectoryW
0x18002a9fb  test    eax, eax
0x18002a9fd  jnz     short loc_18002AA28
0x18002a9ff  call    cs:__imp_GetLastError
0x18002aa05  mov     ebx, eax
0x18002aa07  test    eax, eax
0x18002aa09  jle     short loc_18002AA14
0x18002aa0b  movzx   ebx, ax
0x18002aa0e  or      ebx, 80070000h
0x18002aa14  mov     r8d, ebx
0x18002aa17  lea     rdx, aFailedToRemove; "Failed to remove directory after emptyi"...
0x18002aa1e  mov     ecx, 4; unsigned __int8
0x18002aa23  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002aa28  test    rsi, rsi
0x18002aa2b  jz      short loc_18002AA36
0x18002aa2d  mov     rcx, rsi; hFindFile
0x18002aa30  call    cs:__imp_FindClose
0x18002aa36  mov     eax, ebx
0x18002aa38  mov     rcx, [rbp+5D0h+var_30]
0x18002aa3f  xor     rcx, rsp; StackCookie
0x18002aa42  call    __security_check_cookie
0x18002aa47  add     rsp, 6B8h
0x18002aa4e  pop     rdi
0x18002aa4f  pop     rsi
0x18002aa50  pop     rbx
0x18002aa51  pop     rbp
0x18002aa52  retn
0x18002aa53  mov     r9d, eax
0x18002aa56  lea     r8, [rsp+6D0h+FindFileData.cFileName]
0x18002aa5b  lea     rdx, aFormatStringPr_1; "Format string print for copying source "...
0x18002aa62  mov     ecx, 2; unsigned __int8
0x18002aa67  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002aa6c  jmp     short loc_18002AA28
```
