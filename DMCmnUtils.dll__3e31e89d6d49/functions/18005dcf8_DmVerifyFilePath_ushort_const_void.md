# DmVerifyFilePath(ushort const *,void *)

- ea: `0x18005dcf8`
- end: `0x18005decd`
- name: `?DmVerifyFilePath@@YAJPEBGPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HANDLE hFile)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18005dab0`
- `0x18005ded4`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180058368`
- `0x1800583e8`
- `0x18005dcf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005de51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005de51`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005ddfd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005de16`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005de36`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005ddfd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005de16`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005de36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005de92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005de92`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005de69`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005de69`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005dd88`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005dd88`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrNIW` at `0x18005ddb1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrNIW` at `0x18005ddb1`

## pseudocode

```c
signed int __fastcall DmVerifyFilePath(const unsigned __int16 *a1, HANDLE hFile)
{
  signed int result; // eax
  size_t v5; // rbx
  size_t v6; // rax
  WCHAR *v7; // rcx
  size_t v8; // rax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t Source[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szFilePath[264]; // [rsp+270h] [rbp+170h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  memset_0(szFilePath, 0, 0x20Au);
  memset_0(Source, 0, 0x20Au);
  if ( hFile == (HANDLE)-1LL )
    return -2147024809;
  if ( GetFinalPathNameByHandleW(hFile, szFilePath, 0x105u, 0) - 1 > 0x103 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    if ( !StrStrNIW(a1, L"\\\\?\\", 4u) && (int)StringCchCopyW(Source, 0x105u, L"\\\\?\\") < 0
      || StringCchCatW(Source, 0x105u, a1) < 0 )
    {
      return -2147024735;
    }
    v5 = wcsnlen(Source, 0x105u);
    v6 = wcsnlen(szFilePath, 0x105u);
    v7 = szFilePath;
    if ( v6 >= v5 )
      v7 = Source;
    v8 = wcsnlen(v7, 0x105u);
    if ( !(unsigned int)_o__wcsnicmp(szFilePath, Source, v8) && GetFileInformationByHandle(hFile, &FileInformation) )
      return FileInformation.nNumberOfLinks > 1 ? 0x800700A1 : 0;
    else
      return -2147024735;
  }
  return result;
}

```

## disassembly

```asm
0x18005dcf8  mov     [rsp-8+arg_10], rbx
0x18005dcfd  push    rbp
0x18005dcfe  push    rsi
0x18005dcff  push    rdi
0x18005dd00  lea     rbp, [rsp-390h]
0x18005dd08  sub     rsp, 490h
0x18005dd0f  mov     rax, cs:__security_cookie
0x18005dd16  xor     rax, rsp
0x18005dd19  mov     [rbp+3A0h+var_20], rax
0x18005dd20  xorps   xmm0, xmm0
0x18005dd23  mov     rdi, rdx
0x18005dd26  mov     rbx, rcx
0x18005dd29  xor     eax, eax
0x18005dd2b  mov     esi, 20Ah
0x18005dd30  mov     [rsp+4A0h+FileInformation.nFileIndexLow], eax
0x18005dd34  mov     r8d, esi; Size
0x18005dd37  lea     rcx, [rbp+3A0h+szFilePath]; void *
0x18005dd3e  xor     edx, edx; Val
0x18005dd40  movups  xmmword ptr [rsp+4A0h+FileInformation.dwFileAttributes], xmm0
0x18005dd45  movups  xmmword ptr [rsp+4A0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18005dd4a  movups  xmmword ptr [rsp+4A0h+FileInformation.nFileSizeHigh], xmm0
0x18005dd4f  call    memset_0
0x18005dd54  mov     r8d, esi; Size
0x18005dd57  lea     rcx, [rsp+4A0h+Source]; void *
0x18005dd5c  xor     edx, edx; Val
0x18005dd5e  call    memset_0
0x18005dd63  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005dd67  jnz     short loc_18005DD73
0x18005dd69  mov     eax, 80070057h
0x18005dd6e  jmp     loc_18005DEAA
0x18005dd73  mov     esi, 105h
0x18005dd78  lea     rdx, [rbp+3A0h+szFilePath]; lpszFilePath
0x18005dd7f  mov     r8d, esi; cchFilePath
0x18005dd82  xor     r9d, r9d; dwFlags
0x18005dd85  mov     rcx, rdi; hFile
0x18005dd88  call    cs:__imp_GetFinalPathNameByHandleW
0x18005dd8f  nop     dword ptr [rax+rax+00h]
0x18005dd94  dec     eax
0x18005dd96  cmp     eax, 103h
0x18005dd9b  ja      loc_18005DE92
0x18005dda1  mov     r8d, 4; cchMax
0x18005dda7  lea     rdx, pszSrch; "\\\\?\\"
0x18005ddae  mov     rcx, rbx; pszFirst
0x18005ddb1  call    cs:__imp_StrStrNIW
0x18005ddb8  nop     dword ptr [rax+rax+00h]
0x18005ddbd  test    rax, rax
0x18005ddc0  jnz     short loc_18005DDDD
0x18005ddc2  lea     r8, pszSrch; "\\\\?\\"
0x18005ddc9  mov     edx, esi; unsigned __int64
0x18005ddcb  lea     rcx, [rsp+4A0h+Source]; unsigned __int16 *
0x18005ddd0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ddd5  test    eax, eax
0x18005ddd7  js      loc_18005DE8B
0x18005dddd  mov     r8, rbx; unsigned __int16 *
0x18005dde0  lea     rcx, [rsp+4A0h+Source]; unsigned __int16 *
0x18005dde5  mov     rdx, rsi; unsigned __int64
0x18005dde8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005dded  test    eax, eax
0x18005ddef  js      loc_18005DE8B
0x18005ddf5  mov     rdx, rsi; MaxCount
0x18005ddf8  lea     rcx, [rsp+4A0h+Source]; Source
0x18005ddfd  call    cs:__imp_wcsnlen
0x18005de04  nop     dword ptr [rax+rax+00h]
0x18005de09  mov     rdx, rsi; MaxCount
0x18005de0c  lea     rcx, [rbp+3A0h+szFilePath]; Source
0x18005de13  mov     rbx, rax
0x18005de16  call    cs:__imp_wcsnlen
0x18005de1d  nop     dword ptr [rax+rax+00h]
0x18005de22  mov     rdx, rsi; MaxCount
0x18005de25  lea     rcx, [rbp+3A0h+szFilePath]
0x18005de2c  cmp     rax, rbx
0x18005de2f  jb      short loc_18005DE36
0x18005de31  lea     rcx, [rsp+4A0h+Source]; Source
0x18005de36  call    cs:__imp_wcsnlen
0x18005de3d  nop     dword ptr [rax+rax+00h]
0x18005de42  mov     r8, rax
0x18005de45  lea     rdx, [rsp+4A0h+Source]
0x18005de4a  lea     rcx, [rbp+3A0h+szFilePath]
0x18005de51  call    cs:__imp__o__wcsnicmp
0x18005de58  nop     dword ptr [rax+rax+00h]
0x18005de5d  test    eax, eax
0x18005de5f  jnz     short loc_18005DE8B
0x18005de61  lea     rdx, [rsp+4A0h+FileInformation]; lpFileInformation
0x18005de66  mov     rcx, rdi; hFile
0x18005de69  call    cs:__imp_GetFileInformationByHandle
0x18005de70  nop     dword ptr [rax+rax+00h]
0x18005de75  test    eax, eax
0x18005de77  jz      short loc_18005DE8B
0x18005de79  mov     eax, 1
0x18005de7e  cmp     eax, [rsp+4A0h+FileInformation.nNumberOfLinks]
0x18005de82  sbb     eax, eax
0x18005de84  and     eax, 800700A1h
0x18005de89  jmp     short loc_18005DEAA
0x18005de8b  mov     eax, 800700A1h
0x18005de90  jmp     short loc_18005DEAA
0x18005de92  call    cs:__imp_GetLastError
0x18005de99  nop     dword ptr [rax+rax+00h]
0x18005de9e  test    eax, eax
0x18005dea0  jle     short loc_18005DEAA
0x18005dea2  movzx   eax, ax
0x18005dea5  or      eax, 80070000h
0x18005deaa  mov     rcx, [rbp+3A0h+var_20]
0x18005deb1  xor     rcx, rsp; StackCookie
0x18005deb4  call    __security_check_cookie
0x18005deb9  mov     rbx, [rsp+4A0h+arg_10]
0x18005dec1  add     rsp, 490h
0x18005dec8  pop     rdi
0x18005dec9  pop     rsi
0x18005deca  pop     rbp
0x18005decb  retn
```
