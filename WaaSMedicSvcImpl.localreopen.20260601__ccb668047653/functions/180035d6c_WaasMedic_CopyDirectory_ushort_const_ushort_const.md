# WaasMedic::CopyDirectory(ushort const *,ushort const *)

- ea: `0x180035d6c`
- end: `0x180035fd4`
- name: `?CopyDirectory@WaasMedic@@YAJPEBG0@Z`
- size: `616`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18002b6f4`
- `0x180035d6c`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000c638`
- `0x18002e81c`
- `0x180035d6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f2b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035db6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035db6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035f6b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035f6b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035fa5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035fa5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035e42`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035e42`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180035f21`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180035f21`

## string_xrefs

- `0x180035ddf`: `Failed to create directory %s! hr=0x%08x`
- `0x180035f84`: `Format string print for copying source directory %s failed! hr = 0x%08x`
- `0x180035f57`: `CopyFile for %s to %s failed! hr = 0x%08x`
- `0x180035f7b`: `Format string print for copying destination directory %s failed! hr = 0x%08x`
- `0x180035f10`: `CopyDirectory for %s to %s failed! hr = 0x%08x`

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
0x180035d6c  mov     [rsp-8+arg_10], rbx
0x180035d71  push    rbp
0x180035d72  push    rsi
0x180035d73  push    r12
0x180035d75  push    r14
0x180035d77  push    r15
0x180035d79  lea     rbp, [rsp-7C0h]
0x180035d81  sub     rsp, 8C0h
0x180035d88  mov     rax, cs:__security_cookie
0x180035d8f  xor     rax, rsp
0x180035d92  mov     [rbp+7E0h+var_30], rax
0x180035d99  mov     r14, rdx
0x180035d9c  mov     r15, rcx
0x180035d9f  xor     edx, edx; Val
0x180035da1  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x180035da6  mov     r8d, 250h; Size
0x180035dac  call    memset_0
0x180035db1  xor     edx, edx; lpSecurityAttributes
0x180035db3  mov     rcx, r14; lpPathName
0x180035db6  call    cs:__imp_CreateDirectoryW
0x180035dbc  test    eax, eax
0x180035dbe  jnz     short loc_180035DF8
0x180035dc0  call    cs:__imp_GetLastError
0x180035dc6  mov     ebx, eax
0x180035dc8  cmp     eax, 0B7h
0x180035dcd  jz      short loc_180035DF8
0x180035dcf  test    eax, eax
0x180035dd1  jle     short loc_180035DDC
0x180035dd3  movzx   ebx, ax
0x180035dd6  or      ebx, 80070000h
0x180035ddc  mov     r9d, ebx
0x180035ddf  lea     rdx, aFailedToCreate_2; "Failed to create directory %s! hr=0x%08"...
0x180035de6  mov     r8, r14
0x180035de9  mov     ecx, 2; unsigned __int8
0x180035dee  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035df3  jmp     loc_180035FAB
0x180035df8  mov     r12d, 104h
0x180035dfe  lea     r8, aS; "%s\\*.*"
0x180035e05  mov     edx, r12d; unsigned __int64
0x180035e08  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x180035e0f  mov     r9, r15
0x180035e12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035e17  mov     ebx, eax
0x180035e19  test    eax, eax
0x180035e1b  jns     short loc_180035E36
0x180035e1d  mov     r8d, eax
0x180035e20  lea     rdx, aFormatStringPr; "Format string print for search string f"...
0x180035e27  mov     ecx, 2; unsigned __int8
0x180035e2c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035e31  jmp     loc_180035FAB
0x180035e36  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180035e3b  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x180035e42  call    cs:__imp_FindFirstFileW
0x180035e48  mov     rsi, rax
0x180035e4b  lea     rdx, asc_18008063C; "."
0x180035e52  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x180035e57  call    cs:__imp__o__wcsicmp
0x180035e5d  test    eax, eax
0x180035e5f  jz      loc_180035F63
0x180035e65  lea     rdx, asc_18007E6B0; ".."
0x180035e6c  lea     rcx, [rsp+8E0h+FindFileData.cFileName]
0x180035e71  call    cs:__imp__o__wcsicmp
0x180035e77  test    eax, eax
0x180035e79  jz      loc_180035F63
0x180035e7f  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x180035e84  mov     r9, r15
0x180035e87  lea     r8, aSS; "%s\\%s"
0x180035e8e  mov     [rsp+8E0h+var_8C0], rax
0x180035e93  mov     rdx, r12; unsigned __int64
0x180035e96  lea     rcx, [rbp+7E0h+ExistingFileName]; unsigned __int16 *
0x180035e9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035ea2  mov     ebx, eax
0x180035ea4  test    eax, eax
0x180035ea6  js      loc_180035F84
0x180035eac  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x180035eb1  mov     r9, r14
0x180035eb4  lea     r8, aSS; "%s\\%s"
0x180035ebb  mov     [rsp+8E0h+var_8C0], rax
0x180035ec0  mov     rdx, r12; unsigned __int64
0x180035ec3  lea     rcx, [rbp+7E0h+PathName]; unsigned __int16 *
0x180035eca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035ecf  mov     ebx, eax
0x180035ed1  test    eax, eax
0x180035ed3  js      loc_180035F7B
0x180035ed9  test    byte ptr [rsp+8E0h+FindFileData.dwFileAttributes], 10h
0x180035ede  lea     rdx, [rbp+7E0h+PathName]; unsigned __int16 *
0x180035ee5  lea     rcx, [rbp+7E0h+ExistingFileName]; this
0x180035eec  jz      short loc_180035F1E
0x180035eee  call    ?CopyDirectory@WaasMedic@@YAJPEBG0@Z; WaasMedic::CopyDirectory(ushort const *,ushort const *)
0x180035ef3  mov     ebx, eax
0x180035ef5  test    eax, eax
0x180035ef7  jns     short loc_180035F63
0x180035ef9  lea     r9, [rbp+7E0h+PathName]
0x180035f00  mov     dword ptr [rsp+8E0h+var_8C0], eax
0x180035f04  lea     r8, [rbp+7E0h+ExistingFileName]
0x180035f0b  mov     ecx, 2; unsigned __int8
0x180035f10  lea     rdx, aCopydirectoryF; "CopyDirectory for %s to %s failed! hr ="...
0x180035f17  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035f1c  jmp     short loc_180035F9D
0x180035f1e  xor     r8d, r8d; bFailIfExists
0x180035f21  call    cs:__imp_CopyFileW
0x180035f27  test    eax, eax
0x180035f29  jnz     short loc_180035F63
0x180035f2b  call    cs:__imp_GetLastError
0x180035f31  mov     ebx, eax
0x180035f33  test    eax, eax
0x180035f35  jle     short loc_180035F40
0x180035f37  movzx   ebx, ax
0x180035f3a  or      ebx, 80070000h
0x180035f40  lea     r9, [rbp+7E0h+PathName]
0x180035f47  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x180035f4b  lea     r8, [rbp+7E0h+ExistingFileName]
0x180035f52  mov     ecx, 2; unsigned __int8
0x180035f57  lea     rdx, aCopyfileForSTo; "CopyFile for %s to %s failed! hr = 0x%0"...
0x180035f5e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035f63  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180035f68  mov     rcx, rsi; hFindFile
0x180035f6b  call    cs:__imp_FindNextFileW
0x180035f71  test    eax, eax
0x180035f73  jnz     loc_180035E4B
0x180035f79  jmp     short loc_180035F9D
0x180035f7b  lea     rdx, aFormatStringPr_0; "Format string print for copying destina"...
0x180035f82  jmp     short loc_180035F8B
0x180035f84  lea     rdx, aFormatStringPr_1; "Format string print for copying source "...
0x180035f8b  mov     r9d, eax
0x180035f8e  lea     r8, [rsp+8E0h+FindFileData.cFileName]
0x180035f93  mov     ecx, 2; unsigned __int8
0x180035f98  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035f9d  test    rsi, rsi
0x180035fa0  jz      short loc_180035FAB
0x180035fa2  mov     rcx, rsi; hFindFile
0x180035fa5  call    cs:__imp_FindClose
0x180035fab  mov     eax, ebx
0x180035fad  mov     rcx, [rbp+7E0h+var_30]
0x180035fb4  xor     rcx, rsp; StackCookie
0x180035fb7  call    __security_check_cookie
0x180035fbc  mov     rbx, [rsp+8E0h+arg_10]
0x180035fc4  add     rsp, 8C0h
0x180035fcb  pop     r15
0x180035fcd  pop     r14
0x180035fcf  pop     r12
0x180035fd1  pop     rsi
0x180035fd2  pop     rbp
0x180035fd3  retn
```
