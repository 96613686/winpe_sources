# IsValidFilePath(ushort *,void *)

- ea: `0x14006e208`
- end: `0x14006e447`
- name: `?IsValidFilePath@@YAHPEAGPEAX@Z`
- size: `575`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *, HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x14006ff04`

## callees

- `0x140002c73`
- `0x140004e48`
- `0x140004eb0`
- `0x14006cd90`
- `0x14006e208`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetFileInformationByHandle` at `0x14006e396`
- `KERNEL32!GetFileInformationByHandle` at `0x14006e396`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14006e2a0`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14006e2a0`
- `KERNEL32!GetLastError` at `0x14006e403`
- `KERNEL32!GetLastError` at `0x14006e403`
- `msvcrt!wcsnlen` at `0x14006e2f0`
- `msvcrt!wcsnlen` at `0x14006e306`
- `msvcrt!wcsnlen` at `0x14006e321`
- `msvcrt!wcsnlen` at `0x14006e2f0`
- `msvcrt!wcsnlen` at `0x14006e306`
- `msvcrt!wcsnlen` at `0x14006e321`
- `msvcrt!_wcsnicmp` at `0x14006e2c7`
- `msvcrt!_wcsnicmp` at `0x14006e337`
- `msvcrt!_wcsnicmp` at `0x14006e2c7`
- `msvcrt!_wcsnicmp` at `0x14006e337`
- `msvcrt!free` at `0x14006e3f5`
- `msvcrt!free` at `0x14006e3f5`

## pseudocode

```c
_BOOL8 __fastcall IsValidFilePath(unsigned __int16 *a1, HANDLE hFile)
{
  int v4; // ebx
  char v5; // si
  size_t v6; // rbx
  size_t v7; // rax
  WCHAR *v8; // rcx
  size_t v9; // rax
  signed int LastError; // eax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String2[12]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR szFilePath[520]; // [rsp+80h] [rbp-80h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  memset_0(szFilePath, 0, sizeof(szFilePath));
  wcscpy(String2, L"\\\\?\\");
  if ( hFile == (HANDLE)-1LL )
  {
    v4 = -2147024809;
    return v4 >= 0;
  }
  if ( GetFinalPathNameByHandleW(hFile, szFilePath, 0x208u, 0) - 1 <= 0x207 )
  {
    if ( _wcsnicmp(a1, String2, 4u) )
    {
      a1 = ConvertFullPathToLongUNC(a1);
      v5 = 1;
    }
    else
    {
      v5 = 0;
    }
    v6 = wcsnlen(a1, 0x208u);
    v7 = wcsnlen(szFilePath, 0x208u);
    v8 = szFilePath;
    if ( v7 >= v6 )
      v8 = a1;
    v9 = wcsnlen(v8, 0x208u);
    if ( _wcsnicmp(szFilePath, a1, v9) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (_DWORD)a1,
          (__int64)szFilePath);
      }
    }
    else if ( GetFileInformationByHandle(hFile, &FileInformation) )
    {
      if ( FileInformation.nNumberOfLinks <= 1 )
      {
        v4 = 0;
        goto LABEL_22;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, a1);
      }
    }
    v4 = -2147024735;
LABEL_22:
    if ( v5 && a1 )
      free(a1);
    return v4 >= 0;
  }
  LastError = GetLastError();
  v4 = -2147024896;
  if ( LastError <= 0 )
    v4 = LastError;
  return v4 >= 0;
}

```

## disassembly

```asm
0x14006e208  mov     [rsp-8+arg_10], rbx
0x14006e20d  push    rbp
0x14006e20e  push    rsi
0x14006e20f  push    rdi
0x14006e210  push    r14
0x14006e212  push    r15
0x14006e214  lea     rbp, [rsp-3A0h]
0x14006e21c  sub     rsp, 4A0h
0x14006e223  mov     rax, cs:__security_cookie
0x14006e22a  xor     rax, rsp
0x14006e22d  mov     [rbp+3C0h+var_30], rax
0x14006e234  xorps   xmm0, xmm0
0x14006e237  mov     r14, rdx
0x14006e23a  mov     rdi, rcx
0x14006e23d  xor     eax, eax
0x14006e23f  xor     edx, edx; Val
0x14006e241  mov     [rsp+4C0h+FileInformation.nFileIndexLow], eax
0x14006e245  lea     rcx, [rbp+3C0h+szFilePath]; void *
0x14006e249  mov     r8d, 410h; Size
0x14006e24f  movups  xmmword ptr [rsp+4C0h+FileInformation.dwFileAttributes], xmm0
0x14006e254  movups  xmmword ptr [rsp+4C0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14006e259  movups  xmmword ptr [rsp+4C0h+FileInformation.nFileSizeHigh], xmm0
0x14006e25e  call    memset_0
0x14006e263  movsd   xmm0, qword ptr cs:asc_1400959B0; "\\\\?\\"
0x14006e26b  movzx   eax, word ptr cs:asc_1400959B0+8; ""
0x14006e272  movsd   qword ptr [rsp+4C0h+String2], xmm0
0x14006e278  mov     [rsp+4C0h+var_450], ax
0x14006e27d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14006e281  jnz     short loc_14006E28D
0x14006e283  mov     ebx, 80070057h
0x14006e288  jmp     loc_14006E419
0x14006e28d  mov     r15d, 208h
0x14006e293  lea     rdx, [rbp+3C0h+szFilePath]; lpszFilePath
0x14006e297  mov     r8d, r15d; cchFilePath
0x14006e29a  xor     r9d, r9d; dwFlags
0x14006e29d  mov     rcx, r14; hFile
0x14006e2a0  call    cs:__imp_GetFinalPathNameByHandleW
0x14006e2a7  nop     dword ptr [rax+rax+00h]
0x14006e2ac  dec     eax
0x14006e2ae  cmp     eax, 207h
0x14006e2b3  ja      loc_14006E403
0x14006e2b9  mov     r8d, 4; MaxCount
0x14006e2bf  lea     rdx, [rsp+4C0h+String2]; String2
0x14006e2c4  mov     rcx, rdi; String1
0x14006e2c7  call    cs:__imp__wcsnicmp
0x14006e2ce  nop     dword ptr [rax+rax+00h]
0x14006e2d3  test    eax, eax
0x14006e2d5  jz      short loc_14006E2E7
0x14006e2d7  mov     rcx, rdi; unsigned __int16 *
0x14006e2da  call    ?ConvertFullPathToLongUNC@@YAPEAGPEAG@Z; ConvertFullPathToLongUNC(ushort *)
0x14006e2df  mov     rdi, rax
0x14006e2e2  mov     sil, 1
0x14006e2e5  jmp     short loc_14006E2EA
0x14006e2e7  xor     sil, sil
0x14006e2ea  mov     rdx, r15; MaxCount
0x14006e2ed  mov     rcx, rdi; Source
0x14006e2f0  call    cs:__imp_wcsnlen
0x14006e2f7  nop     dword ptr [rax+rax+00h]
0x14006e2fc  mov     rdx, r15; MaxCount
0x14006e2ff  lea     rcx, [rbp+3C0h+szFilePath]; Source
0x14006e303  mov     rbx, rax
0x14006e306  call    cs:__imp_wcsnlen
0x14006e30d  nop     dword ptr [rax+rax+00h]
0x14006e312  mov     rdx, r15; MaxCount
0x14006e315  lea     rcx, [rbp+3C0h+szFilePath]
0x14006e319  cmp     rax, rbx
0x14006e31c  jb      short loc_14006E321
0x14006e31e  mov     rcx, rdi; Source
0x14006e321  call    cs:__imp_wcsnlen
0x14006e328  nop     dword ptr [rax+rax+00h]
0x14006e32d  mov     rdx, rdi; String2
0x14006e330  lea     rcx, [rbp+3C0h+szFilePath]; String1
0x14006e334  mov     r8, rax; MaxCount
0x14006e337  call    cs:__imp__wcsnicmp
0x14006e33e  nop     dword ptr [rax+rax+00h]
0x14006e343  test    eax, eax
0x14006e345  jz      short loc_14006E38E
0x14006e347  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e34e  lea     rax, WPP_GLOBAL_Control
0x14006e355  cmp     rcx, rax
0x14006e358  jz      short loc_14006E387
0x14006e35a  test    byte ptr [rcx+1Ch], 2
0x14006e35e  jz      short loc_14006E387
0x14006e360  cmp     byte ptr [rcx+19h], 2
0x14006e364  jb      short loc_14006E387
0x14006e366  mov     rcx, [rcx+10h]
0x14006e36a  lea     rax, [rbp+3C0h+szFilePath]
0x14006e36e  mov     edx, 51h ; 'Q'
0x14006e373  mov     [rsp+4C0h+var_4A0], rax
0x14006e378  mov     r9, rdi
0x14006e37b  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e382  call    WPP_SF_SS
0x14006e387  mov     ebx, 800700A1h
0x14006e38c  jmp     short loc_14006E3E8
0x14006e38e  lea     rdx, [rsp+4C0h+FileInformation]; lpFileInformation
0x14006e393  mov     rcx, r14; hFile
0x14006e396  call    cs:__imp_GetFileInformationByHandle
0x14006e39d  nop     dword ptr [rax+rax+00h]
0x14006e3a2  test    eax, eax
0x14006e3a4  jz      short loc_14006E387
0x14006e3a6  cmp     [rsp+4C0h+FileInformation.nNumberOfLinks], 1
0x14006e3ab  jbe     short loc_14006E3E6
0x14006e3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e3b4  lea     rax, WPP_GLOBAL_Control
0x14006e3bb  cmp     rcx, rax
0x14006e3be  jz      short loc_14006E387
0x14006e3c0  test    byte ptr [rcx+1Ch], 2
0x14006e3c4  jz      short loc_14006E387
0x14006e3c6  cmp     byte ptr [rcx+19h], 2
0x14006e3ca  jb      short loc_14006E387
0x14006e3cc  mov     rcx, [rcx+10h]
0x14006e3d0  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e3d7  mov     edx, 52h ; 'R'
0x14006e3dc  mov     r9, rdi
0x14006e3df  call    WPP_SF_S
0x14006e3e4  jmp     short loc_14006E387
0x14006e3e6  xor     ebx, ebx
0x14006e3e8  test    sil, sil
0x14006e3eb  jz      short loc_14006E419
0x14006e3ed  test    rdi, rdi
0x14006e3f0  jz      short loc_14006E419
0x14006e3f2  mov     rcx, rdi; Block
0x14006e3f5  call    cs:__imp_free
0x14006e3fc  nop     dword ptr [rax+rax+00h]
0x14006e401  jmp     short loc_14006E419
0x14006e403  call    cs:__imp_GetLastError
0x14006e40a  nop     dword ptr [rax+rax+00h]
0x14006e40f  test    eax, eax
0x14006e411  mov     ebx, 80070000h
0x14006e416  cmovle  ebx, eax
0x14006e419  not     ebx
0x14006e41b  shr     ebx, 1Fh
0x14006e41e  mov     eax, ebx
0x14006e420  mov     rcx, [rbp+3C0h+var_30]
0x14006e427  xor     rcx, rsp; StackCookie
0x14006e42a  call    __security_check_cookie
0x14006e42f  mov     rbx, [rsp+4C0h+arg_10]
0x14006e437  add     rsp, 4A0h
0x14006e43e  pop     r15
0x14006e440  pop     r14
0x14006e442  pop     rdi
0x14006e443  pop     rsi
0x14006e444  pop     rbp
0x14006e445  retn
```
